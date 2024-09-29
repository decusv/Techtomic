---
title: Caching Types
draft: false
tags:
  - caching
---
## Client-side Caching

This type of caching would be located on the client side e.g., the operating system, or the web browser.

---
## Web Server Caching

[[Reverse Proxy|Reverse proxies]] can be put in front of web servers and act as caches. Similarly, you can use web accelerators like Varnish Cache to speed up static content delivery.

---
## Application caching

Examples include [[Caching Software#Memcached|Memcached]] and [[Caching Software#Redis|Redis]]. Given limited space, cache invalidation algorithms then to lead to certain cached entries to expire via algorithms like least recently used (LRU) to invalidate 'cold' entries.

---
### Query-Based Caching:

This is the most common caching pattern, where the result of a database query is stored in the cache, using a **hashed query** as the cache key. When the query is run again, the cache is checked first. However, this approach has challenges, particularly with **expiration**. If a single piece of data changes (e.g., a table cell), you need to invalidate all cached queries that may include that data, which can be complex and inefficient.

---
## Object Caching

Refers to caching complete objects e.g., data structures, records or files in memory. Can be implemented using [[Caching Software#Memcached|Memcached]] and [[Caching Software#Redis|Redis]].

### Examples of objects to cache:

- User sessions
	- Good to cache as these are frequently accessed, but don't change often e.g.,  authentication data, preferences, session state. 

- Fully rendered blog articles
	- Good to cache because once pages are rendered, they'll only need to be re-cached if the content changes or if the website layout changes.
	
- Activity streams
	- Posts, comments and likes are more generally more read heavy than write.
