# Operating Systems Interview Preparation for Freshers

## 1. OS Fundamentals — High Priority

1. What is an operating system, and what are its main responsibilities?
2. What is a kernel, and how is it different from an operating system?
3. What is the difference between user mode and kernel mode?
4. What is a system call, and why do applications need system calls?
5. How is a system call different from a regular function call?
6. What is the difference between an interrupt and an exception?
7. How do multiprogramming, multitasking, multiprocessing, and multithreading differ?
8. What happens at the OS level when an application requests data from a file?

## 2. Processes and Threads — High Priority

1. What is a process, and how is it different from a program?
2. What is a thread, and how is it different from a process?
3. What are the common states of a process, and what causes transitions between them?
4. What is a Process Control Block (PCB), and what information does it contain?
5. Which resources do threads within the same process share, and which resources are private to each thread?
6. What is context switching, and why does it introduce overhead?
7. How does switching between processes differ from switching between threads in the same process?
8. What is the difference between concurrency and parallelism?
9. How do user-level threads differ from kernel-level threads?
10. Why might an application use multiple processes instead of multiple threads?
11. Can a multithreaded application benefit from running on a single-core CPU?
12. What can happen to other threads in a process if one thread causes an invalid memory access?

## 3. CPU Scheduling — High Priority

1. What is CPU scheduling, and why is it necessary?
2. What is the difference between preemptive and non-preemptive scheduling?
3. What are arrival time, burst time, completion time, turnaround time, waiting time, and response time?
4. How do First-Come, First-Served (FCFS), Shortest Job First (SJF), Shortest Remaining Time First (SRTF), and Round Robin scheduling work?
5. Given arrival times and CPU burst times, how would you draw a scheduling Gantt chart and calculate average waiting and turnaround times?
6. How does the time quantum affect responsiveness and context-switch overhead in Round Robin scheduling?
7. What is the convoy effect, and which scheduling algorithm is commonly associated with it?
8. What is starvation, and how can aging help prevent it?
9. How do CPU-bound and I/O-bound processes differ?
10. Which scheduling characteristics are important for an interactive application compared with a batch-processing system?

## 4. Synchronization and Race Conditions — High Priority

1. What is a race condition, and when can it occur?
2. What is a critical section?
3. What are mutual exclusion, progress, and bounded waiting?
4. Why can two threads incrementing the same shared counter produce an incorrect result?
5. What is a mutex, and how does it protect shared data?
6. What is a semaphore, and how do binary and counting semaphores differ?
7. How does a mutex differ from a binary semaphore, particularly regarding ownership?
8. What is the difference between a spinlock and a blocking lock?
9. What is an atomic operation, and why is it useful in concurrent programs?
10. How would you coordinate a producer and a consumer sharing a bounded buffer?
11. What is the readers–writers problem?
12. What can happen if a thread fails to release a lock?

## 5. Deadlocks — High Priority

1. What is a deadlock? Can you describe a simple example involving two locks?
2. What are the four necessary conditions for a deadlock?
3. How does deadlock differ from starvation and livelock?
4. What is the difference between deadlock prevention, avoidance, detection, and recovery?
5. How can acquiring locks in a consistent order prevent deadlocks?
6. What are safe and unsafe states? Does an unsafe state necessarily mean a deadlock already exists?
7. What is the basic idea behind the Banker’s algorithm?
8. Given a small allocation, maximum-demand, and available-resource table, how would you determine whether a safe sequence exists?
9. How can an operating system recover after detecting a deadlock?

## 6. Memory Management Fundamentals — High Priority

1. Why does an operating system need memory management?
2. What is the difference between a logical or virtual address and a physical address?
3. What is the role of the Memory Management Unit (MMU)?
4. How do stack memory and heap memory differ?
5. What is contiguous memory allocation?
6. What is the difference between internal and external fragmentation?
7. How do first-fit, best-fit, and worst-fit memory allocation differ?
8. What is paging, and what are pages and frames?
9. What is segmentation, and how does it differ from paging?
10. What is a page table, and how is it used for address translation?
11. What is a Translation Lookaside Buffer (TLB), and why is it useful?
12. How does the OS prevent one process from accessing another process’s memory?

## 7. Virtual Memory and Page Replacement — High Priority

1. What is virtual memory, and why is it useful?
2. How can a process have a virtual address space larger than the available physical RAM?
3. What is demand paging?
4. What is a page fault, and what steps does the OS take to handle one?
5. How is a TLB miss different from a page fault?
6. Does every page fault require reading data from disk?
7. How do FIFO, Least Recently Used (LRU), and Optimal page replacement differ?
8. Given a page-reference string and a fixed number of frames, how would you calculate page faults using FIFO or LRU?
9. What is Belady’s anomaly, and which page replacement algorithm can exhibit it?
10. What is locality of reference, and how does it influence memory performance?
11. What is thrashing, what causes it, and how can it be reduced?
12. How does a valid page fault differ from an invalid memory access that causes a segmentation fault?

