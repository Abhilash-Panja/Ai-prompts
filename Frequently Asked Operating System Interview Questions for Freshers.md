# Frequently Asked Operating System Interview Questions for Freshers

These notes are designed for:

* Freshers
* 0–2 years experience
* Software Engineer interviews
* Java Backend interviews
* Product-based company interviews

The goal is **not to memorize textbook definitions**.

The goal is to understand:

```text
Why does the concept exist?
        ↓
What problem does it solve?
        ↓
How does it work?
        ↓
How do I explain it concisely in an interview?
```

---

# 1. What is an Operating System?

### On-Point Answer

An Operating System is **system software that acts as an interface between applications/users and computer hardware**.

It manages resources such as:

* CPU
* Memory
* Files
* I/O devices
* Processes

### Memory

```text
Operating System
=
Interface/Abstraction
+
Resource Manager
```

---

# 2. What are the Main Functions of an Operating System?

### On-Point Answer

The main functions are:

```text
Process Management
Memory Management
File Management
Device / I/O Management
CPU Scheduling
Security and Access Control
Resource Allocation
```

### Memory

```text
CPU
Memory
Processes
Files
Devices
Security
```

---

# 3. Why Do We Need an Operating System?

### On-Point Answer

Without an Operating System, every application would need to directly manage hardware resources.

The OS provides:

* Hardware abstraction
* Resource sharing
* Protection
* Process isolation
* Convenient APIs for applications

Example:

```text
Application
    ↓
Operating System
    ↓
Hardware
```

---

# 4. What is the Kernel?

### On-Point Answer

The kernel is the **core component of the Operating System**.

It runs with high privileges and manages:

* Processes
* Memory
* Devices
* File systems
* System calls
* Hardware interaction

### Memory

```text
Applications
    ↓
System Calls
    ↓
Kernel
    ↓
Hardware
```

---

# 5. What is User Mode?

### On-Point Answer

User Mode is a restricted execution mode where normal applications run.

Applications in User Mode cannot directly:

* Execute privileged instructions
* Modify kernel memory
* Freely access hardware

This protects the operating system from buggy or malicious applications.

---

# 6. What is Kernel Mode?

### On-Point Answer

Kernel Mode is a privileged execution mode where the operating-system kernel can perform critical operations and access protected system resources.

Examples:

```text
Manage memory
Control devices
Handle interrupts
Schedule processes
Execute privileged instructions
```

---

# 7. User Mode vs Kernel Mode

| User Mode                                 | Kernel Mode                         |
| ----------------------------------------- | ----------------------------------- |
| Applications normally run here            | Kernel runs here                    |
| Restricted privileges                     | High privileges                     |
| Cannot execute privileged instructions    | Can execute privileged instructions |
| Failure usually affects one process       | Serious failure can affect whole OS |
| Requests OS services through system calls | Performs OS services                |

### Memory

```text
User Mode
→ Restricted

Kernel Mode
→ Privileged
```

---

# 8. What is Privileged Mode?

### On-Point Answer

Privileged Mode refers to a CPU execution mode where code has permission to execute protected operations.

In common Operating System terminology:

```text
Privileged Mode
≈ Kernel Mode / Supervisor Mode
```

---

# 9. What is a System Call?

### On-Point Answer

A system call is the mechanism through which a user-level application requests a service from the Operating System kernel.

Examples:

```text
Open a file
Read a file
Create a process
Allocate resources
Use network services
```

Flow:

```text
Application
   ↓
System Call
   ↓
Kernel
   ↓
Requested Resource
```

---

# 10. Why Do We Need System Calls?

### On-Point Answer

User applications cannot directly perform privileged operations.

System calls provide a **controlled way to request kernel services**.

Example:

```text
Java Application
     ↓
File Read Request
     ↓
System Call
     ↓
Kernel
     ↓
Disk
```

---

# 11. What are the Types of Operating Systems?

Common types:

```text
Batch OS
Multiprogramming OS
Multitasking / Time-Sharing OS
Multiprocessing OS
Real-Time OS
Distributed OS
Embedded OS
```

---

# 12. What is a Batch Operating System?

### On-Point Answer

A Batch Operating System collects jobs and executes them automatically without continuous user interaction.

Common examples:

```text
Payroll Processing
Billing
Report Generation
```

### Memory

```text
Collect jobs
→ Process them automatically
```

---

# 13. What is Multiprogramming?

### On-Point Answer

Multiprogramming keeps multiple programs in memory.

When one program waits for I/O, another ready program gets the CPU.

The main goal is:

> **Improve CPU utilization.**

Flow:

```text
Process A Running
      ↓
Waiting for I/O
      ↓
Process B Runs
```

### Memory

```text
Multiprogramming
→ Don't let CPU stay idle
```

---

# 14. What is Multitasking?

### On-Point Answer

Multitasking allows multiple tasks to make progress by rapidly sharing CPU time.

The OS switches between tasks using **context switching**, often after a time slice expires.

