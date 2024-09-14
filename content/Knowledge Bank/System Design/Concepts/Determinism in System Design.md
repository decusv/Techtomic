---
title: Determinism in System Design
draft: false
tags:
  - system-design
---
### Deterministic Systems

 Produce the same output for the same input every time. Design focuses on predictability and consistency, which is essential for applications requiring reliability.
 
 Examples include financial systems or safety-critical applications.

### Indeterministic Systems

Show some variability in behaviour but with recognizable patterns. The design aims to manage this variability while ensuring acceptable performance.

Examples include real-time video streaming systems like Twitch, where content delivery is subject to variability due to network conditions and server loads, but general patterns like average latency can be observed.

### Nondeterministic Systems

Have unpredictable outcomes even with the same input. The design focuses on robustness and handling a wide range of possible results, ideal for simulations or highly concurrent distributed systems.

Examples include concurrent player actions inside online games.