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

Given that networks are not reliable, you only get to choose to focus on consistency (CP) or availability (AP)

## Consistency + Partition Tolerance (CP)

If a network partition/split occurs, wait for a response. In case the node being targeted has failed, you'd get an error (hence losing availability). However, you could guarantee data consistency i.e., getting the most recent writes.

This is best suited for systems requiring atomic reads and writes i.e., no chance for ambiguity like banking applications.

---

## Availability + Partition Tolerance (AP)

In this case, a targeted node returns a most recent version of data available in that node, which is not necessarily the most recent piece of data i.e., stale data.

Writes can still be made, and the writes can be queued for later processing when the network partition/split has been resolved. 

In this case, the application shouldn't require atomic reads and writes e.g., shopping applications that could lose your shopping cart information.