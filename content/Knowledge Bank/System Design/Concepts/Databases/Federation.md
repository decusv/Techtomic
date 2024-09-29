---
title: Federation
draft: false
tags:
  - databases
---
Federation is a process also known as functional partitioning. It refers to splitting a large, monolithic database into multiple smaller databases based on the domain, or function they will serve. Federation is contrasted by horizontal partitioning e.g., [[Sharding]].

For example, a large database could be split into tables such as :

1. The users database that contains user data.
2. A forums database that contains threads and the posts within those threads.

## Advantages of Federation

- Smaller databases result in more data being stored in a cache. This in turn improves [[Cache Locality]] and in turn cache hits i.e., the likelihood of finding the data being looked for inside the cache storage.

## Disadvantages of Federation

- Federation will not be effective if your database schema requires huge tables.
- The application logic will have to be updated to determine which database to query.
- Federation will add more complexity and more hardware (due to more databases).
- Joining data from two databases will be complex as a server link will be required.