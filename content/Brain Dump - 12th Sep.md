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
								1. Use cookies to store a randomly generated value on the user's browser that is sent passed to the LB. The LB can then compare values with some DB to determine which server the request should be sent to for processing.
								2. Cookies have finite size.
									1. What are cookies in more detail?
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



1. PHP can use accelerators to cache data, speeding up performance as there's no need to re-compile/re-interpret PHP code every time a user requests PHP page data.
	1. if code changes, all cached data needs to be discarded.
	2. What are opcodes in the context of PHP?


1. Caching
		1. mySQL caching
		2. memcached -> Facebook
			1. Table stored in RAM for quick retrieval on something like a DB server.
			2. Memcached would have an expiry or priority in place to replace old un-used cached data.
			3. It's a key-value store.
		3. InnoDB
			1. Is a storage engine for DBs like MySQL and MariaDB
			1. row-level locking rather than table-level locking allowing for better concurrency.
			2. ACID Compliant transactions
				1. atomic e.g., no partial transactions
				2. consistent state before and after transaction
				3. changes made are safe even with a crash after the transaction
				4. transactions are isolated, which means multiple transactions can take place at any one time and mess each other up. Exact behaviour depends on DB isolation levels configured
					1. e.g., Serializable level ensures that all transactions on the same record are executed in sequence, eliminating all possibilities. however, this can slow down performance due to high probability of locking.


1. Replication (Master - Slave)
	1. Making automatic copies of something
	2. Master - Slave relationship for Databases
		1. Slaves get a copy of every row in the Master DB.
		2. In theory, the master and all slaves are identical.
		3. Provides redundancy in case of a master DB loss
		4. Read heavy applications can use slave DBs for improved concurrency e.g., load balance large volumes of read requests.


2. Replication (Master - Master)
	1. Load balance across both master DBs, propagate differences.
	2. Provides redundancy.


3. Load balancing + replication
		1. Things can still die in a Load Balancer -> Web servers -> LB -> MySQL slaves
		2. MySQL master copy can die
		3. Singular LBs can die.


4. Active - Active LB set-up (similar to Master - Master for DBs)
	1. Either one can receive requests from the internet
	2. Both of the active LBs are sending "heartbeat" packets to each other to inform if they are still both alive

5. Active - passive LB set-up
	1. if Active LB dies and then the passive LB will understand that through lack of "heartbeat" packets and promote itself to Active LB.
	2. Promotion means taking over the previous active LB's public IP address.


6. Partioning for data if servers reached capacitiy for vertical scaling. 
	1. Example with old Facebook having servers to store MIT, Harvard databases separately.
	2. Allowed to horizontally scale when new schools were introduced.
	3. Feature limitations arose when users from different schools would try to use features, hence why some features were limited to the respective school 'domains'.

7. Classify incoming requests to a web server into clusters to allow partitioning. Different DBs would get queried depending on characteristics of your requests e.g., geolocation of request.

8. Load balancing a the DNS level, load balance based on geography/geolocation of the request.


9. Avoid single points of failures
	1. no single LBs, servers, network switches, DBs


10. Security considerations in architectures
	1. Offload your security e.g., HTTPS/SSL to top-level LBs and drop down to your TCP/IP once within internal network.
	2. Firewall things to ensure only relevant ports are opened for the architecture components e.g., 80, 443, 22, 3306 (for db) ensures if one web server is compromised, it can only do things within intended scope e.g., 3306 but not 22 to other adjacent web server.