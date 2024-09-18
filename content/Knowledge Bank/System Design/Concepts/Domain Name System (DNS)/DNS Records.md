---
title: DNS Records
draft: false
tags:
  - dns
  - system-design
---
**NS record (name server)** 

Specifies the authoritative DNS servers for your domain/subdomain.

`example.com.   86400   IN   NS   ns1.exampledns.com`

- **example.com**: The domain.
- **86400**: The TTL (Time to Live), the time in seconds the record is valid (86400 = 24 hours).
- **IN**: Internet record type. (?)
- **NS**: Indicates it’s a name server record. (?)
- **ns1.exampledns.com**: The DNS server for the domain.

---


**MX record (mail exchange)** 

Specifies which mail servers should receive email for the domain.

`example.com. 3600 IN MX 10 mail1.example.com.
`example.com. 3600 IN MX 20 mail2.example.com.`

- **example.com**: The domain.
- **3600**: TTL, valid for 1 hour.
- **MX**: Mail Exchange record.
- **10** and **20**: The priority values (lower numbers indicate higher priority, so `mail1.example.com` is preferred over `mail2.example.com`).
- **mail1.example.com**: The mail server that accepts emails for the domain.

---

**A record (address)** 

Maps a domain name to an IPv4 IP address.

`www.example.com.   600   IN   A   192.0.2.1`

- **[www.example.com](http://www.example.com)**: The domain name.
- **600**: TTL, valid for 10 minutes.
- **A**: Indicates an address record.
- **192.0.2.1**: The IP address that `www.example.com` points to.

---

**CNAME (canonical)** 

Points a domain name to another domain name (often used for aliases).

`blog.example.com. 3600 IN CNAME www.example.com.`

- **blog.example.com**: The alias or subdomain.
- **3600**: TTL, valid for 1 hour.
- **CNAME**: Canonical Name record.
- **[www.example.com](http://www.example.com)**: The target domain name. When someone visits `blog.example.com`, it will resolve to the same address as `www.example.com`.
