---
title: Caching Mechanisms
draft: false
tags:
  - system-design
  - availability
---
### Caching Mechanisms

- **MySQL Caching**: Stores query results in memory for faster access.
- **Memcached**:
    - **Usage**: Employed by companies like Facebook.
    - **Feature**: Caches data in RAM for quick retrieval.
    - **Management**: Handles data expiration and priority.
    - **Type**: Key-value store.

### InnoDB Storage Engine

- **Overview**: Used by MySQL and MariaDB.
- **Features**:
    - **Row-Level Locking**: Improves concurrency compared to table-level locking.
    - **ACID Compliance**: Ensures transactions are:
        - **Atomic**: No partial transactions.
        - **Consistent**: Maintains database state before and after transactions.
        - **Durable**: Persists changes even after a crash.
        - **Isolated**: Transactions operate independently, with isolation level affecting behaviour. Different isolation configurations available in DBs :
            - **Serializable**: Ensures sequential execution on the same record, which can impact performance due to high locking.