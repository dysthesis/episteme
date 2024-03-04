---
id: System calls
aliases: []
tags: []
created: 2024-03-04 14:54
type: Topic note
---

System calls allow for a [[User-mode|user-mode]] application to perform [[Kernel-mode|kernel-mode]] operations. They can be thought of as special function call.

# User-to-kernel

# Kernel-to-user

Return from [[Kernel-mode|privileged-mode]] back to the application.

# Why is this necessary?

To prevent processes from arbitrarily jumping to restricted regions of code, bypassing any checks, *e.g.* to prevent a [[User-mode|user-mode]] application from reading `/etc/passwd`.

# MIPS

## Exception management

### `c0_cause`

Returns the cause for why the operating system was invoked (*i.e.* to find out what really went wrong).


### `c0_status`

Returns the state of the microprocessor itself (what mode it was in, etc.)

Whenever an exception occurs, the bits mode to the left of the registers.

#### Kernel/User (KU)

Determines whether or not we were running in kernel mode.

- 0 means kernel mode
- 1 means user mode

#### Interrupts enabled (IE)

Determines whether or not interrupts are enabled.

- 0  means all interrupts are masked
- 1 means interrupts are enabled.

#### Current, previous, old (c, p, o)

### `c0_epc`

`epc` stands for exception program counter, which is returns the address of the instruction that was about to be executed before an interrupt.

---
# References
