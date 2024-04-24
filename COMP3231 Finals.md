# Sample exam 1

## Question 1

Determine whether the statements below are true or false.

1. A smaller page size leads to smaller page tables – False – need more entries because we have more pages
2. A smaller page size leads to more TLB misses – True – the fixed number of TLB entries cover less virtual memory.
3. A smaller page size leads to fewer page faults – True - In practice, initial faulting-in is usually less important than page faults generated once the application is up and running. Once the app is up and running, reducing the page size results in a more accurate determination of work set, which can be smaller, which requires less memory, which in-turn leads to a lower page fault rate.
4. A smaller page size reduces paging I/O throughput – True
5. Threads are cheaper to create than processes – True
6. Kernel-scheduled threads are cheaper to create than user-level threads – False
7. A blocking kernel-scheduled thread blocks all threads in the process – False. This is true for user-level threads
8. Threads are cheaper to context switch than processes – True – don’t have to save the address space
9. A blocking user-level thread blocks the process - True
10. Different user-level threads of the same process can have different scheduling priorities in kernel – False. User level threads appear as a single kernel thread.
11. All kernel-scheduled threads of a process share the same virtual address space – True
12. The optimal page replacement algorithm is the best choice in practice – False - it’s impossible to implement
13. The operating system is not responsible for resource allocation between competing processes – False – it is responsible for this
14. System calls do not change to privilege mode of the processor – False – we trap into the kernel so we do change the privilege mode
15. A scheduler favouring I/O-bound processes usually does not significantly delay the completion of CPU-bound processes – True – the I/O processes get the I/O and then yield the CPU again.

## Question 2

### Part A

#### Question

Consider a demand-paging system with a paging disk that has an average access and transfer time of 5 milliseconds for a single page. Addresses are translated through a page table in main memory, with an access time of 100 nanoseconds per memory access. Thus, each memory reference through the page table takes two accesses. The system has a 48-entry TLB to speed up memory accesses. Assume that 99% of memory accesses result in a TLB hit, and of the remaining 1%, 5 percent (or 0.05% of the total) cause page faults. What is the effective memory access time?

#### Answer 

.99 TLB hits, which needs only a single memory access (the actual one required)

.0095 TLB miss, one read from memory to get the page table entry to load TLB, then one read to read actual memory.

.0005 pagefault plus eventual read from memory plus something like one of the following (I'd take a few variations here)

1. A memory reference to update the page table
2. A memory reference to update the page table and a memory reference for the hardware to re-read the same entry to refill the TLB
3. Any reasonable scenario that results in valid page table and refilled TLB.

I'll assume option 2 for final answer, thus

.99 * 100ns + .0095 *2 * 100ns + .0005 (3 * 100ns + 5ms)

would be one answer I would accept.

### Part B

#### Question

Some versions of UNIX store the first part of each file in the same disk block as the inode. Discuss why this might be advantageous in practice

#### Answer

Many applications just read the first few bytes of a file, for instance to determine the file's type. If these bytes were not in the same disk block as the inode, then when an application asks to read the start of the file the disk would need to read the block with the inode sending this back to the file system code, which would find out the address of the block with the data, then send another request to the disk. Whereas if the first few bytes were in the block with the inode, then only one request to the disk is needed.

A significant fraction of files are small, thus a significant fraction of files can be stored in the inode entirely - thus reducing/avoiding the need to seek to the inode and then seek to the data - it is all in the inode.

## Question 3

### Part A

#### Question

Suppose that the head of a moving-head disk with 192 tracks, numbered 0 to 191, is currently serving a request at track 80 and has just finished a request at track 62. The queue of requests is kept in the FIFO order: 119, 58, 114, 28, 111, 55, 103, 30, 75. What is the total number of tracks traversed by head movements needed to satisfy these requests for the following disk-scheduling algorithms?

I) FCFS.
Ii) SSTF.
Iii) Elevator (SCAN).
Iv) Modified Elevator (C-SCAN).

#### Answer

I) FCFS order traversed: 119,58,114,28,111,55,103,30,75

Tracks traversed: 547

Ii) SSTF order traversed: 75,58,55,30,28,103,111,114,119

Tracks traversed: 143

Iii) SCAN/elevator order traversed: 103,111,114,119,75,58,55,30,28

