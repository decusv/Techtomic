---
title: Load Balancing Setups
draft: false
tags:
  - system-design
  - availability
  - scalability
---
### Active-Active [[Load Balancing Methods|Load Balancer]] Setup

- **Overview**: Both load balancers handle requests and monitor each other.
- **Details**:
    - Each LB receives requests from the internet.
    - "Heartbeat" packets are exchanged to confirm that both are operational.

### Active-Passive [[Load Balancing Methods|Load Balancer]] Setup

- **Overview**: One LB is active, and the other is passive, ready to take over if needed.
- **Details**:
    - Passive LB promotes itself to active status upon detecting the active LB's failure.
    - Takes over the public IP address of the failed active LB.