---
id: Semaphores
aliases:
  - semaphore
  - semaphores
  - Semaphore
tags:
  - os
  - COMP3231
  - concurrency
created: 2024-02-23 15:41
type: Topic note
---

[[Semaphores]] are variables used to enforce [[Mutual exclusion|mutual exclusion]] for a [[Critical region|critical region]]. It describes the number of [[Process|processes]] that can enter a [[Critical region|critical region]] at the given time.[^1]

# Operations

[[Modern Operating Systems - Andrew S Tanenbaum Herbert Bos#^hu7t11we8k|These operations are atomic]], uninterruptible during their execution, [[Atomic actions alleviates concurrency issues|in order to prevent concurrency issues]] within them.

## Wait / down (_proberen_)

Decrements the value of the [[Semaphores|semaphore]]

- The original Dutch name, _proberen_, means 'to test'.

## Signal / up (_verhogen_)

Increments the value of the [[Semaphores|semaphore]].

- The original Dutch name, _verhogen_, means to increment.

# Types

- [[Binary semaphore]]
- [[Counting semaphore]]

---

# References

- [[Modern Operating Systems - Andrew S Tanenbaum Herbert Bos|Modern Operating Systems]]
- [[COMP3231]]

[^1]: How does this differ from a [[Lock|lock variable]]?