Tracks traversed: 130

Iv) C-SCAN/modified-elevator order traversed: 103,111,114,119,28,30,55,58,75

Tracks traversed: 177.

### Part B

#### Question 

User-level threads packages generally implement cooperative scheduling. What is cooperative scheduling, and why is it the common method used to schedule user-level threads?

#### Answer 

Cooperative scheduling is a system of scheduling where the threads manually yield to allow other threads to have a go. It is commonly used because user-level code normally has no access to timers. That means there is no way to interrupt the thread when it runs too long, so it relies on cooperation from other threads to switch. Sometimes user level code has access to timers, but the units of time are not small enough to give the illusion of parallelism.

These are advantages of user level threads in general, not of cooperative threading for user level threads The scheduler can be optimized per application and context switches are faster than kernel level context switches.

## Question 4

### Question

Explain how a 32-bit virtual address is translated into a physical address on a system using a two-level page table and 4 kb pages. Your explanation, where it refers to parts of an address, must specifically state which bits of the address you are talking about. (Ignore any TLB). State any assumptions you make!

### Answer
- The first 10 bits (left most, 31:22) of the vaddr is the index into first-level page table. The index is used to load the corresponding entry in the first-level table which contains a pointer to the second level table.
- The next 10 bits (21:12) of the vaddr is combined with the pointer to index into the second level table to obtain the page table entry.
- The PTE contains a frame number which is combined with the final 12 bits of the vaddr (11:0) to gain the paddr.
- Assuming 10-bit/10-bit indexing of page table levels.

## Question 5

### Part A

#### Question 

Describe the difference between external and internal fragmentation. Indicate which of the two are most likely to be an issues on a) a simple memory memory mangement machine using base limit registers and static partitioning, and b) a similar machine using dynamic partitioning

#### Answer

Internal fragmentation is when there is the space inside an allocated region is wasted. External fragmentation is when the space outside an allocated region is wasted.

Internal fragmentation is more likely with static partitioning because the memory allocated is often rounded up to something larger than needed, or where the minimum unit of allocation is larger than required - e.g. disks are allocated in whole blocks. With dynamic partitioning, external fragmentation is more likely, because dynamic partitioning often leaves areas of the memory that are too small to place anything.

### Part B

#### Question

Describe the difference between a normal test-and-set spinlock and a read-before-test-and-set spinlock. Why would the latter be advantageous over the former on multiprocessor systems?

#### Answer

Test-and-Set Hardware locks the bus during the TSL instruction to prevent memory accesses by any other CPU Issue: Spinning on a lock requires bus locking which slows all other CPUs down

- Independent of whether other CPUs need a lock or not
- Causes bus contention

Caching does not help this test and set.

Hence to reduce bus contention.

- Read before TSL
    - Spin reading the lock variable waiting for it to change
    - When it does, use TSL to acquire the lock
- Allows lock to be shared read-only in all caches until its released
    - no bus traffic until actual release
- No race conditions, as acquisition is still with TSL.

## Question 6

### Question

Describe the four conditions required for deadlock to occur. Describe a common method for deadlock prevention that prevents one of the conditions occurring.

### Answer

1. Mutual exclusion
    - Each resource is either assigned to only one process or available.
2. Hold and wait
    - A process holding resources can request more.
3. No preemption
    - Requests granted cannot be taken away by the OS.
4. Circular wait
    - Each process in a set of at least 2 cannot proceed until it acquires a resource currently held by another process in the set.

One way to solve circular wait would be to set a requirement where they can only request resources in a pre-determined fixed order. All processes can only get and hold resources from a that order, this way, it's not possible for two processes to hold resources that the other needs.

# Sample exam 2

## Question 1

Determine whether the statements below are true or false.

