---
title: Key-Value Store
draft: false
tags:
  - databases
  - nosql
---
A key-value store generally allows for O(1) (constant time) read and write operations. This is because data is accessed via the key, ensuring there is no need to search through large datasets.

Implementations of **lexicographical order** in key-value stores allow for efficient queries for *ranges* of information e.g., values with keys that start between "a" and "c".

Key-value store implementations are generally simple, which means most logic has to be written within the application code.

Key-value stores can also hold metadata associated with the value e.g., timestamps, or other attributes like permissions needed.


---

## Key-Value Store Uses

1. Redis (uses memory or SSDs to ensure low-latency)
2. DynamoDB
3. Memcached
4. Used to build [[Document Store]] and [[Graph Store]]