### Memory

```text
Task A
 ↓
Context Switch
 ↓
Task B
 ↓
Context Switch
 ↓
Task C
```

Goal:

> **Responsiveness**

---

# 15. Multiprogramming vs Multitasking

| Multiprogramming                    | Multitasking                         |
| ----------------------------------- | ------------------------------------ |
| Improves CPU utilization            | Improves responsiveness              |
| Multiple programs in memory         | Multiple tasks share CPU time        |
| Switch commonly when process blocks | Switch may happen after time quantum |
| Traditionally batch-oriented        | Interactive                          |

### Memory

```text
Multiprogramming
→ Keep CPU busy

Multitasking
→ Keep user experience responsive
```

---

# 16. What is Multiprocessing?

### On-Point Answer

Multiprocessing means using **multiple CPUs or CPU cores** to execute processes.

Example:

```text
Core 1 → Process A
Core 2 → Process B
Core 3 → Process C
```

This allows true parallel execution.

---

# 17. Multitasking vs Multiprocessing

```text
Multitasking
→ Many tasks share CPU time

Multiprocessing
→ Multiple CPUs/Cores execute work
```

Multitasking provides concurrency.

Multiprocessing can provide actual parallelism.

---

# 18. What is a Real-Time Operating System?

### On-Point Answer

A Real-Time Operating System is designed for systems where tasks must respond within specified timing constraints.

The focus is:

> **Predictability, not simply speed.**

Examples:

* Automotive control systems
* Robotics
* Industrial systems
* Avionics
* Spacecraft control systems

---

# 19. Hard Real-Time vs Soft Real-Time

## Hard Real-Time

Missing the deadline is unacceptable.

Example:

```text
Aircraft Control
Safety-Critical System
```

## Soft Real-Time

Occasional deadline misses may be tolerated.

Example:

```text
Multimedia
Streaming
```

### Memory

```text
Hard RTOS
→ Deadline MUST be met

Soft RTOS
→ Deadline SHOULD be met
```

---

# 20. What is an Embedded Operating System?

### On-Point Answer

An Embedded Operating System is designed for specialized devices performing specific tasks.

Examples:

```text
Router
Smart Appliance
Automotive Controller
Medical Device
```

These systems may have limited:

* Memory
* CPU
* Storage
* Power

---

# 21. What is a Distributed Operating System?

### On-Point Answer

A Distributed Operating System manages multiple network-connected computers and coordinates their resources while attempting to provide a unified computing environment.

```text
Machine A
Machine B
Machine C
    ↓
Coordinated as a system
```

---

# 22. What is a Program?

### On-Point Answer

A program is a **passive set of instructions stored on disk**.

Example:

```text
Chrome.exe
Java .class / .jar
Executable file
```

---

# 23. What is a Process?

### On-Point Answer

A process is a **program currently in execution**.

It contains:

```text
Program Code
Program Counter
CPU Registers
Stack
Heap
Process State
```

### Memory

```text
Program
→ Passive

Process
→ Running instance of program
```

---

# 24. Program vs Process

| Program        | Process                      |
| -------------- | ---------------------------- |
| Passive        | Active                       |
| Stored on disk | Executing                    |
| Static         | Dynamic                      |
| Instructions   | Instructions + runtime state |

---

# 25. What is a Thread?

### On-Point Answer

A thread is the **smallest unit of CPU execution inside a process**.

Multiple threads of the same process share:

* Code
* Heap
* Process resources

But each thread has its own:

* Stack
* Program Counter
* Registers

---

# 26. Process vs Thread

| Process                                  | Thread                            |
| ---------------------------------------- | --------------------------------- |
| Independent execution unit               | Execution unit inside process     |
| Separate address space                   | Shares process address space      |
| Heavier                                  | Lighter                           |
| Context switching usually more expensive | Usually cheaper                   |
| Communication requires IPC               | Threads can share memory directly |

### Memory

```text
Process
→ Separate house

Threads
→ People living inside same house
```

---

# 27. What Do Threads Share?

Threads in the same process generally share:

```text
Code
Heap
Global Data
Open Files
Process Resources
```

Each thread has its own:

```text
Stack
Program Counter
Registers
```

---

# 28. Why are Threads Called Lightweight?

### On-Point Answer

Threads are lightweight because threads inside the same process share many resources.

Creating and switching between threads is generally less expensive than creating and switching between completely separate processes.

---

# 29. What are Process States?

Common states:

```text
New
Ready
Running
Waiting / Blocked
Terminated
```

Flow:

```text
New
 ↓
Ready
 ↓
Running
 ↙     ↘
Ready   Waiting
          ↓
        Ready

Running
  ↓
Terminated
```

---

# 30. What is Ready State?

### On-Point Answer

A process in Ready State has everything required to execute except the CPU.

```text
Ready
→ Waiting for CPU
```

---

# 31. What is Waiting / Blocked State?

### On-Point Answer

A blocked process cannot continue until some event occurs.

