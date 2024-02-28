---
type: Assignment
course: COMP3231
tags:
  - assignment
created: 2024-02-27 09:53
---
# Overview

> [!important] Due date
> This assignment is due on **March 8, 16:00**

This assignment is about solving [[Synchronisation|synchronisation]] problems with the [[OS/161]] kernel.

## Setting up

### Clone the source repository
```bash
git clone https://<zID>@nw-syd-gitlab.cseunsw.tech/COMP3231/24T1/z8888888-asst1.git asst1-src
```

### Configure the source 
```bash
cd asst1-src
./configure && bmake && bmake install
```

### Configure the kernel 
```bash
cd asst1-src/kern/conf
./config ASST1
```

You should now see an ASST1 directory in the kern/compile directory.



---
# Specifications

## Objective

## Coded solution (70%)

### Part 1 - The Concurrent Counter problem (~20%)

> [!summary] Overview
> Correctly create, destroy, increment, and decrement [[Synchronisation|synchronised]] counters. 


### Part 2 - The Bounded-Buffer Producer/Consumer problem (~30%)

> [!summary] Overview
> Coordinate producer and consumer [[Threads|threads]] to avoid [[Race conditions|race conditions]], overflow, and underflow of a fixed-size buffer.


### Part 3- The CDROM (~50%)

> [!summary] Overview
> Complete and synchronize the `cdrom_read` and `cdrom_handler` functions according to given requirements and constraints.


## Video explanation (30%)

Create a 1-2 minute video explaining the solutions to the coding problems.

- Address concurrency problems
- Explain how the solutions solves them effectively

## Grading criteria

> [!hint] Weight
> This assignment is worth **20 marks out of 100** of the overall course grade.

$$
\text{Mark} = 20\cdot\left(\frac{\text{Coded solution marks}}{14}\right)^{0.7} \cdot\left(\frac{\text{Video marks}}{6}\right)^{0.3}
$$

---
# Notes

> [!info]+ About this section 
> This section should contain miscellaneous notes on the assignment.
