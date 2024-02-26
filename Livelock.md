---
type: Topic note
tags: 
created: 2024-02-26 14:27
aliases:
  - livelocked
  - livelock
  - livelocks
  - Livelocks
  - Livelocked
---
Unlike [[Deadlock|deadlocks]], [[Livelock|livelocked]] [[Process|processes]] are alive, not blocked, but are unable to make any progress.

# Example

```C
void proc_A() {
	lock_acquire(&res_1);
	lock_acquire(&res_2);
	use_both_res();
	lock_release(&res_2);
	lock_release(&res_1);
}

void proc_B() {
	lock_acquire(&res_2);
	lock_acquire(&res_1);
	use_both_res();
	lock_release(&res_1);
	lock_release(&res_2);
}
```
Executing both of these function could result in both [[Process|processes]] acquiring one of the [[Lock|locks]] each, but never proceeding due to each of their inability to acquire the other [[Lock|lock]].  Notice that both of them are still running, but they are stuck.

A solution to this conundrum is to  have these functions release the [[Lock|lock]] that they are holding if they are unable to acquire the other [[Lock|lock]].
```C
void proc_A() {
	lock_acquire(&res_1);
	
	while(try_lock(&res_2) == FAIL) {
		lock_release(&res_1);
		wait_fixed_time();
		lock_acquire(&res_1);
	}
	
	use_both_res();
	
	lock_release(&res_2);
	lock_release(&res_1);
}

void proc_B() {
	lock_acquire(&res_2);
	
	while(try_lock(&res_1) == FAIL) {
		lock_release(&res_2);
		wait_fixed_time();
		lock_acquire(&res_2);
	}
	
	use_both_res();
	
	lock_release(&res_1);
	lock_release(&res_2);
}
```

---
# References
