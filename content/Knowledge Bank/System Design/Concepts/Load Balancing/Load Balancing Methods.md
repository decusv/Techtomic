---
title: Load Balancing Methods
draft: false
tags:
  - system-design
  - availability
  - scalability
  - dns
---
## Load Balancers and Sticky Sessions

Load balancers play a critical role in horizontal scaling by distributing incoming traffic among backend servers. Software solutions like AWS Elastic Load Balancer or HAProxy, and more expensive hardware-based load balancers like those from Barracuda or Cisco, can efficiently manage this traffic. 

However, load balancing introduces challenges with session management. If a user is directed to one server, a subsequent request might route them to a different server, causing the session to be lost. To prevent this, **sticky sessions** use cookies to store a unique identifier in the user's browser. The load balancer can then use this information to route the user’s request to the same server, ensuring session continuity.

## Load Balance Across Dedicated Servers

Another horizontal scaling method involves using dedicated servers for specific tasks. In this setup, different types of content, such as HTML pages or media files, are served by separate servers. 

This segmentation improves performance by reducing the workload on any single server and allowing the infrastructure to be tailored for specific tasks, such as serving static content or handling dynamic requests.

## Round-Robin DNS Load Balancing

Round-robin [[Domain Name System (DNS)|DNS]] load balancing offers a simpler alternative to traditional load balancers by distributing requests across servers using [[Domain Name System (DNS)|DNS]] resolution. Each time a request is made, the DNS server returns a different backend server, cycling through available options in a round-robin fashion. 

While this avoids the need for a dedicated load balancer, it has several drawbacks. Some servers may receive more traffic than others, leading to imbalanced resource use. Additionally, caching efficiency is reduced, as identical queries may not return cached data from the same server. The **TTL (Time to Live)** settings in [[Domain Name System (DNS)|DNS]] also dictate how long a user’s request is routed to a particular server before being redirected to another. Though easy to implement, round-robin DNS is not as efficient as traditional load balancing in terms of traffic management and performance optimization.

This can also be done by having a DNS resolve to a single IP address belonging to a load balancer which in turn carries out round-robin when forwarding client requests to backend servers.

## Weighted Round Load Balancing

Weighted round-robin load balancing offers a version of round-robin where the load balancer has weights associated with each backend servers. Higher weights means that corresponding servers will be forwarded a proportionally higher number of incoming client requests.

## [[Domain Name System (DNS)|DNS]]-Level Load Balancing On Geography

[[Domain Name System (DNS)|DNS]]-level load balancing can distribute traffic based on the geographic location of requests. This method ensures that users are directed to servers that are closer to their location, improving response times and overall performance.

---

## Latency-based DNS Load Balancing

(?)

## Additional load balancing options

1. Load balance based on least server CPU usage.
2. Load balance based on least number of connections to the server.