Example:

```text
Waiting for disk I/O
Waiting for network
Waiting for lock
```

---

# 32. Ready vs Waiting State

```text
Ready
→ Waiting for CPU

Waiting / Blocked
→ Waiting for some event/resource
```

This is a very common interviewer trap.

---

# 33. What is PCB?

PCB stands for:

> **Process Control Block**

### On-Point Answer

A PCB is a data structure maintained by the OS containing information required to manage a process.

It may contain:

```text
Process ID
Process State
Program Counter
CPU Registers
Scheduling Information
Memory Information
I/O Information
```

### Memory

```text
PCB
→ Process's OS record
```

---

# 34. What is Context Switching?

### On-Point Answer

Context switching is the process of saving the state of the currently running process/thread and restoring the state of another so the CPU can switch execution.

Flow:

```text
Process A
   ↓
Save Context
   ↓
Scheduler
   ↓
Load Context of B
   ↓
Process B
```

---

# 35. What Information is Saved During Context Switching?

Common information includes:

```text
Program Counter
CPU Registers
Stack Pointer
Process State
```

Process-related information is maintained using structures such as the PCB.

---

# 36. Is Context Switching Free?

### On-Point Answer

No.

Context switching introduces overhead because the CPU spends time:

* Saving state
* Selecting another task
* Restoring state
* Potentially losing useful cache/TLB state

During the switch, useful application work is not being performed.

---

# 37. What is a Scheduler?

### On-Point Answer

A scheduler is an OS component that determines which process should execute and when.

Important schedulers:

```text
Long-Term Scheduler
Short-Term Scheduler
Medium-Term Scheduler
```

---

# 38. What is Short-Term Scheduler?

### On-Point Answer

The short-term scheduler selects a process from the **Ready Queue** and gives it the CPU.

### Memory

```text
Ready Queue
    ↓
CPU Scheduler
    ↓
CPU
```

---

# 39. What is Long-Term Scheduler?

### On-Point Answer

The long-term scheduler decides which jobs are admitted into the system for execution.

It helps control the degree of multiprogramming.

---

# 40. What is Medium-Term Scheduler?

### On-Point Answer

The medium-term scheduler may temporarily remove processes from memory and later bring them back.

This is associated with:

```text
Swapping
```

---

# 41. What is CPU Scheduling?

### On-Point Answer

CPU scheduling is the process of selecting which ready process should receive CPU time.

Goals may include:

```text
High CPU utilization
High throughput
Low waiting time
Low turnaround time
Low response time
Fairness
```

---

# 42. What is FCFS Scheduling?

FCFS:

> First Come First Serve

### On-Point Answer

Processes execute in the order they arrive.

```text
P1 → P2 → P3
```

Advantages:

* Simple
* Easy to implement

Disadvantage:

> **Convoy Effect**

---

# 43. What is Convoy Effect?

### On-Point Answer

Convoy Effect occurs when a long-running process at the front of the queue causes many shorter processes to wait behind it.

Example:

```text
P1 = 20 sec
P2 = 2 sec
P3 = 1 sec

Execution:

P1 → P2 → P3
```

Short jobs wait unnecessarily.

---

# 44. What is SJF?

SJF:

> Shortest Job First

### On-Point Answer

SJF selects the process with the smallest CPU burst time.

It can minimize average waiting time when burst times are known.

Problem:

> Long processes may suffer starvation.

---

# 45. What is SRTF?

SRTF:

> Shortest Remaining Time First

### On-Point Answer

SRTF is the **preemptive version of SJF**.

If a new process arrives with a shorter remaining time, the currently running process may be preempted.

---

# 46. What is Round Robin Scheduling?

### On-Point Answer

Round Robin gives each ready process a fixed amount of CPU time called a **time quantum**.

Example:

```text
P1 → 5ms
P2 → 5ms
P3 → 5ms
P1 → ...
```

It is commonly associated with time-sharing systems.

---

# 47. What is Time Quantum?

### On-Point Answer

Time quantum is the maximum CPU time given to a process before it may be preempted and moved back to the ready queue.

---

# 48. What if Time Quantum is Too Small?

### On-Point Answer

If the time quantum is too small:

```text
More Context Switches
      ↓
More Overhead
```

---

# 49. What if Time Quantum is Too Large?

### On-Point Answer

Round Robin begins behaving more like FCFS.

---

# 50. What is Priority Scheduling?

### On-Point Answer

Priority Scheduling selects processes based on priority.

Higher-priority processes execute before lower-priority processes.

Problem:

> Low-priority processes may starve.

---

# 51. What is Starvation?

### On-Point Answer

Starvation occurs when a process waits indefinitely because other processes continuously receive the required CPU/resource first.

Example:

```text
Low Priority Process
       ↓
Keeps getting ignored
```

---

# 52. What is Aging?

### On-Point Answer

Aging prevents starvation by gradually increasing the priority of processes that have been waiting for a long time.

