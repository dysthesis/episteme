---
type: Topic note
tags:
  - os
  - concurrency
  - COMP3231
created: 2024-02-26 14:54
---
Resources often have multiple units, such as RAM or blocks on a hard drive.

# Data structures

There are several data structures that are required to be able to accurately model resource allocation and [[Deadlock detection|detect deadlocks]].

The first is a vector of all the resources in existence, which can be defined as:
$$
\mathbf E = \begin{pmatrix}E_{1}\\ E_{2} \\ E_{3}\\ \vdots \\E_m\end{pmatrix}
$$


# Algorithm

1. Look for an unmarked process $P_i$, for which the $i^\text{th}$ row of $R$ is less than or equal to $A$. Intuitively, $P_i$ is process which have yet to be completed.
2. 

$$
\sum^n_{i=1}C_{ij} +A_j=E_j
$$

# Example

![[Pasted image 20240226151302.png]]
**Note.** Convert this into LaTeX later.

1. Given the current available resources ($A$), none of the requests (rows of $R$) can be satisfied.

---
# References
