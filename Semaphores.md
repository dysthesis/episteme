---
type: Topic note
tags:
  - os
  - COMP3231
  - concurrency
created: 2024-02-23 15:41
aliases:
  - semaphore
  - semaphores
  - Semaphore
---
[[Semaphores]] are variables used to enforce [[Mutual exclusion|mutual exclusion]] for a [[Critical region|critical region]]. It describes the number of [[Process|processes]] that can enter a [[Critical region|critical region]] at the given time.[^1]

# Operations

These operations are 

## Wait / down (*proberen*)

Decrements the value of the [[Semaphores|semaphore]]

- The original Dutch name, *proberen*, means 'to test'.

## Signal / up (*verhogen*)

Increments the value of the [[Semaphores|semaphore]].

- The original Dutch name, *verhogen*, means to increment.

# Types

- [[Binary semaphore]]
- [[Counting semaphore]]

---
# References

[^1]: How does this differ from a [[Lock|lock variable]]?