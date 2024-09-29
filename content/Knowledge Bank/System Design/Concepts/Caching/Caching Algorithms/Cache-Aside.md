---
title: Cache-Aside
draft: false
tags:
  - caching
---
![[Pasted image 20240929222650.png]]

In a cache-aside (also known as lazy loading) approach, the cache doesn't directly interact with the storage e.g., database. Instead, the application first queries the cache. If the cache results in a cache miss, then the query is made to the storage. After which, the entry is added to a cache. Lastly, the cached entry is returned to the user.

## Disadvantages

1.  Each cache miss results in three trips (query cache, query storage, add entry to cache).
2. If the data is updated in the database, the cache may still hold stale data.
3. If a cache fails, it has to be repopulated.