1. The role of an operating systems is to present all the low level details of the computer hardware without any abstraction. **False, the role of the operating system is to abstract away low level details**
2. The operating system runs in the privileged mode of the microprocessor. **True (If the processor features a privileged mode, then the operation system will use it.)**
3. An application running in user-mode shares the same stack with the operating system when it runs in kernel mode.  **False, the kernel has a separate stack**
4. An operating system can enforce security by putting checks in the standard C-library. **False, the operating system is language independent and has no control over the C library which is user code**
5. Arguments to system calls are placed in registers (or on the stack) based on a mutually defined convention between the OS and user-level applications. **True, otherwise syscalls wouldn't work**
6. In the three-state process model, and common transition is from ready to blocked. **False, a process can go from blocked to ready but not the other way, it needs to be running to block.**
7. Co-operative (non-preemptive) multitasking can result in a non-responsive system if an application has an endless loop. **True, in co-operative multitasking, a thread must yield() in order for another thread to take over**
8. A threading library implementation at user-level (i.e. user-level threads) does not expose the concurrency available in the application to the operating system. **True, the kernel does not know about user-level threads**
9. Application threading supported by kernel implemented threads (i.e. kernel-level threads) can take advantage of multiple processors if available. **True, the OS can schedule kernel-level threads**
10. Applications (i.e. user-level code) can synchronise to avoid race conditions by disabling and enabling interrupts. **False, user-level applications can not disable interrupts as this requires privileged mode**
11. Semaphores can be used to implement mutual exclusion primitives. **True, if initialised to one**
12. Condition variables are used together with semaphores to manage blocking and waking within the semaphore. **False, condition variables are used in conjunction with _monitors_, or monitor-like lock use (e.g. in OS/161)**
13. Bankers algorithm can avoid deadlock if the maximum resource requirements of threads are known in advance. **True, although this is not realistic in practice**
14. Hold and wait is a practical deadlock prevention strategy.**False, in fact hold and wait is one of the four preconditions that leads to deadlock**
15. Sparse files save disk space by not storing the parts of the file that are not written to. **True, metadata representing the empty blocks can be stored instead**
16. The buffer cache improves write performance by buffering writes. Without extra application effort, the performance increase comes at the expense of reliability and consistency in the presence of failures. **True, even if the FS remains in a consistent (or recoverable) state, data is still lost**
17. Contiguous file allocation is an allocation strategy suitable for read-only media. **True, if the file increases in size, re-allocation will be required**
18. Chained (link-list) file allocation is desirable for file systems that support random-access workloads. **False, Random access in a linked list is very slow so not 'desirable'**
19. Best-fit memory allocation gives the best result in terms of memory fragmentation. **True, best fit results in the least external fragmentation.**
20. Swapping allows applications larger than physical memory to execute. **False, swapping _swaps_ the entire application, so it must fit entirely in memory to be present. There is some confusion between swapping versus paging (note linux/windows use the term "swapping" inaccurately). The following link happens to have a nice answer: https://stackoverflow.com/questions/4415254/difference-swapping-and-paging**
21. Overlays allow applications larger than physical memory to execute. **True, the application controls the overlays**
22. With appropriate language and OS support, segmentation can be used for bounds checking array access. **True, the OS checks that memory access falls within a segment's boundaries**
23. Virtual memory thrashing is where virtual memory translation happens too fast. **False, they are two unrelated concepts**
24. Optimal is the best practical page replacement algorithm. **False, it is not practical**
25. When choosing a victim for page replacement, a clean page is faster to replace than a dirty page. **True, it doesn't have to be written to disk**
26. Increasing the page size generally increases the working set size of an application. **True, the larger granularity of inclusion results in more virtual memory being included in the working set when only part of the page is actually accessed.**
27. Spatial locality contributes to VM system efficiency, but temporal locality does not. **False, the TLB hit rate is higher if entries are reused before they are replaced**
28. Adding more levels of I/O buffering always improves performance. **False, buffering adds memory copy overhead, which can be significant for fast I/O devices (e.g. multi gigabit networks).**
29. Shortest seek time first is a disk scheduling algorithm that is always fair. **False, Shortest Seek Time First can cause starvation**
30. Compared to polled I/O, Interrupt driven I/O is preferable when there is a significant delay between a device request and the device response. **True, otherwise CPU time is wasted polling**
31. Favouring CPU-bound applications over I/O-bound applications generally improves overall system performance. **False, a combination of I/O-bound and CPU-bound is optimal**
32. Rate-monotonic scheduling can always schedule a task set if the total utilisation is less or equals to 1. **False, but earliest-deadline-first does, see the example in lectures**
33. Round robin scheduling can be tuned by varying the time-slice length to trade-off responsiveness for decreased CPU overhead. **True.**
34. Spinlocks can never be more efficient to use than blocking locks, even on a multiprocessor machine. **False, they can avoid the overhead of context switching to scheduler then another process on a multiprocessor**
35. On a multiprocessor machine, a single ready queue provides automatic load balancing between CPUs. **True, ready processes are variable to all CPUs**
36. A read before test and set implementation of a spinlock just adds extra overhead to the lock implementation by adding a superfluous read. **False, reduces bus traffic since the test & set instructions are only applied when they might succeed.**
37. A multiprocessor machine only speeds up parallelisable workloads. **True.**
38. On a processor with a hardware-refilled TLB, the operating system is free to implement the most efficient page table data structure for the expected workload. **False, the PT structure must be readable by the hardware refilling the TLB**
39. Memory compaction can be performed transparently to an application on a machine with base and limit registers. **True, the whole segment can be copied higher or lower in physical memory**
40. Page sizes are always a power of 2. **True**

