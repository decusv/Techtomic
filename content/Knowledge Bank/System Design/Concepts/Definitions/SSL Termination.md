---
title: SSL Termination
draft: false
tags:
  - definition
---
**SSL termination** is the process of decrypting **SSL/TLS-encrypted** traffic at an intermediary point such as a [[Load Balancer]] or a [[Reverse Proxy|Reverse Proxy]] before it reaches its final destination, typically the application server. In essence, SSL termination offloads the resource-intensive task of encryption and decryption from the backend servers, improving their performance.