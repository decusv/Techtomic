---
title: Brain Dump
draft: true
tags:
  - example-tag
---

Consistency
	- Client Side Eventual Consistency Levels
		- Casual consistency
		- Read-your-writes consistency
		- Session consistency
		- Monotonic read consistency
		- Monotonic write consistency
	- Server-side consistency
		- Number of nodes that store replicas of the data (N)
		- Number of replicas that need to acknowledge receipt of the update before the update c ompletes (W)
		- Number of replicas that are contacted when a data object is accessed through a read operation. (R)
			- What is strong consistency W + R > N
			- What is eventual consistency W + R <= N