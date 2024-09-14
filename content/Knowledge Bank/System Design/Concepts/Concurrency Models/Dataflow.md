---
title: Dataflow
draft: false
tags:
  - concurrency
---
In dataflow concurrency, execution of operations is based on data dependencies.  Operations are executed when the required data become available. This creates a natural order of execution based on data dependencies. 

Thiis model can simplify parallelism by automatically managing dependencies and the execution order of operations.