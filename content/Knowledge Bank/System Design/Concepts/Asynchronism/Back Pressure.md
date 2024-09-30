---
title: Back Pressure
draft: false
tags:
  - async
---
Back pressure is a common issue that can occur to communication mechanisms like [[Message Queues]] and [[Task Queues]]. 

Back pressure takes place when the '*consumer*' of messages cannot keep up with the rate of messages produced by the '*producer*'. If this occurs, the queue begins to fill up and reach capacity which c an result in compromising the quality of the service.

## Strategies for Managing Back Pressure


1. Throttle the producer's ability to push messages to the queue e.g., establishing rate limits.

2. Increase capacity of the 'consumer', thus improving the rate of messages in the queue being processed.

3. Prioritize messages in the queue based on urgency.

