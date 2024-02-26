---
type: Topic note
tags:
  - rust
created: 2024-02-26 18:09
aliases:
  - ownership
---

Reading data [[Concurrency|concurrently]] will not cause any issues, but writing/mutating it [[Concurrency|concurrently]] with another read/write operation will. 

- [[Ownership]] is useful to track [[Resources|resources]] (files, memory, etc.)

# Opting out

The [[Copy]] type is used to opt out of the [[Ownership|ownership]] system.

---
# References

- [[COMP6991]]