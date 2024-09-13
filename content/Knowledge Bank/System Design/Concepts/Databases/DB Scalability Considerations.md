---
title: DB Scalability Considerations
draft: false
tags:
  - scalability
  - system-design
  - "#databases"
---

## Scaling Relational Databases

In order to scale relational DBs like MySQL, you'll need to scale your DBs both [[Scaling Approaches#Vertical Scaling#|vertically]] and [[Scaling Approaches#Horizontal Scaling|horizontally]]. 

From a vertical perspective, you'll need upgrade your master (in a [[Replication#Replication (Master-Slave)|in master-slave replication set-up]]) server with more RAM to scale with the increasing number of read operations, and in turn slave replicas to propagate changes to. Hardware scaling only becomes more costly.

From a horizontal scaling perspective, with the increasing read operations, you'll need to scale the number of slave replicas available.

## Scaling Non-Relation (NoSQL) Databases