```text
Longer wait
   ↓
Higher priority
```

---

# 53. Preemptive vs Non-Preemptive Scheduling

## Preemptive

The OS can take the CPU away from a running process.

Examples:

```text
Round Robin
SRTF
Preemptive Priority
```

## Non-Preemptive

Once a process gets the CPU, it runs until:

* Completion
* Blocking
* Voluntary release

Examples:

```text
FCFS
Non-preemptive SJF
```

---

# 54. What is Turnaround Time?

### Formula

```text
Turnaround Time
=
Completion Time - Arrival Time
```

Meaning:

> Total time from process arrival until completion.

---

# 55. What is Waiting Time?

### Formula

```text
Waiting Time
=
Turnaround Time - CPU Burst Time
```

Meaning:

> Total time process spends waiting in ready queue.

---

# 56. What is Response Time?

### Formula

```text
Response Time
=
First CPU Start Time - Arrival Time
```

Meaning:

> How long the process waits before getting CPU for the first time.

---

# 57. What is Concurrency?

### On-Point Answer

Concurrency means multiple tasks make progress during overlapping periods of time.

On a single core:

```text
Task A
Task B
Task A
Task C
```

They may interleave rather than literally execute simultaneously.

---

# 58. What is Parallelism?

### On-Point Answer

Parallelism means multiple tasks are actually executing at the same time.

Example:

```text
Core 1 → Task A
Core 2 → Task B
```

---

# 59. Concurrency vs Parallelism

```text
Concurrency
→ Multiple tasks make progress

Parallelism
→ Multiple tasks execute simultaneously
```

### Memory

```text
Concurrency
→ Dealing with many things

Parallelism
→ Doing many things at once
```

---

# 60. What is a Race Condition?

### On-Point Answer

A race condition occurs when multiple threads/processes access shared data concurrently and the final result depends on the order of execution.

Example:

```text
count = 10

Thread A reads 10
Thread B reads 10

A writes 11
B writes 11

Expected = 12
Actual   = 11
```

---

# 61. What is Critical Section?

### On-Point Answer

A critical section is a part of code where shared data or resources are accessed.

Only properly synchronized threads should execute conflicting critical sections at the same time.

Example:

```text
lock
 ↓
Update shared balance
 ↓
unlock
```

---

# 62. What is Mutual Exclusion?

### On-Point Answer

Mutual exclusion ensures that only one thread/process at a time accesses a critical resource when exclusive access is required.

### Memory

```text
One at a time
```

---

# 63. What is a Mutex?

### On-Point Answer

A mutex is a synchronization mechanism used to provide mutual exclusion.

A thread acquires the mutex before entering a critical section and releases it afterward.

```text
Lock
 ↓
Critical Section
 ↓
Unlock
```

---

# 64. What is a Semaphore?

### On-Point Answer

A semaphore is a synchronization mechanism based on a counter that controls access to shared resources.

Two common types:

```text
Binary Semaphore
Counting Semaphore
```

---

# 65. Binary Semaphore vs Counting Semaphore

## Binary Semaphore

Values typically:

```text
0 or 1
```

Can be used for signaling or mutual-exclusion-style coordination.

## Counting Semaphore

Can have values greater than 1.

Useful when multiple identical resources exist.

Example:

```text
5 database connections
→ Semaphore count = 5
```

---

# 66. Mutex vs Semaphore

| Mutex                     | Semaphore                         |
| ------------------------- | --------------------------------- |
| Mainly mutual exclusion   | Signaling/resource counting       |
| Typically ownership-based | Not necessarily ownership-based   |
| Usually one holder        | Count may allow multiple accesses |

### Memory

```text
Mutex
→ Lock

Semaphore
→ Counter / Signal
```

---

# 67. What is Synchronization?

### On-Point Answer

Synchronization coordinates concurrent threads/processes so shared resources are accessed safely and operations occur in the required order.

It prevents problems such as:

* Race conditions
* Inconsistent data

---

# 68. What is Inter-Process Communication?

IPC stands for:

> **Inter-Process Communication**

### On-Point Answer

IPC refers to mechanisms that allow different processes to exchange data and coordinate.

Examples:

```text
Pipes
Message Queues
Shared Memory
Sockets
Signals
```

---

# 69. Shared Memory vs Message Passing

## Shared Memory

Processes communicate through a shared memory region.

Advantages:

```text
Fast
Less copying
```

Requires synchronization.

## Message Passing

Processes exchange explicit messages.

```text
Process A
   ↓
Message
   ↓
Process B
```

Often easier to isolate.

---

# 70. What is Deadlock?

### On-Point Answer

Deadlock is a situation where two or more processes wait indefinitely for resources held by each other.

Example:

```text
Process A holds Resource 1
and waits for Resource 2

Process B holds Resource 2
and waits for Resource 1
```

Neither can continue.

---

# 71. What are the Four Necessary Conditions for Deadlock?

All four must exist:

