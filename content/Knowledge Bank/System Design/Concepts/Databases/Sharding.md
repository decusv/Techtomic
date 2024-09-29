---
title: Sharding
draft: false
tags:
  - system-design
  - databases
---
Sharding refers to the concept of splitting your database (both relational and non-relational) horizontally, and distributing your data across multiple servers a.k.a. shards, where each shard contains a subset of the data.

This allows for [[Scaling Approaches#Horizontal Scaling|horizontal scaling]] as the data continues to grow, allowing you to handle more queries by spreading the load across several machines.#

## Advantages of Sharding

- Sharding reduces dataset size which improves performance due to smaller index size.
- Reduced datasets also ensure higher [[Cache Locality]].
- Allows for a higher throughput of writes due to shards allowing independent writes instead of having to go through a central master database.
## Disadvantages of Sharding

- Application logic will have to be updated to work with shards and lead to complex SQL queries.
- Distribution of data across shards might be lopsided. Some shards may be under increased load compared to the others.
	- To fix this, rebalancing of data across shards is needed. This may require moving a potentially large amount of data which can be resource intensive.
	- Ensuring a system remains operational during rebalancing adds significant complexity.


## Additional Topics

1. Consistent Hashing using ring-based structures in sharding.

