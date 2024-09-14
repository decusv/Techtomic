---
title: CAP Theorem
draft: false
tags:
  - system-design
  - performance
---
Brewer's CAP Theorem states that in a distributed system, it is impossible to achieve all three of the below guarantees simultaneously:

1. **Consistency** - Every read request receives the most recent written data.
2. Availability - Every request receives a response (both success and **failures**).
3. **Partition Tolerance** - The system continues to operate despite network partitions (also known as network splits) i.e., a distributed system's network has been partitioned where the partitioned areas cannot communicate with each other.
