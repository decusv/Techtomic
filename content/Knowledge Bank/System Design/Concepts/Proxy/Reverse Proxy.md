---
title: Reverse Proxy
draft: false
tags:
  - lb
---
A reverse proxy is a server that sits between client devices and backend servers, handling incoming client requests and forwarding them to one or more backend servers. It then also sends the backend server’s response back to the client. It provides a layer of abstraction (by acting as the public face to incoming client requests) and helps ensure smooth flow of network traffic.

The primary goal of a reverse proxy is to:

1. Hide the identity of backend servers.

3. Enhance Security -Ensure no information about backend servers is visible outside your internal network to ensure malicious users cannot access them directly.

5. Provide additional features like [[SSL Termination]] (much like a [[Load Balancer]] would), and [[Intelligent Compression]].



