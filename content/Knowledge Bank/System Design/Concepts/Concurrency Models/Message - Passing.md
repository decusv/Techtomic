---
title: Message - Passing
draft: false
tags:
  - concurrency
---
Message-passing concurrency involves communication between threads or processes through messages rather than sharing state directly.

## Key Concepts

**Communication** -  Threads or processes exchange data by sending messages to each other, typically through queues or channels.

**Decoupling** - Reduces the need for explicit synchronization since each entity operates independently and communicates via messages.

**Advantages** - Simplifies concurrency management by avoiding shared state issues and reduces the likelihood of race conditions. Common in distributed systems and actor-based models.