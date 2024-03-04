---
id: Simple model of CPU computation
aliases: []
tags: []
created: 2024-03-04 15:16
type: Topic note
---


- [[Stack pointer]]
- [[Status register]]
- [[General purpose registers]]

An embedded microprocessor looks like this.

# Privilege

In general, processes are separated into several levels of privilege. This typically consists of the [[User-mode|user-mode]] and [[Kernel-mode|kernel-mode]], though it may contain more or less. For example, `x66_64` CPUs consists of four rings of privilege.

---
# References
