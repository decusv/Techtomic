---
title: Replication
draft: false
tags:
  - system-design
  - availability
---
### Replication (Master-Slave)

- **Overview**: Automatically copies data from a master database to slave databases. Read from slave copies, write data to master, then propagate data from master to slaves.

- **Details**:
    - Slaves replicate every row from the master.
    - Ensures redundancy in case of master DB failure.
    - Slaves can handle read-heavy applications, improving concurrency and load balancing for read requests.

### Replication (Master-Master)

- **Overview**: Load balances and synchronizes data across two master databases.

- **Details**:
    - Provides redundancy and handles write operations on both masters.
    - Propagates data changes between master databases.

### [[Load Balancing Methods|Load Balancing Methods]] and Replication

- **Overview**: Integrates load balancing with replication for improved reliability.
- **Details**:
    - Addresses potential failures in load balancers, web servers, or master databases.
    - Ensures continued operation despite failures in individual components.
