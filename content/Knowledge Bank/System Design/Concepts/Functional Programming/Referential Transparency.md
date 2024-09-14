---
title: Referential Transparency
draft: false
tags:
  - system-design
  - functional
---
Referential transparency is a concept in functional programming where an expression can be replaced with its value without changing the behaviour of the program. In other words, calling a function with the same input parameters will always produce the same output without causing any side effects.


## Referentially transparent function example in Java.

```java

int sum(int op1,int op2) {
	return op1+op2;
}

```

1. Same inputs will always provide the same outputs..
2. No state changes outside of its function scope implies no side effects.