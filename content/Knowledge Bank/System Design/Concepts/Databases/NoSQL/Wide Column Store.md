---
title: Wide Column Store
draft: false
tags:
  - databases
  - nosql
---
![[Pasted image 20240929164908.png]]

A wide column store is a type of a [[NoSQL]] database designed for handling large amounts of data inside flexible data structures i.e., different rows in the same column family can have different sets of columns, allow you to store only the necessary data for each row without having to define empty fields.

For example, for a "users" super column family, some rows i.e., individual users, may have an "email" field, whilst others may have a "phone" field.

The basic unite of data is a column which represents a name-value pair e.g., "protocol"-"http".

---

## Advantages of Wide Column Stores

1. Highly available
2. Highly scalable
3. Flexible schema/data structures.


## Disadvantages of Wide Column Stores

1. Designing a schema is complicated because data needs to be denormalized and structured for efficient querying.
2. Not designed for complex queries that involve joins, aggregations or subqueries.
3. Follows [[Eventual Consistency]].

---

## Examples of wide column stores

1. Google BigTable
2. Cassandra
3. HBase
