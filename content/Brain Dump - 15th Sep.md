---
title: Brain Dump
draft: true
tags:
  - example-tag
---

1. Scalability patterns
	1. Behavior
	2. Event-Driven Architecture
		1. Domain Events
	3. Compute Grids
		1. Parallel execution
			1. Divide and Conquer
			2. MapReduce - Master Worker
		2. Products like Google MapReduce, Hadoop

1. What is CQRS


1. What is Event Stream Prrocessing?
	1. Store-Forward
	2. Messaging
		1. RabbitMQ
	3. Pub Sub
	4. Point To Point
	5. Request Reply


3. Event Sourcing
	1. Every state change is materialized into an event
	2. Events are sent to an EventProcessor
		1. Events stored in Event Log
		2. Log can be replayed.

1. Load balancing
	1. Reverse proxy?
	2. Random allocation
	3. Round Robin Allocation
	4. Weighted Allocation
	5. Dynamic load balancing 
		1. Least connections
		2. Least Server CPU


Stability patterns
1. Timeouts
2. Circuit breaker
3. Let it crash
4. Fail fast
5. Bulkheads
6. Steady State
7. Throttling


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