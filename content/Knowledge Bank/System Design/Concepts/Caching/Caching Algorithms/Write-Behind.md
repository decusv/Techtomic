---
title: Write-Behind
draft: false
tags:
  - caching
---
![[Pasted image 20240929225429.png]]

Write-behind (also known as write-back) follows a similar principle to [[Write-Through]]. The difference being is that the write operation to the data store is done asynchronously by putting the write message into a queue e.g., Kafka queue.

## Disadvantages of write-behind

1. Harder to implement than [[Cache-Aside]] and [[Write-Through]]
2. Potential risk of data loss if the cache fails before adding the event to the queue.