## Question 2

### Part A

#### Question
Consider a demand-paging system with a paging disk that has an average access and transfer time of 5 milliseconds for a single page. Addresses are translated through a page table in main memory, with an access time of 100 nanoseconds per memory access. Thus, each memory reference through the page table takes two accesses. The system has a 48-entry TLB to speed up memory accesses. Assume that 99% of memory accesses result in a TLB hit, and of the remaining 1%, 5 percent (or 0.05% of the total) cause page faults. What is the effective memory access time?

#### Answer
.99 TLB hits, which needs only a single memory access (the actual one required)

.0095 TLB miss, one read from memory to get the page table entry to load TLB, then one read to read actual memory.

.0005 pagefault plus eventual read from memory plus something like one of the following (I'd take a few variations here)

1. A memory reference to update the page table
2. A memory reference to update the page table and a memory reference for the hardware to re-read the same entry to refill the TLB
3. Any reasonable scenario that results in valid page table and refilled TLB.

I'll assume option 2 for final answer

thus

.99 * 100ns + .0095 *2 * 100ns + .0005 (3 * 100ns + 5ms)

would be one answer I would accept.

### Part B

#### Question 
Some versions of UNIX store the first part of each file in the same disk block as the inode. Discuss why this might be advantageous in practice.

#### Answer 
Many applications just read the first few bytes of a file, for instance to determine the file's type. If these bytes were not in the same disk block as the inode, then when an application asks to read the start of the file the disk would need to read the block with the inode sending this back to the file system code, which would find out the address of the block with the data, then send another request to the disk. Whereas if the first few bytes were in the block with the inode, then only one request to the disk is needed.

A significant fraction of files are small, thus a significant fraction of files can be stored in the inode entirely - thus reducing/avoiding the need to seek to the inode and then seek to the data - it is all in the inode.

### Part C

#### Question 
In most UNIX file systems, every file has an index block, called an inode, which is used to store information about the file as well as pointers to data blocks, as shown in the diagram below.

![[Screenshot 2024-04-25 at 08.08.34.png]]

Assume a block size of 2 kilobytes (2048 bytes) and 4-byte block numbers. What is the largest possible file size support by this filesystem?

#### Answer
Number of blocks addressable from one block = 2048 / 4 = 512

Direct blocks = 12

Single indirect blocks = 512

Double indirect blocks = 512**2

Triple indirect blocks = 512**3

Total blocks = 134480396

Max file size = 134480396 * 2KiB = 256.5GiB

## Question 3

### Part A

#### Question 
Suppose that the head of a moving-head disk with 192 tracks, numbered 0 to 191, is currently
Serving a request at track 80 and has just finished a request at track 62. The queue of requests is kept in the FIFO order: 119, 58, 114, 28, 111, 55, 103, 30, 75. What is the total number of tracks traversed by head movements needed to satisfy these requests for the following disk-scheduling algorithms?

I) FCFS.
Ii) SSTF.
Iii) Elevator (SCAN).
Iv) Modified Elevator (C-SCAN).

#### Answer 
i) 547
(ii) 143
(iii) (119 - 80) + (119 - 28) = 130
(iv) Count the traversal from high to low, (119 - 80) + (119 - 28) + (75 - 28) = 177

### Part B

#### Question 
User-level threads packages generally implement cooperative scheduling. What is cooperative scheduling, and why is it the common method used to schedule user-level threads?

