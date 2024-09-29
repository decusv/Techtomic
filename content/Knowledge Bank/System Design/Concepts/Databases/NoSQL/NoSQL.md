---
title: NoSQL
draft: false
tags:
  - databases
  - nosql
---
NoSQL refers to a non-relational database e.g., MongoDB. There are different types of data representations available. Data in these kinds of databases is [[Denormalization|denormalized]], where joins are done within the application's code.

Most NoSQL databases lack [[ACID]] transactions, and instead favour [[Eventual Consistency|eventual consistency]]. Instead, [[BASE]] is often used to describe the properties of NoSQL databases. In relation to the [[CAP Theorem]], NoSQL prioritizes [[Availability|availability]] over consistency.
 
---

## NoSQL Representation Types

1. [[Key-Value Store]]
2. [[Document Store]]
3. [[Graph Store]]
4. [[Wide Column Store]]

---

## Reasons to use NoSQL

1. Dynamic/flexible schema is required.
2. Complex joins won't be required.
3. Need to store terabytes or petabytes of data.
4. Used by an application with large volumes of data that requires real-time processing or some other data-intensive workload.
5. Used by an application that is processing thousands of transactions per second i.e., high [[Throughput|throughput]].