---
type: Topic note
tags: 
created: 2024-02-26 15:41
---

1. Look at the difference between the total existing resources and the currently available resources
2. Iterate through all the [[Process|processes]]
	1. Find the difference between the maximum resources demanded and the currently held resources.
	2. If this difference is satisfiable by the currently available resources, the process can execute until completion.
	3. Once the [[Process]] completes, the resources it holds should be added back to the available resources.
	4. Rinse and repeat.

If there is an order of execution that does not occur in a deadlock, this is a [[Safe and unsafe states|safe state]].

Not commonly used in practice, as it is sometimes impossible to know what the maximum amount of resources a [[Process|process]] will require is.

---
# References
