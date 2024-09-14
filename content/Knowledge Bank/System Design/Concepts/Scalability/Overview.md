---
title: Scalability Overview
draft: false
tags:
  - scalability
  - system-design
---
Scalability refers to a system's ability to increase performance proportionally as resources are added, whether it's to serve more units of work or handle larger (or more complex) workloads.

Considering an example of a streaming service like Twitch, an example of scaling a service to handle more units of work could be compared to allowing more users to stream, whereas an example of processing larger units of work can be akin to being able to stream higher resolution (1080p compared to 4K) content.

In distributed systems, scalability also means ensuring redundancy without compromising performance, which improves reliability. This could be best explained as having a service that can handle a 100 users, as well as 10,000 without slowing down.

Scalability must be considered from the outset of system design. Algorithms that work under low load can become inefficient as demand or data grows. Additionally, scaling out introduces [[Heterogeneity|heterogeneity]]. To achieve good scalability, systems need to be designed with growth, redundancy, and heterogeneity in mind from the start.