```text
1. Mutual Exclusion
2. Hold and Wait
3. No Preemption
4. Circular Wait
```

### Memory

```text
M H N C

Mutual Exclusion
Hold and Wait
No Preemption
Circular Wait
```

---

# 72. Explain Mutual Exclusion in Deadlock

A resource can be used by only one process at a time.

---

# 73. Explain Hold and Wait

A process holds at least one resource while waiting for another resource.

---

# 74. Explain No Preemption

Resources cannot simply be forcibly taken away; they must normally be released by the process holding them.

---

# 75. Explain Circular Wait

Processes form a circular chain of resource dependency.

Example:

```text
P1 waits for P2
P2 waits for P3
P3 waits for P1
```

---

# 76. How Can Deadlock Be Handled?

Common approaches:

```text
Deadlock Prevention
Deadlock Avoidance
Deadlock Detection and Recovery
Ignore the Problem
```

---

# 77. What is Deadlock Prevention?

### On-Point Answer

Deadlock prevention ensures that at least one of the four necessary deadlock conditions cannot occur.

Example:

Prevent circular wait by imposing a fixed resource ordering.

---

# 78. What is Deadlock Avoidance?

### On-Point Answer

Deadlock avoidance makes resource-allocation decisions only when the system can remain in a **safe state**.

Famous algorithm:

```text
Banker's Algorithm
```

---

# 79. What is a Safe State?

### On-Point Answer

A system is in a safe state if there exists some order in which all processes can complete without deadlock.

---

# 80. What is Banker's Algorithm?

### On-Point Answer

Banker's Algorithm is a deadlock-avoidance algorithm.

Before allocating resources, the OS checks whether the allocation keeps the system in a safe state.

### Memory

```text
Request Resource
     ↓
Would system remain safe?
     ↓
Yes → Allocate
No  → Wait
```

---

# 81. Deadlock vs Starvation

| Deadlock                           | Starvation                        |
| ---------------------------------- | --------------------------------- |
| Processes wait on each other       | One process keeps getting ignored |
| Usually circular dependency        | Resource/scheduling unfairness    |
| Involved processes cannot progress | Other processes may continue      |
| Requires deadlock conditions       | Doesn't require circular wait     |

---

# 82. What is Memory Management?

### On-Point Answer

Memory management is the OS function responsible for:

* Allocating memory
* Deallocating memory
* Tracking memory usage
* Protecting process memory
* Supporting virtual memory

---

# 83. What is Logical Address?

### On-Point Answer

A logical or virtual address is the address generated/used by a process.

The process generally sees its own virtual address space.

---

# 84. What is Physical Address?

### On-Point Answer

A physical address refers to the actual location in RAM.

```text
Virtual Address
     ↓
Address Translation
     ↓
Physical Address
```

---

# 85. Logical Address vs Physical Address

```text
Logical / Virtual Address
→ Address seen by process

Physical Address
→ Actual RAM location
```

---

# 86. What is Paging?

### On-Point Answer

Paging divides:

```text
Virtual Memory → Fixed-size Pages
Physical Memory → Fixed-size Frames
```

Pages can be placed into available frames.

### Memory

```text
Page
→ Virtual Memory

Frame
→ Physical Memory
```

---

# 87. Why Do We Need Paging?

### On-Point Answer

Paging allows processes to use non-contiguous physical memory and helps eliminate external fragmentation.

---

# 88. What is a Page Table?

### On-Point Answer

A page table maps virtual pages to physical frames.

Example:

```text
Page 0 → Frame 5
Page 1 → Frame 2
Page 2 → Frame 9
```

---

# 89. What is a TLB?

TLB stands for:

> **Translation Lookaside Buffer**

### On-Point Answer

TLB is a small, fast cache that stores recently used page-table entries.

It reduces the time required for virtual-to-physical address translation.

Flow:

```text
Virtual Address
     ↓
Check TLB
  ↙      ↘
Hit      Miss
 ↓         ↓
Fast    Check Page Table
```

---

# 90. What is TLB Hit?

The required page translation is found in the TLB.

```text
Fast translation
```

---

# 91. What is TLB Miss?

The translation is not in the TLB, so the page table must be consulted.

This is slower than a TLB hit.

---

# 92. What is Segmentation?

### On-Point Answer

Segmentation divides memory according to logical program units of variable size.

Examples:

```text
Code Segment
Data Segment
Stack Segment
```

Unlike paging, segments are generally variable-sized.

---

# 93. Paging vs Segmentation

| Paging                           | Segmentation                       |
| -------------------------------- | ---------------------------------- |
| Fixed-size blocks                | Variable-size blocks               |
| Pages and frames                 | Logical segments                   |
| Transparent to programmer        | Reflects logical program structure |
| Can cause internal fragmentation | Can cause external fragmentation   |

---

# 94. What is Fragmentation?

### On-Point Answer

Fragmentation occurs when memory is wasted because available memory cannot be used efficiently.

Types:

```text
Internal Fragmentation
External Fragmentation
```

