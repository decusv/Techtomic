---
title: Refresh-Ahead
draft: false
tags:
  - caching
---
![[Pasted image 20240929225824.png]]

In a refresh-ahead approach, cache entries can be automatically refresh by the data store prior to the entry's expiration. 

## Disadvantages of refresh-ahead

1. Accurately predicting which entries to refresh is difficult.
2. Can be worse using this approach than not.