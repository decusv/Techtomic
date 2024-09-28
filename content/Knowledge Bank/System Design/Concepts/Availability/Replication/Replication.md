---
title: Replication
draft: false
tags:
  - system-design
  - availability
---
## Active Replication

Active replication is a replication strategy where all replicas process requests simultaneously and independently. Each replica runs the same logic and produces the same result. This is useful for fault tolerance but can be resource-intensive.

## Passive Replication

In passive replication, only one replica processes requests, while others remain in standby. The active replica handles requests and updates backups (passive replicas), which take over only if the active one fails. This reduces resource consumption but introduces some latency in failover situations.

---

### Replication (Master-Slave / Passive)

Automatically copies data from a master database to slave databases. Read from slave copies, write data to master, then propagate data from master to slaves.

- Slaves replicate every row from the master.
- Ensures redundancy in case of master DB failure.
- Slaves can handle read-heavy applications, improving concurrency and load balancing for read requests.

If the master instance goes down, then a slave instance can be promoted to master, but this requires additional logic to exist for this to work.

Disadvantages:

- Potential problems can occur when the master instance goes down after a new write before it can be replicated to the read replicas (slaves). To fix this, the write should only be confirmed after another read replicas has confirmed receipt of the most recent write operation.

- In a system with high volume of writes, read replicas can be overwhelmed with constant need to replay the writes into their own storage which can prevent them from actually serving read requests effectively. 

- In a system with high number of read replicas (slaves), replication lag is introduced before some replicas are up-to-date thus increasing the likelihood of serving out-of-date or stale data. 

	Lag can be introduced due to network latency, or processing delays (maybe due to differing hardware resources available between the read replicas).

---

### Replication (Master-Master / Active)

Load balances and synchronizes data across two master databases.

- Provides redundancy and handles write operations on both masters.
- Propagates data changes between master databases.

Disadvantages:

- Most master-master systems are loosely consistent (do not guarantee the data is immediately updated across all instances after every write operation), thus violating [[ACID]], or have increased write latency due to requiring synchronising across both master instances.

- As number of instances increases, and as network latency increases, the conflict resolution process which determines which version of the data is "correct" can begin to occur more often and also increase [[Latency]].


---
### [[Load Balancing Methods|Load Balancing Methods]] and Replication (Both)

Load balancing with replication distributes incoming requests across multiple replica servers. 

In passive replication (e.g., master-slave setups), read requests are balanced among multiple slave nodes while all write requests are directed to a single master node, which then propagates changes to the slaves.

In active replication (e.g., master-master setups), both read and write requests are distributed across all active nodes, each capable of processing requests and synchronizing with others. 