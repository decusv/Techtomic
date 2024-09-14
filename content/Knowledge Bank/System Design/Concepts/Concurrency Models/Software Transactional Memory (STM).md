---
title: Software Transactional Memory (STM)
draft: false
tags:
  - concurrency
---
In STM, each thread or process makes changes to memory in a separate transaction. STM systems check if multiple transactions interfere with each other i.e., conflicts before finalizing the changes.  

If conflicts are found, then changes can be rolled back to keep everything consistent. If no conflicts are found, then changes can be committed.