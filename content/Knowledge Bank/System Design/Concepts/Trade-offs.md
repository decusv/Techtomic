---
title: Trade-offs
draft: false
tags:
  - system-design
---
## Performance vs. Scalability

Enhancing performance for individual users can sometimes lead to scalability issues. For example, using complex database queries, such as those involving multiple join operations, can be effective for a small number of users. However, as the user base grows and more of these complex queries are executed simultaneously, the database can become a bottleneck. This increased load can slow down the overall performance of the application.

## Redundancy vs. Scalability

To increase redundancy in a system, additional machines may be introduced. Redundancy is crucial for systems that require high availability, such as emergency services. If adding redundancy leads to performance degradation, it indicates a scalability problem. Back-up systems or components should enhance reliability without compromising performance, and ideally, should improve it.

