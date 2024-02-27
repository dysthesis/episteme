---
type: Topic note
tags:
  - rust
created: 2024-02-27 18:34
aliases:
  - slice
  - slices
  - Slice
---
A generalised form of [[Arrays|arrays]] and [[Vectors|vectors]] in [[Rust]]. It simply refers to some contiguous section in [[Memory|memory]], which applies for both.

If a slice is used as a parameter of a function, such as
```rust
fn some_function(x: &mut [i32]);
```
it cannot be resized (*e.g.* via `x.push(42)`) even if the variable passed in is a [[Vectors]].

- This is useful for supporting different architectures which may not support memory allocation

# Borrowing slices

Multiple  [[Borrowing|borrows]] of different sections of a [[Slices|slice]] cannot be created, even if they are mutually exclusive of each other. However, there exists 

---
# References