---

# 95. What is Internal Fragmentation?

### On-Point Answer

Internal fragmentation occurs when allocated memory contains unused space inside the allocated block.

Example:

```text
Page size = 4 KB
Process needs = 3 KB

1 KB wasted inside page
```

---

# 96. What is External Fragmentation?

### On-Point Answer

External fragmentation occurs when enough free memory exists overall, but it is scattered into small non-contiguous blocks.

Example:

```text
Free 10 KB
Free 5 KB
Free 8 KB
```

Need:

```text
20 KB contiguous
```

Total free memory is enough, but no single block is large enough.

---

# 97. Internal vs External Fragmentation

```text
Internal Fragmentation
→ Waste inside allocated block

External Fragmentation
→ Waste/free gaps between allocated blocks
```

---

# 98. What is Virtual Memory?

### On-Point Answer

Virtual memory gives each process the illusion of having a large continuous address space even when all of its data is not currently in physical RAM.

It allows parts of a process to be loaded into RAM only when needed.

---

# 99. Why Do We Need Virtual Memory?

Virtual memory allows:

* Programs larger than physical RAM to run
* Better memory utilization
* Process isolation
* Demand paging
* More processes to coexist

---

# 100. What is Demand Paging?

### On-Point Answer

Demand paging loads a page into memory only when the process actually accesses it.

```text
Need page?
 ↓
Yes
 ↓
Load into RAM
```

---

# 101. What is a Page Fault?

### On-Point Answer

A page fault occurs when a process accesses a page that is not currently present in physical memory.

Flow:

```text
Process accesses page
        ↓
Page not in RAM
        ↓
Page Fault
        ↓
OS loads page from storage
        ↓
Update page table
        ↓
Resume process
```

---

# 102. Is Every Page Fault an Error?

### On-Point Answer

No.

A page fault can be a normal part of demand paging.

It becomes an error only when the access itself is invalid or cannot be satisfied.

---

# 103. What is Page Replacement?

### On-Point Answer

When memory is full and a new page needs to be loaded, the OS must choose an existing page to remove.

That decision is called **page replacement**.

Common algorithms:

```text
FIFO
LRU
Optimal
```

---

# 104. What is FIFO Page Replacement?

### On-Point Answer

FIFO removes the page that entered memory first.

```text
Oldest loaded page
→ Remove
```

Simple, but not always efficient.

---

# 105. What is LRU Page Replacement?

LRU:

> Least Recently Used

### On-Point Answer

LRU removes the page that has not been used for the longest time.

### Memory

```text
Used least recently
→ Replace
```

---

# 106. What is Optimal Page Replacement?

### On-Point Answer

Optimal replaces the page that will not be used for the longest time in the future.

It gives the minimum possible page faults for a reference string, but future accesses are not generally known in real systems.

So it is mainly used as a benchmark.

---

# 107. What is Belady's Anomaly?

### On-Point Answer

Belady's Anomaly is the situation where increasing the number of page frames unexpectedly increases the number of page faults.

It can occur with:

```text
FIFO
```

---

# 108. What is Thrashing?

### On-Point Answer

Thrashing occurs when the system spends most of its time swapping/loading pages instead of executing useful work.

```text
Too many page faults
      ↓
Constant disk activity
      ↓
Very little useful CPU work
```

---

# 109. Why Does Thrashing Occur?

Common reason:

> Processes do not have enough frames for their active working set.

This causes frequent page faults.

---

# 110. What is Swapping?

### On-Point Answer

Swapping involves moving process memory between RAM and secondary storage to free physical memory.

Conceptually:

```text
RAM
 ↕
Disk / Swap Space
```

---

# 111. What is an Interrupt?

### On-Point Answer

An interrupt is a signal that causes the CPU to temporarily stop normal execution and execute an interrupt handler.

Examples:

```text
Keyboard Input
Timer
Disk I/O completion
Network event
```

---

# 112. What Happens During an Interrupt?

Conceptually:

```text
Program Running
      ↓
Interrupt Occurs
      ↓
Save Current State
      ↓
Execute Interrupt Handler
      ↓
Restore State
      ↓
Resume Program
```

---

# 113. What is an Exception?

### On-Point Answer

An exception is an event generated during instruction execution that requires special handling.

Examples:

```text
Divide by zero
Invalid memory access
Page fault
```

---

# 114. Interrupt vs Exception

```text
Interrupt
→ Commonly caused by external/asynchronous events

Exception
→ Caused by currently executing instruction / synchronous event
```

---

# 115. What is a Trap?

### On-Point Answer

A trap is a synchronous transfer of control to the OS caused intentionally or by a particular CPU event.

Historically/system-dependently, system calls and certain exceptions may be implemented using trap mechanisms.

---

# 116. What is a File System?

### On-Point Answer

A file system is the method used by the Operating System to organize, store, retrieve, and manage files on storage devices.

Examples:

```text
NTFS
ext4
APFS
```

---

