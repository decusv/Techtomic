---
title: Asynchronism
draft: false
tags:
  - async
---
Asynchronous workflows improve system performance by allowing expensive computational operations to be performed 'in the background' rather than having to wait for the operation to complete.

## Advantages of Asynchronism

- Reducing request times as you can offload expensive requests instead of having to wait for them.
- Allows you to pre-process data ahead of time e.g., generating detailed reports which may take along time as generating and requesting the reports are now decoupled due to asynchronism.

## Disadvantages of Asynchronism

- Some use cases that are computationally inexpensive operations might be better suited for synchronous processing as introducing queues can increase [[Latency]] and add more complexity.

---

## Implementations of Asynchronism

- [[Message Queues]]