## 8. Interprocess Communication — Medium Priority

1. What is Interprocess Communication (IPC), and why is it needed?
2. What are the common IPC mechanisms?
3. How does shared memory differ from message passing?
4. Why does shared memory usually require additional synchronization?
5. How do anonymous pipes differ from named pipes?
6. How do pipes differ from message queues?
7. What are sockets, and can they be used for communication between processes on the same machine?
8. What are signals, and how do they differ from mechanisms designed to transfer application data?
9. Which IPC mechanism would you consider for two local processes exchanging large amounts of data, and what trade-offs would you evaluate?

## 9. File Systems — Medium Priority

1. What is a file system, and what responsibilities does it have?
2. What is the difference between a file’s contents and its metadata?
3. What is a file descriptor, and how does a process use it?
4. What is an inode in a Unix-like file system?
5. How do absolute and relative paths differ?
6. How do hard links and symbolic links differ?
7. What happens to hard links and symbolic links when the original filename is deleted?
8. What happens when a process keeps a file open after its filename has been deleted?
9. How do contiguous, linked, and indexed file allocation differ?
10. What is file-system journaling, and how does it help after a crash?

## 10. I/O and Storage Management — Medium Priority

1. What is the role of a device driver?
2. How does polling differ from interrupt-driven I/O?
3. What is Direct Memory Access (DMA), and why is it useful?
4. What is the difference between buffering, caching, and spooling?
5. How does blocking I/O differ from non-blocking I/O?
6. Why does a process typically enter a waiting state during blocking I/O?
7. Why is disk scheduling useful for hard disk drives?
8. How do FCFS, SSTF, SCAN, and C-SCAN disk scheduling differ?
9. Why are seek-based disk scheduling algorithms less relevant to SSDs?

## 11. Linux/Unix Process Basics — Medium Priority

1. What are the roles of `fork()`, `exec()`, and `wait()`?
2. What does `fork()` return in the parent and child processes?
3. How does creating a child with `fork()` differ from replacing a process’s program with `exec()`?
4. How many processes are created by a short code snippet containing multiple unconditional `fork()` calls?
5. What is a zombie process, and how is it removed?
6. What is an orphan process, and how does it differ from a zombie process?
7. What is the difference between `SIGTERM` and `SIGKILL`?
8. How would you inspect running processes, CPU usage, and memory usage using basic Linux commands?
9. How do read, write, and execute permissions differ for files and directories?

## 12. Optional Advanced Topics — Low Priority

1. How do monolithic kernels and microkernels differ?
2. What is copy-on-write, and how can it make `fork()` more efficient?
3. What is priority inversion, and how does priority inheritance address it?
4. What is a condition variable, and why should its condition usually be checked in a loop?
5. What is the difference between a deadlock-free algorithm and a lock-free algorithm?
6. How do virtual machines and containers differ in their relationship with the operating system?
7. What is a real-time operating system, and how do hard and soft real-time requirements differ?
8. Why are multilevel page tables useful for large virtual address spaces?

## Must-Prepare Checklist

- [ ] OS responsibilities, kernel, user mode, and kernel mode.
- [ ] System calls, interrupts, and exceptions.
- [ ] Program vs process vs thread.
- [ ] Process states and the Process Control Block.
- [ ] Resources shared and owned by threads.
- [ ] Context switching and its overhead.
- [ ] Concurrency vs parallelism.
- [ ] Preemptive vs non-preemptive scheduling.
- [ ] FCFS, SJF, SRTF, and Round Robin.
- [ ] Scheduling Gantt charts, waiting time, turnaround time, and response time.
- [ ] Starvation, aging, and the convoy effect.
- [ ] Race conditions and critical sections.
- [ ] Mutexes, semaphores, and spinlocks.
- [ ] Producer–consumer synchronization.
- [ ] Deadlock conditions and handling strategies.
- [ ] Deadlock vs starvation vs livelock.
- [ ] Safe states and basic Banker’s algorithm problems.
- [ ] Virtual vs physical addresses.
- [ ] Stack vs heap.
- [ ] Internal vs external fragmentation.
- [ ] Paging vs segmentation.
- [ ] Page tables, the MMU, and the TLB.
- [ ] Virtual memory, demand paging, and page-fault handling.
- [ ] FIFO and LRU page-replacement problems.
- [ ] Belady’s anomaly, locality, and thrashing.
- [ ] Shared memory vs message passing.
- [ ] File descriptors, inodes, and file links.
- [ ] Buffering vs caching vs spooling.
- [ ] Blocking vs non-blocking I/O.
- [ ] `fork()`, `exec()`, and `wait()`.
- [ ] Zombie vs orphan processes.
