---
title: Service Discovery
draft: false
tags:
  - microservice
---
Service discovery is a process used in [[Microservice| microservice]] architecture to allow the various services to find and communicate with each other. 

Example tools used for this are Consul, Etcd. These essentially act as a key-value store for microservices. Another tool is Zookeper, that works similarly to the other two.

## How It Works


1. Service Registration - When a service starts, it communicates to the Service Discovery tool its address and port.

2. When a service wants to connect to another service, it reaches out to the Service Discovery tool with the service's name to get its IP and port.

3. Services typically provide a health endpoint e.g., `/health` to allow the Service Discovery tool to perform health checks on it.

