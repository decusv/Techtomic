---
title: Brain Dump
draft: true
tags:
  - example-tag
---

Ref : https://www.youtube.com/watch?v=-W9F__D3oY4
Title : CS75 Harvard Lecture

1. How do you go about scaling to allow your website to handle more users?
	1. Vertical Scaling
		1. Running low on CPU cycles, disk space -> Get more.
		2. Not a 'complete' solution.
			1. Only so much you can do to upgrade a single machine in either budget or in component capability.
	2. Horizontal Scaling
		1. Accepting the fact there's a ceiling in vertical scaling.
		2. Instead of few powerful machines, get more of less powerful and potentially older servers.
		3. Distribute incoming requests coming to a server.
			1. Use load balancers. Sofware -> AWS Elastic Load Balancer, HAProxy. Hardware -> load balancers by Barrarcuda, Cisco, Citrix which are much more expensive.
				1. Incoming traffic is distributed (balanced) across the various backend servers. 
					1. #1 - Let DNS resolve to a load balancer which has a public IP address. Load balancer returns one of the private IP addresses belonging to one of the servers. Where all servers are identical.
						1. Load balancer can query the servers with the client request, get response and pass it back to the client without revealing. 
						2. Problem arises with sessions if a machine has a session with a server, but gets redirected by load balancer to a different back-end server upon refresh, thus losing the session and thus requiring you to login again.
						3. STICKY SESSIONS - How can you ensure sessions don't get ended when a user refreshes the page?
							
					2. #2 -  There can be dedicated servers e.g., one for HTML, one for media files, etc. 
					3. # 3 - Load Balancing with BIND
						1. Instead of DNS server resolving to a public IP address of a load balancer, DNS server can go in round-robin to return different backend servers (where all servers are identical). Can avoid a need for load balancer.
							1. One of the servers can get a lot more heavy use compared to others, thus utilizing one server a lot more than others.
							2. Inefficient because round-robin doesn't allow for the same server to returned cached information in identical queries made by a user.
							3. DNS servers have configured rules for TTLs i.e., time to live, before the same user's requests can be routed elsewhere by the DNS server.


1. RAID
		1.RAID0
			1. Two hard drives of identical size
				1. Uses concept of 'striping' data, where the data being written to hard drives is partitioned across both, thus doubling the rate at which data can be written to a hard drive.
		1. RAID1
			1. Two hard drives of identical size
				1. Data is mirrored across both hard drives. Small overhead, but data is written in parallel. 
					1. Provides redundancy
		2. RAID10 
			1. Combination of both RAID0 and RAID1 where data is both mirrored and striped across four identical hard drives.
		3. RAID5
			1. Version of RAID1 
				1. Multiple drives, but only a fifth of the hard drives is used for redundancy. 
		4. RAID6
			1.Similar to RAID5, requires an extra hard drive compared to RAID5, but provides additional redundancy.