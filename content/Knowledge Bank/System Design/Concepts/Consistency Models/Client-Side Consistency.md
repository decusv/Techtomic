---
title: Client-Side Consistency
draft: false
tags:
  - consistency
---
Client-Side consistency refers to models used to describe how data is maintained from the perspective of the client.


## Client-Side Causal Consistency

**Client-Side Causal Consistency** ensures that if one operation (let's say "A") causes another operation (say "B"), then all clients will see operation "A" before operation "B". However, unrelated operations might not follow this order strictly.


## Read-Your-Writes Consistency

Guarantees that after a client writes data, they will always read their own updates, even if the data hasn’t propagated to other replicas.


## Session Consistency

Guarantees [[#Read-Your-Writes Consistency|read-your-writes consistency]] during the duration of a session. This means within a single session (like while you're logged in), your reads and writes will be consistent, but outside that session, the guarantee may not hold.

## Monotonic Read Consistency

This guarantees that if you read a certain value of data, any future reads will never return an **older** value. In other words, your reads will always show data that is at least as up-to-date as your last read. 

Keep in mind, they might show the same value or a more recent one.

## Monotonic Write Consistency

Ensures that write operations are performed in order. Once you submit a write, any following write operation will not happen until the first one is fully applied. 

If you transfer money between accounts, the system ensures that the withdrawal from one account occurs before the deposit to the other.