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
## Weak Consistency

After a write, reads may or may not see it. Best effort approach is taken. Best suited for Voice Over Internet Protocol (VoIP), video-chat, multiplayer games, reception.

## Strong Consistency (W + R > N)

In strong consistency, **W + R > N**, meaning that the sum of write acknowledgments and read acknowledgments is greater than the total number of nodes. This ensures that at least one replica has the most recent data during a read operation, guaranteeing consistent reads and writes. Only one read replica is needed to have the most recent data, as the system can do something like prioritize the most up-to-date read replica.

***Synchronous*** replication is used. This ensures that the system wait for the data to be replicated to multiple replicas before acknowledging the write operation as complete to the client. Consensus protocols help coordinate that read operations only retrieve the most recent writes.

Works well in systems that need transactions.





## Eventual Consistency (W + R ≤ N)

In eventual consistency, **W + R ≤ N**, meaning the sum of the write and read acknowledgments is less than or equal to the number of replicas.

This allows updates to be propagated **gradually**, so some nodes might have outdated data for a period of time. However, eventually, all replicas will converge to the same data.

Data is replicated asynchronously which means data isn't going to be immediately replicated. It will be propagated, but the client will receive a response prior to replication being completed. This allows the system to continue operating without waiting for all replicas to be updated.

Works well in highly available systems.
