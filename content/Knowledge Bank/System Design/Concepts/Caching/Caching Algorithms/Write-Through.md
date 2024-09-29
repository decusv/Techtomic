---
title: Write-Through
draft: false
tags:
  - caching
---
![[Pasted image 20240929223054.png]]

In a write-through approach, the application uses the cache as the main data store. In other words:

1. Application adds a new entry or updates an existing entry in a cache.
2. The cache writes the entry to the data store e.g., a DB.
3. The new/updated data is returned to the application for immediate access.

## Disadvantages of write-through

1. Extended latency from write operations due to having to write to the cache, and then also to the database.
2. If the cache fails and a new instance is spun up, entries won't be cached until data has been updated. Using [[Cache-Aside]] in conjunction with write operations can mitigate this.
3. Most data that has been written might not be read again. This can be minimized with a short TTL.