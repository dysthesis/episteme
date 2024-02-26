---
type: Topic note
tags: 
created: 2024-02-26 15:16
---
Once a [[Deadlock detection|deadlock is detected]], it might be possible to [[Recovery from deadlock|recover from it]] by a number of methods.

# Preemption

It may be possible to take a resource from some other [[Process|process]]

# Rollback

1. Create a checkpoint of the current state. This checkpoint is an image of the current state.
2. In the future, if a [[Deadlock|deadlock]] (or even any other errors) occurs, roll back to a previous working checkpoint.

An example of this is the auto-save feature available in most modern programs.

# Killing processes

This is the brute force approach: simply **kill one of the [[Process|processes]] stuck in the [[Deadlock|deadlock]] cycle.** This is what the [[Out-of-memory killer|OOMK in Linux]] does.

---
# References
