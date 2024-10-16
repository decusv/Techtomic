---
title: Load Balancer
draft: false
tags:
  - lb
---
![[Pasted image 20240924233114.png]]

A load balancer (LB) is a component that distributes incoming client requests to computing resources such as application servers and databases. The LB forwards the requests, and also forwards the responses from the resources back to the client.

## Advantages of Load Balancers 

- LBs are good at ensuring requests are not pushed to unhealthy/inactive resources
- LBs ensure that the resources are not overloaded with requests.
- They help with eliminating a single point of failure from your system architecture.
-  Perform **[[SSL termination]]**.
- Allows for simplifying management of X.509 certificates as they can be managed on LBs instead of the servers themselves.
- Can help ensuring session persistence/[[Load Balancing Methods#Load Balancers and Sticky Sessions|sticky sessions]].

## Disadvantages of Load Balancers

- Can become a bottleneck if the amount of resources available is not sufficient.
- Will result in a single point of failure unless more load balancers are introduced.
- Increases architecture complexity by introducing load balancer(s).


LBs can be implemented via software like HAProxy, or via hardware which is more expensive.

---