# 117. What is a File Descriptor?

### On-Point Answer

A file descriptor is a small integer used by Unix-like operating systems to identify an open file or I/O resource within a process.

Common descriptors:

```text
0 → Standard Input
1 → Standard Output
2 → Standard Error
```

---

# 118. What is an inode?

### On-Point Answer

In Unix-like file systems, an inode stores metadata about a file.

It may contain:

```text
File type
Permissions
Owner
Size
Timestamps
Pointers to data blocks
```

The filename itself is generally stored in directory entries, not directly as part of the inode's main metadata.

---

# 119. What is a Device Driver?

### On-Point Answer

A device driver is software that allows the Operating System to communicate with and control a hardware device.

Examples:

```text
Printer Driver
Network Driver
GPU Driver
Storage Driver
```

Flow:

```text
Application
    ↓
Operating System
    ↓
Device Driver
    ↓
Hardware
```

---

# 120. What is Booting?

### On-Point Answer

Booting is the process of starting the computer and loading the Operating System into memory.

Simplified flow:

```text
Power On
   ↓
Firmware
   ↓
Bootloader
   ↓
Kernel
   ↓
Operating System Services
```

---

# Most Important Comparison Questions

## Process vs Thread

```text
Process
→ Separate address space

Thread
→ Shares process address space
```

---

## Program vs Process

```text
Program
→ Passive instructions

Process
→ Program in execution
```

---

## User Mode vs Kernel Mode

```text
User Mode
→ Restricted

Kernel Mode
→ Privileged
```

---

## Multiprogramming vs Multitasking

```text
Multiprogramming
→ CPU utilization

Multitasking
→ Responsiveness
```

---

## Concurrency vs Parallelism

```text
Concurrency
→ Multiple tasks make progress

Parallelism
→ Tasks actually execute simultaneously
```

---

## Mutex vs Semaphore

```text
Mutex
→ Exclusive lock

Semaphore
→ Counter / signaling mechanism
```

---

## Deadlock vs Starvation

```text
Deadlock
→ Processes wait on each other

Starvation
→ One process keeps getting ignored
```

---

## Paging vs Segmentation

```text
Paging
→ Fixed-size

Segmentation
→ Variable-size logical units
```

---

## Internal vs External Fragmentation

```text
Internal
→ Waste inside allocation

External
→ Free space scattered outside allocations
```

---

## Logical vs Physical Address

```text
Logical
→ Seen/generated by process

Physical
→ Actual location in RAM
```

---

# Top 25 OS Questions to Prioritize

If preparation time is limited, master these first:

```text
1. What is an Operating System?

2. Main functions of OS

3. Kernel

4. User Mode vs Kernel Mode

5. System Calls

6. Process vs Program

7. Process vs Thread

8. Process States

9. PCB

10. Context Switching

11. CPU Scheduling

12. FCFS / SJF / Round Robin

13. Preemptive vs Non-Preemptive Scheduling

14. Concurrency vs Parallelism

15. Race Condition

16. Critical Section

17. Mutex vs Semaphore

18. Deadlock

19. Four Deadlock Conditions

20. Deadlock vs Starvation

21. Paging

22. Virtual Memory

23. Page Fault

24. TLB

25. Internal vs External Fragmentation
```

---

# Most Common Interview Traps

## Trap 1

### Wrong

```text
A process waiting for CPU is in waiting state.
```

### Correct

```text
Waiting for CPU
→ Ready State

Waiting for I/O/resource
→ Blocked State
```

---

## Trap 2

### Wrong

```text
Multitasking means tasks execute truly simultaneously.
```

### Correct

On a single CPU core:

```text
Multitasking
→ Rapid context switching / concurrency
```

Multiple cores can provide parallelism.

---

## Trap 3

### Wrong

```text
Real-time means extremely fast.
```

### Correct

```text
Real-time
→ Predictable execution within timing constraints
```

---

## Trap 4

### Wrong

```text
Every page fault is an error.
```

### Correct

```text
Page fault
→ Can be normal in demand paging
```

---

## Trap 5

### Wrong

```text
Threads have completely separate memory.
```

### Correct

Threads in the same process generally share:

```text
Code
Heap
Process resources
```

but have separate:

```text
Stacks
Registers
Program Counters
```

---

## Trap 6

### Wrong

```text
Context switching is free.
```

### Correct

```text
Context Switch
→ CPU + cache/TLB overhead
```

---

## Trap 7

### Wrong

```text
Deadlock and starvation are the same.
```

### Correct

```text
Deadlock
→ Circular/resource dependency stops progress

Starvation
→ One process waits indefinitely while others progress
```

---

# OS Interview Question → Concept Mapping

