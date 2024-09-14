---
title: Immutability in Scalability
draft: false
tags:
  - scalability
---
## Definition

Immutability is a characteristic given to an object or data structure that cannot be changed.

## In the Context of Scalability

Immutable data structures make distributed systems easier to scale, as complications relating to state changes can be avoided. Since immutable objects don't change, they can be safely shared between threads, processes or systems without the need for synchronizing. 

Synchronizing is needed to ensure data consistency and prevent race conditions (multiple processes or threads trying to access and modify the same data simultaneously).

Systems designed using functional programming paradigms via languages like Haskell, allow you to leverage immutability to achieve scalability and reliability. 