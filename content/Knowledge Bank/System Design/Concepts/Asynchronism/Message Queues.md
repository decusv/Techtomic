---
title: Message Queues
draft: false
tags:
  - async
---
A message queue is a mechanism through which components and services part of your system can asynchronously communicate with each other. Message queues can receive, hold and deliver messages.  Message queues are best suited when an operation is too expensive or too slow to perform synchronously i.e., where we wait for for the result of the operation. 

In some cases, superficial processing could be carried out to create the illusion that the task is complete, even if the is still being processed e.g., visibly publishing tweet to your timeline before it is actually shared with your followers.

---

## Typical Flow Of A Message Queue

1. Application publishes a job to the queue.
2. User is notified of the job's status e.g., a step builder's workflow status like Power Automate.
3. Once resources are available, a 'worker' picks up a job from the queue, processes it, and returns a signal that the job is complete.

## Advantages of Message Queues

- User is not blocked by the process because the job can be processed 'in the background'.

## Example Implementations of Message Queues

1. RabbitMQ
2. Amazon SQS
3. Redis 