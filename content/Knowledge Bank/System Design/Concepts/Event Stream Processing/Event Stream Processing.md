---
title: Event Stream Processing
draft: false
tags:
  - system-design
---
Event Stream Processing refers to processing a continuous stream of real-time events as they happen. These events can be anything from a user clicking a button on a website to sensor data from a device. The idea is to process these events immediately, enabling real-time insights or actions, like detecting fraud or updating a dashboard as new data arrives.

## Store Forward

**Store-Forward** is a technique where messages or events are stored temporarily before being forwarded to their destination. If the destination is not available (like a server being down), the events are stored and forwarded later. This ensures that no data is lost during downtime.

For example, a payment processing system might store transaction data if the database is temporarily unavailable and forward it once the system is back up.

## Pub/Sub

In the **Publish-Subscribe** pattern, there are publishers and subscribers. Publishers create events or messages and don’t worry about who receives them. Subscribers, on the other hand, subscribe to certain types of messages. Multiple subscribers can listen to the same event.

For example, in a stock trading system, a stock price update (publisher) is sent out, and various subscribers (traders, analysts, apps) receive that update simultaneously.

## Point-to-Point

In the **Point-to-Point** messaging model, messages are sent from one sender to one specific receiver. Unlike Pub/Sub, where many receivers might get the same message, here, the message is delivered to only one recipient.

For example, in a ticketing system, when a customer service agent picks up a ticket (event), it is removed from the queue and no other agent can access that specific ticket.