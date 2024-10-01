---
title: HTTP
draft: false
tags:
  - protocol
---
HTTP is a method for encoding and transporting data between a client and a server. It is a request-response protocol i.e., clients issue requests and servers issue responses with relevant results.

HTTP is self-contained i.e., it contains all relevant information within the HTTP message to traverse intermediary devices like [[Load Balancer|load balancers]] or routers. The self-contained nature also allows responses to be [[Cache|cached]] and sent when needed.


---

### HTTP API Methods

|Verb|Description|Idempotent*|Safe|Cacheable|
|---|---|---|---|---|
|GET|Reads a resource|Yes|Yes|Yes|
|POST|Creates a resource or trigger a process that handles data|No|No|Yes if response contains freshness info|
|PUT|Creates or replace a resource|Yes|No|No|
|PATCH|Partially updates a resource|No|No|Yes if response contains freshness info|
|DELETE|Deletes a resource|Yes|No|No|

*Can be called many times without different outcomes.

HTTP is an application layer protocol relying on lower-level protocols such as **TCP** and **UDP**.