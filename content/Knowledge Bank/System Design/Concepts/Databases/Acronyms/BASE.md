---
title: BASE
draft: false
tags:
  - acronym
  - system-design
  - databases
---
BASE is conceptual model designed to provide an alternative to [[ACID]], which is typically used in relational databases. It is suited for large-scale, distributed and fault-tolerant systems that need to prioritize availability and scalability over [[Eventual Consistency|strong consistency]].

## What is BASE?

Basically Available - Respond to every request, although not guarantee most up-to-date data. Achieved through replicating data across nodes and therefore allowing the system to remain responsive even in the presence of failures or partitions. Useful for always-on services.

Soft State - The system's state can change over time because replicas of data may not be immediately synchronised. In contrast, traditional system expect to have consistent data at all times. The system must allow uncertainty in its state while updates are propagating across replicas.

[[Eventual Consistency]] - System guarantees that with enough time, all replicas will eventually converge on the same state.
