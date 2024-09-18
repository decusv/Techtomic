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

### Replication (Master-Master / Active)

Load balances and synchronizes data across two master databases.

- Provides redundancy and handles write operations on both masters.
- Propagates data changes between master databases.

### [[Load Balancing Methods|Load Balancing Methods]] and Replication (Both)

Load balancing with replication distributes incoming requests across multiple replica servers. 

In passive replication (e.g., master-slave setups), read requests are balanced among multiple slave nodes while all write requests are directed to a single master node, which then propagates changes to the slaves.

In active replication (e.g., master-master setups), both read and write requests are distributed across all active nodes, each capable of processing requests and synchronizing with others. 