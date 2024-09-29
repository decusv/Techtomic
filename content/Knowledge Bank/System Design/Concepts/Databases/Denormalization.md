---
title: Denormalization
draft: false
tags:
  - "#databases"
  - system-design
---
## Definition

Intentional duplication of data across multiple tables, or storing the data in fewer, larger tables to reduce the need for using join commands in your database queries. 

Best suited for distributed systems where querying often requires complex joins.

## Advantages of Denormalization

- Improved read performance by storing redundant copies of data in multiple denormalized tables.
- Avoids expensive joins during reads, improving read speeds.

## Disadvantages of Denormalization

- Decreases write speeds as data has to be updated across several copies of the data across multiple tables which have been denormalized.
- Data is duplicated.
-  A denormalized database under heavy load may perform worse than a normalized counterpart.
- Ensuring the redundant copies remain consistent and up-to-date can introduce additional complexity (similar to [[Replication#Replication (Master-Master / Active)|master-master replication]]).


