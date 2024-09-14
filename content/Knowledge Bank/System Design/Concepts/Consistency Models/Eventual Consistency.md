---
title: Eventual Consistency
draft: false
tags:
  - system-design
  - consistency
---
Eventual consistency refers to a consistency model in distributed systems where updates made to a distributed data store will propagate to all replicas (although not necessarily immediately). Once the propagation of of the updates completes, all replicas will converge on the same state.

When relating this to Brewer's [[CAP Theorem]], systems that employ this model tend to focus on availability and partition tolerance guarantees, as this doesn't guarantee most recent write updates for every read request made.

## Use Cases

1. Cassandra
2. AWS DynamoDB