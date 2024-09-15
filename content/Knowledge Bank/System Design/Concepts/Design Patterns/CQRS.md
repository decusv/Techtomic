---
title: CQRS
draft: false
tags:
  - scalability
  - acronym
---
Command Query Responsibility Segregation is a design pattern used in software architecture that separates reading and writing data into two distinct models:

**Command**: This part of the system is responsible for handling changes to the data, like updating, creating, or deleting records. These are called "commands" because they tell the system to perform an action that modifies the state of the system.

**Query**: This part is responsible for reading or fetching data. Queries do not change the state of the system; they just retrieve information.

### Why separate the two?

In a traditional system, the same model is used to both read and write data. With CQRS, you split them into separate paths because the needs for reading data are often different from the needs for writing data. For example, consider a read heavy application like a news website, where the volume of article reads is much higher than article writes.

### Benefits of CQRS

1. **Scalability**: Since reads and writes are separated, they can be scaled independently. For example, if a system has more read operations than write operations, you can optimize the query side for fast data retrieval.

2. **Performance Optimization**: You can optimize how data is stored and retrieved for each operation type. For instance, you might use different databases or structures for writing (e.g., optimized for fast inserts) and reading (e.g., optimized for fast lookups).

3. **Flexibility**: Each model can evolve independently, making it easier to add new features or make performance improvements over time.