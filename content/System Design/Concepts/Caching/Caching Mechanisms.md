---
title: Caching Mechanisms
draft: false
tags:
  - system-design
  - availability
---

## Memcached

**Usage**: Widely used by large-scale applications like Facebook to improve performance.

**Feature**: A high-performance, distributed memory object caching system that stores data in in-memory for rapid retrieval.

**Management**: Supports simple key-value data structures and automatically handles data expiration using an eviction policy. It is not persistent, so cached data is lost on restart.


## Redis
 

**Usage**: Popular in real-time applications like Twitter for caching, session management, and more.

**Feature**: An in-memory data structure store that supports various data types like strings, lists, sets, and hashes, offering more flexibility compared to Memcached.

**Management**: Supports automatic data expiration and eviction, but also offers persistence options (e.g., snapshotting and AOF) to save data to disk, ensuring data durability in case of failure.

* Snapshotting - refers to saving data to a binary file every x minutes, or every x write operations. Can still result in data loss in-between snapshots being recorded.

- Append Only File (AOF) - Every write operation is logged in real-time. Allows to reconstruct the dataset in case of a crash.


