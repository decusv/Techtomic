---
title: Vertical Scaling
draft: false
tags:
  - system-design
  - scalability
---
## Vertical Scaling

Vertical scaling involves upgrading the resources of a single machine, such as increasing CPU power or disk space, to handle more traffic. This approach can provide a temporary solution when a server is running low on resources. However, it is not a complete or long-term solution, as there is a limit to how much a single machine can be upgraded. Budget constraints or the physical limits of available hardware often cap the effectiveness of vertical scaling.

## Horizontal Scaling

Horizontal scaling addresses the limitations of vertical scaling by using multiple servers instead of relying on a single machine. Rather than upgrading one powerful server, traffic is distributed across a network of less powerful servers. This approach is more scalable and can handle greater loads as traffic increases. Horizontal scaling typically requires load balancers to distribute incoming traffic to various servers, ensuring that no single machine is overwhelmed.