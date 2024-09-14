---
title: Shared - State
draft: false
tags:
  - concurrency
---
**Shared-State** concurrency involves multiple threads or processes accessing and modifying the same memory. 

### Key concepts 

**Shared Data** - Threads or processes work on common data, requiring synchronization mechanisms like locks to manage access.

**Synchronization** -  Ensures only one thread or process modifies the data at a time to prevent race conditions and maintain consistency

**Challenges** - Managing concurrent access can be complex and error-prone, involving risks such as deadlocks, race conditions, and performance issues.