| Interview Wording                        | Think                     |
| ---------------------------------------- | ------------------------- |
| Program currently running                | `Process`                 |
| Smallest execution unit                  | `Thread`                  |
| OS record of process                     | `PCB`                     |
| Waiting for CPU                          | `Ready State`             |
| Waiting for I/O                          | `Blocked State`           |
| Save one process and load another        | `Context Switching`       |
| Decide who gets CPU                      | `Scheduling`              |
| Give everyone a time slice               | `Round Robin`             |
| One process never gets CPU               | `Starvation`              |
| Increase priority over time              | `Aging`                   |
| Shared data produces inconsistent result | `Race Condition`          |
| Protect shared section                   | `Mutex / Synchronization` |
| Multiple available identical resources   | `Counting Semaphore`      |
| Processes waiting forever for each other | `Deadlock`                |
| Deadlock prerequisites                   | `MHNC`                    |
| Virtual page to physical frame           | `Page Table`              |
| Cache page-table entries                 | `TLB`                     |
| Required page isn't in RAM               | `Page Fault`              |
| Load pages only when needed              | `Demand Paging`           |
| Too many page faults                     | `Thrashing`               |
| Fixed-size memory blocks                 | `Paging`                  |
| Variable logical memory blocks           | `Segmentation`            |
| Waste inside allocation                  | `Internal Fragmentation`  |
| Scattered free memory                    | `External Fragmentation`  |
| Several tasks make progress              | `Concurrency`             |
| Tasks execute at same instant            | `Parallelism`             |

---

# Final OS Memory Map

```text
Operating System
│
├── Kernel
│   ├── User Mode
│   ├── Kernel Mode
│   └── System Calls
│
├── Process Management
│   ├── Process
│   ├── Thread
│   ├── PCB
│   ├── Process States
│   ├── Context Switching
│   └── Scheduling
│
├── CPU Scheduling
│   ├── FCFS
│   ├── SJF
│   ├── SRTF
│   ├── Round Robin
│   └── Priority
│
├── Concurrency
│   ├── Race Condition
│   ├── Critical Section
│   ├── Mutex
│   ├── Semaphore
│   └── IPC
│
├── Deadlocks
│   ├── Mutual Exclusion
│   ├── Hold and Wait
│   ├── No Preemption
│   ├── Circular Wait
│   ├── Prevention
│   ├── Avoidance
│   └── Detection / Recovery
│
├── Memory Management
│   ├── Logical Address
│   ├── Physical Address
│   ├── Paging
│   ├── Segmentation
│   ├── Page Table
│   ├── TLB
│   ├── Virtual Memory
│   ├── Demand Paging
│   ├── Page Fault
│   ├── Page Replacement
│   └── Thrashing
│
└── Storage / I/O
    ├── File System
    ├── File Descriptor
    ├── inode
    ├── Device Driver
    └── Interrupts
```

---

# Final Interview Strategy

For every OS question, ask yourself:

```text
1. What problem existed?

2. Why was this concept introduced?

3. How does the OS solve that problem?

4. Can I give one simple example?

5. Can I explain it in 20–30 seconds?
```

Example:

```text
Why Multiprogramming?
→ CPU was sitting idle during I/O.

Solution?
→ Run another process.

Main goal?
→ Improve CPU utilization.
```

Another:

```text
Why User Mode?
→ Applications should not have unrestricted hardware access.

Solution?
→ Restrict application privileges.

Need protected operation?
→ Use system call to kernel.
```

Another:

```text
Why Virtual Memory?
→ RAM is limited and processes need isolation.

Solution?
→ Give processes virtual address spaces and keep only required pages in RAM.
```

---

# One-Line Revision Sheet

```text
OS
→ Resource Manager + Hardware Abstraction

Kernel
→ Core privileged OS component

System Call
→ User program requests kernel service

Process
→ Program in execution

Thread
→ Smallest execution unit inside process

PCB
→ OS record of a process

Ready
→ Waiting for CPU

Blocked
→ Waiting for event/resource

Context Switch
→ Save one task, restore another

Multiprogramming
→ Keep CPU busy

Multitasking
→ Keep tasks responsive

Round Robin
→ Time quantum

Starvation
→ Process waits indefinitely

Aging
→ Increase priority over time

Race Condition
→ Result depends on execution order

Critical Section
→ Shared-resource code section

Mutex
→ Exclusive lock

Semaphore
→ Counter / signaling

Deadlock
→ Processes permanently wait for each other's resources

Deadlock Conditions
→ Mutual Exclusion + Hold and Wait + No Preemption + Circular Wait

Paging
→ Pages + Frames

Page Table
→ Page → Frame mapping

TLB
→ Cache address translations

Virtual Memory
→ Large virtual address space using RAM + backing storage mechanisms

Demand Paging
→ Load page when required

Page Fault
→ Required page not currently in RAM

Thrashing
→ Too many page faults

Internal Fragmentation
→ Waste inside allocated space

External Fragmentation
→ Free memory scattered

Concurrency
→ Overlapping progress

Parallelism
→ Simultaneous execution
```

> **For fresher OS interviews, understanding the flow is more valuable than memorizing definitions. Always explain the problem first, then the OS mechanism used to solve it.**
