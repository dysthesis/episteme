---
type: Topic note
tags: 
created: 2024-02-26 14:47
---

> [!info] COMP3231
> [[COMP3231]] has a [[Deadlock detection|deadlock detector]] built into the assignments, called `hangman`. This is done via graph traversal.

[[Deadlock|Deadlocks]] can be detected by modelling the usage of resource with a [[Graph|graph]]. If a [[Cycle|cycle]] exists, then there is a [[Deadlock|deadlock]].  

-  [[Deadlock detection is not free]]. Therefore, it is more efficient to prevent it in the first place.
-  [[Deadlock detection]] can significantly slow down the program by orders of magnitudes.
- It is also possible to perform [[Deadlock detection for resources with multiple units|deadlock detection for resources with multiple units]]

---
# References
