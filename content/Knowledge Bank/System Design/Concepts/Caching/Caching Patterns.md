---
title: Caching Patterns
draft: false
tags:
  - "#caching"
---
### Query-Based Caching:

This is the most common caching pattern, where the result of a database query is stored in the cache, using a **hashed query** as the cache key. When the query is run again, the cache is checked first. However, this approach has challenges, particularly with **expiration**. If a single piece of data changes (e.g., a table cell), you need to invalidate all cached queries that may include that data, which can be complex and inefficient.

### Cached Objects:

A better approach is to cache data as **objects**. For example, if you have a "Product" class that gathers data from multiple sources (prices, reviews, etc.), once the data is assembled, store the entire **object or dataset** in the cache. This simplifies invalidation—when a piece of data changes, you can remove or update the cached object directly.

This method also allows for **asynchronous processing**, where worker servers can assemble and cache objects in the background, significantly reducing database load.

Can be implemented using [[Caching Mechanisms#Memcached|Memcached]] and [[Caching Mechanisms#Redis|Redis]].

### Examples of objects to cache:

- User sessions
	- Good to cache as these are frequently accessed, but don't change often e.g.,  authentication data, preferences, session state. 

- Fully rendered blog articles
	- Good to cache because once pages are rendered, they'll only need to be re-cached if the content changes or if the website layout changes.
	
- Activity streams
	- Posts, comments and likes are more generally more read heavy than write.
