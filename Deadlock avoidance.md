---
type: Topic note
tags: 
created: 2024-02-26 15:24
---
[[Deadlock|Deadlocks]] can be avoided given sufficient information about the maximum number of resources required by the [[Process|processes]] in advance.

![[Pasted image 20240226152639.png|A plot of two processes making progress.]]

The shaded region of this diagram represents a [[Deadlock|deadlock]] condition. Observe that at the state $t$, allowing any more progress to [[Process|process]] B will result in [[Deadlock|deadlock]]. Therefore, a decision can be made to halt resource allocation to [[Process|process]] B and allow process A to progress instead until $l_4$[^1].

---
# References

[^1]: How is the [[Deadlock|deadlock]] region of the graph determined? How exactly is progress mentioned? What do the $l_{i}\;\forall\; i\in\mathbb Z, 1 < i < 9$  that dot the axes mean? The whole diagram is confusing.