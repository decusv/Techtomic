---
title: ACID
draft: false
tags:
  - acronym
  - system-design
  - databases
---
ACID describes the properties that a well designed database management system should exhibit in order to ensure data integrity, reliability and consistency during transaction processing.

## ACID rules

**Atomicity**: A transaction is all-or-nothing. If it fails, nothing changes in the database.
    
**Consistency**: Transactions must keep the database in a valid state, following all rules.
    
**Isolation**: Transactions run separately from each other, so they don’t interfere.
    
**Durability**: Once a transaction is saved, it stays saved, even if there’s a crash.