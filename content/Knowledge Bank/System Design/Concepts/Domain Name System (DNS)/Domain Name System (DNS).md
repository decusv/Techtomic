---
title: Domain Name System (DNS)
draft: false
tags:
  - system-design
  - dns
---
![[Pasted image 20240918232251.png]]

A Domain Name System (DNS) translates a domain name such as [www.example.com](http://www.example.com/) to an IP address.

DNS operates hierarchically. At the top are **root servers** and **TLD (Top-Level Domain) servers**, which direct queries to **authoritative DNS servers** responsible for specific domain names. Your router or ISP typically provides information about which DNS resolver (lower-level DNS server) to contact for domain lookups.

When you perform a DNS lookup (e.g., typing a domain like `www.example.com`), your **router or device** contacts a **DNS resolver**, which is typically provided by your **ISP** or manually set by you. This DNS resolver is responsible for handling DNS queries and either resolves the domain from its cache or contacts the appropriate DNS servers (root, TLD, authoritative) to retrieve the IP address for the domain.

The propagation delay to all lower-level/local DNS servers and resolvers depends on the TTL. If the TTL is large, then those cached entries will last longer.

DNS results can also be cached by your browser or OS for a certain period of time, determined by the time to live (TTL).


---

## Disadvantages of DNS

- Accessing a DNS server introduces a slight delay, although this can be mitigated by caching.
- DNS Server management is done by governments, ISPs and large companies which makes it a centralized control point that can lead to censorship, surveillance or manipulation of DNS records.l
- DNS services can be placed under DDoS attacks, preventing users from accessing websites such as Twitter. as they weren't able to know their IP addresses.
