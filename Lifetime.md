---
type: Topic note
tags:
  - rust
created: 2024-02-27 18:49
---
```rust
fn some_function<'a, 'b, 'c>(x: &'a str, y: &'b str) -> &'c str
where
	'a: 'c // read: a outlives c
	'b: 'c // read: b outlives c
{
	// some stuff here
}
```
- Here, 'outlives' means that the lifetime is greater than or equal to the other.

If you declare that two variables have the same lifetime, but it isn't, [[Rust]] will temporarily shorten the lifetime of the longer variable to be the same as the shorter variable. Therefore, this works the same as the previous code:

```rust
fn some_function<'a>(x: &'a str, y: &'a str) -> &'a str {
	// some stuff here
}
```

---
# References
