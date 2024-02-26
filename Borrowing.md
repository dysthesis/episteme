---
type: Topic note
tags: 
created: 2024-02-26 18:52
---
Temporary transfer of [[Ownership|ownership]] in [[Rust]].

- The two types of borrows have roots in the [[Rust#Shared `xor` mutable|shared xor mutable]] principle of [[Rust]].
# Shared borrows

Multiple shared borrows can be distributed at the same time. However, shared borrows are immutable, read only.

# Exclusive borrows

Only one borrow can be distributed.

---
# References
