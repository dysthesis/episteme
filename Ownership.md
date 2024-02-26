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
- [[Ownership]] only exists in [[Compile time|compile time]], used to deduce whether or not something will go wrong in the program.[^1]

# Transfer of ownership

It is always possible to deduce whether or not the [[Ownership|ownership]] of a value have been transferred on [[Compile time|compile time]] in [[Rust]].

# Opting out

The [[Copy]] type is used to opt out of the [[Ownership|ownership]] system.

---
# References

- [[COMP6991]]

[^1]: A more rigorous definition should be provided.