---
title: Server-Side Consistency
draft: false
tags:
  - consistency
---
Server-side consistency deals with how the servers in a distributed system handle updates and reads. Data is typically replicated across multiple servers to improve availability and fault tolerance.


## Number Of Nodes (N) 

The number of nodes that store **replicas** of the data. This ensures redundancy so that if one node fails, the data is still available

## Write Acknowledgements (W)

The number of replicas that need to **acknowledge** receipt of the update for the update to be considered complete. Higher W means stronger consistency, but it may reduce availability or speed.

## Read Acknowledgements (R)

The number of replicas that need to respond with the latest version of the data when a read operation is performed. Remember that in distributed systems, a number of replicas could be consulted for a read operation.

---

## Strong Consistency (W + R > N)

In strong consistency, **W + R > N**, meaning that the sum of write acknowledgments and read acknowledgments is greater than the total number of nodes.

This ensures that at least one replica has the most recent data during a read operation, guaranteeing consistent reads and writes.

In a banking system, strong consistency ensures that any read after a transaction will always reflect the updated balance.

## Eventual Consistency (W + R ≤ N)

In eventual consistency, **W + R ≤ N**, meaning the sum of the write and read acknowledgments is less than or equal to the number of replicas.

This allows updates to be propagated **gradually**, so some nodes might have outdated data for a period of time. However, eventually, all replicas will converge to the same data.
