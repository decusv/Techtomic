---
title: Stability Patterns
draft: false
tags:
  - stability
---
## Timeouts

Timeouts prevent systems from waiting indefinitely. 

For example, an application makes a request to a database. Instead of waiting for more than 4 seconds, it can choose to throw an error, or retry.

## Circuit Breaker

Circuit Breaker protects services from being overwhelmed by failures. If a service fails, no more requests are sent to the failing service. The system then waits for a given period before making a test request to do a health check before allowing regular traffic again.

## Let It Crash

Let it Crash focuses on fast recovery rather than error handling. It may be easier to focus on efficient restarting of a service rather than have complex error handling mechanisms.

## Fail Fast

Fail Fast ensures early detection of failures to prevent further damage. Fail early, rather than go through a long series of operations, thus reducing wasted resources and cascading system failures.

## Bulkheads

Bulkheads isolate failures to prevent system-wide issues. Taking microservice architecture as an example, if one service fails it shouldn't affect other services.

## Throttling / Rate limiting

Throttling controls the load on a system to prevent overload. Time based rate limits are applied that can span different scopes. For example, 200K per organization, and 20K API calls being allowed per account per hour.