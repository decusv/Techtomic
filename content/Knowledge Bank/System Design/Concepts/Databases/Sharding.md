---
title: Sharding
draft: false
tags:
  - system-design
  - databases
---
Sharding refers to the concept of splitting your database (both relational and non-relational) horizontally, and distributing your data across multiple servers a.k.a. shards, where each shard contains a subset of the data.

This allows for [[Scaling Approaches#Horizontal Scaling|horizontal scaling]] as the data continues to grow, allowing you to handle more queries by spreading the load across several machines.

