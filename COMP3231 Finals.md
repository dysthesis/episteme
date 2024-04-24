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

### Question

#### Part A

Consider a demand-paging system with a paging disk that has an average access and transfer time of 5 milliseconds for a single page. Addresses are translated through a page table in main memory, with an access time of 100 nanoseconds per memory access. Thus, each memory reference through the page table takes two accesses. The system has a 48-entry TLB to speed up memory accesses. Assume that 99% of memory accesses result in a TLB hit, and of the remaining 1%, 5 percent (or 0.05% of the total) cause page faults. What is the effective memory access time?

#### Part B

Some versions of UNIX store the first part of each file in the same disk block as the inode. Discuss why this might be advantageous in practice

### Answer

#### Part A

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

#### Part B

Many applications just read the first few bytes of a file, for instance to determine the file's type. If these bytes were not in the same disk block as the inode, then when an application asks to read the start of the file the disk would need to read the block with the inode sending this back to the file system code, which would find out the address of the block with the data, then send another request to the disk. Whereas if the first few bytes were in the block with the inode, then only one request to the disk is needed. 

A significant fraction of files are small, thus a significant fraction of files can be stored in the inode entirely - thus reducing/avoiding the need to seek to the inode and then seek to the data - it is all in the inode.

## Question 3

### Question 

#### Part A

Suppose that the head of a moving-head disk with 192 tracks, numbered 0 to 191, is currently serving a request at track 80 and has just finished a request at track 62. The queue of requests is kept in the FIFO order: 119, 58, 114, 28, 111, 55, 103, 30, 75. What is the total number of tracks traversed by head movements needed to satisfy these requests for the following disk-scheduling algorithms?

I) FCFS.
Ii) SSTF.
Iii) Elevator (SCAN).
Iv) Modified Elevator (C-SCAN).

#### Part B