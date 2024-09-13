---
title: Brain Dump
draft: true
tags:
  - example-tag
---
Reference : https://web.archive.org/web/20220530193911/https://www.lecloud.net/post/7295452622/scalability-for-dummies-part-1-clones

- Users should always get the same results back, independent from what application server they may have landed on.
	- Implies same codebase should be run on the application servers
	- Servers should not store any user-related data n local disc or memory/RAM.
		- Profile pictures
		- Sessions
			- Should be stored in a centralized data store which is accessible by all of the application servers.
				- An external DB or an external persistent cache e.g., Redis
					- External persistence cache would perform better than an external DB.
						- External implies not hosted on one of the application servers, but rather in a nearby location to the application servers.


- Software like Capistrano can be used to remotely deploy code to production e.g., when you have multiple web servers
	- To be able to deploy code consistently, you can create either docker images for your applications, or entire images for servers to allow for consistent deployment of the same code.


---

Reference : https://web.archive.org/web/20220602114024/https://www.lecloud.net/post/7994751381/scalability-for-dummies-part-2-database

