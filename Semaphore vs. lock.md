---
type: Topic note
tags: 
created: 2024-02-25 10:42
---
A [[Lock|lock]] can only be unlocked by the [[Threads|thread]] currently holding it, whereas a [[Binary semaphore|binary semaphore]] can be signalled by anyone.

This means that there are virtually no differences between a [[Lock|lock]] and [[Binary semaphore|binary semaphore]] to enforce [[Mutual exclusion|mutual exclusion]].  Where [[Semaphores|semaphores]] truly shine over [[Lock|locks]] is in the context of  [[Synchronisation|synchronisation]], such as solving the [[Producer-consumer problem]].

---
# References

- [This COMP 3231 EdStem thread](https://edstem.org/au/courses/14865/discussion/1759032?answer=3933811)