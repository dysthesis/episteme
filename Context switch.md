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

- C must call Assembly to manipulate registers, as C can't do it itself. The reason why C cannot do what Assembly does, even though it is eventually compiled into Assembly anyways, is that C is meant to be platform independent, whereas register manipulation may differ due architecture. Therefore, these operations tend to be handled by the compiler in C.

# When does this happen

- If a system call blocks, or if `exit` is called, then the scheduler will perform a [[Context switch|context switch]], since nothing else can be done. 
- A *thread switch* can occur between any two CPU instructions, not just any two statements in the program. A statement may contain multiple instructions.

# Context switches must be transparent

The process of context switching must not be noticeable by processes, as the [[Operating system|operating system]] handles all the state saving.

- To a process, a thread switch will seem to be just like any other function call.

# In OS/161


---
# References
