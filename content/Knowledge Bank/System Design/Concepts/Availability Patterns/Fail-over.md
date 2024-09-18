---
title: Fail-over
draft: false
tags:
  - availability
---
Fail-over is an availability pattern where a backup system automatically takes over when the primary system fails. It ensures system uptime and availability even in case of hardware or software failure.

**Active-passive failover**: One system is active, and the other is on standby. This can be a "cold" standby where the passive system needs to start-up, and an "hot" standby where the passive server is already up and running.

**Active-active failover**: Both systems are active, sharing the load, and can take over if one fails. If both are public facing, then the DNS server will need to know both public IPs.  If the servers are internal facing, the application would need to be aware there are two servers available for handling requests, such that it can programmatically distribute the load between the two.

In both of the above cases, systems send 'heartbeat' signals to each other to imply the system being alive. If one system no longer sends the signal, the other system is alive.

### Disadvantages of failover

- Fail-over adds more hardware and additional complexity.
- There is a potential for loss of data if the active system fails before any newly written data can be replicated to the passive.