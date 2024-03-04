---
id: Context switch
aliases:
  - context switch
tags:
  - concurrency
created: 2024-03-04 14:29
type: Topic note
---

The process of switching between [[Threads|threads]] or [[Process|processes]]. This involves saving the state of a thread before switching away from it and restoring the state when switching back to it.

# When does this happen

- If a system call blocks, or if `exit` is called, then the scheduler will perform a [[Context switch|context switch]], since nothing else can be done. 
- A thread switch can occur between any two CPU instructions, not just any two statements in the program. A statement may contain multiple instructions.

# Context switches must be transparent

The process of context switching must not be noticeable by processes, as the [[Operating system|operating system]] handles all the state saving.

- To a process, a thread switch will seem to be just like any other function call.

[[Trapframe]]

---
# References
