---
type: Topic note
tags:
  - os
  - concurrency
  - COMP3231
created: 2024-02-26 14:20
---
Preventing [[Deadlock|deadlocks]] involves fulfilling one of four conditions:

1. [[Mutual exclusion]]. In practice, this is not feasible, since some resources are not shareable.
2. [[Hold and wait]]
3. [[No preemption]]
4. [[Circular wait]]

There are several approaches to prevent [[Deadlock|deadlocks]]:

- [[Resource ordering]] is the most common technique to prevent [[Deadlock|deadlocks]] in practice. This tackles the [[Circular wait|circular wait]] condition.

---
# References
