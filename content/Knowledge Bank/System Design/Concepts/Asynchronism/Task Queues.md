---
title: Task Queues
draft: false
tags:
  - async
---
Task queues focus on executing and managing tasks, while [[Message Queues]] are concerned with messages being delivered between components of a system.

A task queue manages tasks by adding them to a queue for processing. It executes these tasks either in parallel or sequentially. Once a task is completed, the task queue provides the result or notifies the application/user.


## Example Implementations of Task Queues

1. Celery