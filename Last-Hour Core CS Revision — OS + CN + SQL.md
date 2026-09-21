Yes. Since you are in your **last-hour revision**, do not try to revise every topic we covered. Focus on the concepts interviewers can use to branch into multiple follow-ups.

Use this as a **60-minute OS + CN + SQL final revision sheet**.

# Last-Hour Core CS Revision — OS + CN + SQL

## How to use this

For every question, remember:

> **Definition → Why it exists → Small example → Important distinction**

If the interviewer asks only for a definition, give the **first 2–3 sentences**. Expand only when they ask further.

---

# PART 1 — OPERATING SYSTEMS

## 1. What is an Operating System?

> An Operating System is system software that acts as an interface between applications and hardware. It manages resources such as CPU, memory, processes, files, and I/O devices.

Remember:

```text
OS = Resource Manager + Hardware Abstraction
```

---

## 2. What is a Process?

> A process is a program currently in execution. Along with program instructions, it contains runtime information such as the program counter, registers, stack, heap, and process state.

```text
Program → Passive
Process → Program in execution
```

---

## 3. Process vs Thread

A **process** has its own address space.

A **thread** is an execution unit inside a process.

Threads of the same process share:

```text
Code
Heap
Open files/resources
```

But each thread has its own:

```text
Stack
Registers
Program Counter
```

Memory trick:

```text
Process → Separate house
Threads → People living inside that house
```

---

## 4. What are Process States?

Main states:

```text
New
 ↓
Ready
 ↓
Running
 ↓
Waiting / Blocked
 ↓
Ready
 ↓
Running
 ↓
Terminated
```

Very important:

```text
Ready
→ Waiting for CPU

Blocked
→ Waiting for I/O/event/resource
```

Do not confuse them.

---

## 5. What is PCB?

PCB stands for **Process Control Block**.

> It is an OS data structure containing information required to manage a process.

Contains things such as:

```text
Process ID
Process State
Program Counter
Registers
Scheduling Information
Memory Information
```

Think:

> **PCB = Process's record maintained by OS.**

---

## 6. What is Context Switching?

> Context switching is saving the state of the currently running process/thread and restoring another process/thread's state so the CPU can switch execution.

```text
Process A
 ↓
Save State
 ↓
Load B State
 ↓
Process B
```

Important:

> Context switching has overhead.

---

## 7. What is Multiprogramming?

> Multiple programs are kept in memory. When one process waits for I/O, another ready process uses the CPU.

Main goal:

```text
CPU Utilization
```

Memory:

> **Don't allow CPU to sit idle.**

---

## 8. What is Multitasking?

> Multitasking allows multiple tasks to share CPU time using rapid context switching.

A process may be preempted when:

```text
Time quantum expires
```

Main goal:

```text
Responsiveness
```

Difference:

```text
Multiprogramming
→ Keep CPU busy

Multitasking
→ Keep applications responsive
```

---

## 9. What is Multiprocessing?

> Multiprocessing uses multiple processors or CPU cores so multiple tasks can actually execute in parallel.

```text
Core 1 → Process A
Core 2 → Process B
```

---

# 10. Concurrency vs Parallelism

```text
Concurrency
→ Multiple tasks make progress over overlapping time

Parallelism
→ Multiple tasks execute at the exact same time
```

Single core can provide concurrency.

Multiple cores enable true parallelism.

---

# 11. User Mode vs Kernel Mode

### User Mode

Applications run with restricted privileges.

### Kernel Mode

Kernel executes with privileges required to access protected memory, hardware, and privileged CPU instructions.

Why?

> To prevent application bugs or malicious software from damaging the entire system.

```text
Application
   ↓
User Mode
   ↓
System Call
   ↓
Kernel Mode
   ↓
Hardware / OS resource
```

---

# 12. What is a System Call?

> A system call is the mechanism through which a user-mode application requests a service from the kernel.

Examples:

```text
Read file
Write file
Create process
Network operation
```

---

# 13. What is CPU Scheduling?

> CPU scheduling determines which process from the ready queue gets the CPU next.

Important algorithms:

```text
FCFS
SJF
SRTF
Round Robin
Priority
```

---

# 14. FCFS

First Come First Serve.

> The process that arrives first executes first.

Problem:

```text
Convoy Effect
```

A long process can make many short processes wait.

---

# 15. SJF

Shortest Job First.

> Process with the smallest CPU burst executes first.

Advantage:

> Can minimize average waiting time when burst times are known.

Problem:

```text
Starvation
```

Long jobs may keep waiting.

---

# 16. SRTF

Shortest Remaining Time First.

> Preemptive version of SJF.

If a new process arrives with less remaining execution time, the current process can be preempted.

---

# 17. Round Robin

> Each process gets CPU for a fixed time called the **time quantum**.

```text
P1 → 5ms
P2 → 5ms
P3 → 5ms
P1 → ...
```

If quantum is too small:

```text
Too many context switches
```

If too large:

```text
Round Robin behaves like FCFS
```

---

# 18. Preemptive vs Non-Preemptive Scheduling

```text
Preemptive
→ OS can take CPU away

Non-Preemptive
→ Process runs until completion/blocking/release
```

Examples:

```text
Round Robin → Preemptive
SRTF → Preemptive

FCFS → Non-preemptive
SJF → Usually discussed as non-preemptive
```

---

# 19. What is Starvation?

> A process keeps waiting indefinitely because other processes continuously receive the resource or CPU before it.

Solution:

```text
Aging
```

---

# 20. What is Aging?

> Aging gradually increases the priority of a process that has waited for a long time.

```text
Long waiting time
      ↓
Higher priority
```

---

# 21. What is a Race Condition?

> A race condition occurs when multiple threads access shared data concurrently and the result depends on execution order.

Example:

```text
count = 10

Thread A reads 10
Thread B reads 10

A writes 11
B writes 11

Expected 12
Actual 11
```

---

# 22. Critical Section

> A critical section is the part of code that accesses shared data/resources and therefore requires synchronization.

---

# 23. Mutex vs Semaphore

### Mutex

> Provides mutual exclusion—typically one owner accesses the critical section.

### Semaphore

> Counter-based synchronization mechanism that can control access to one or multiple resources.

Memory:

```text
Mutex
→ Lock

Semaphore
→ Counter / Signal
```

---

# 24. What is Deadlock?

> Deadlock occurs when processes wait indefinitely for resources held by one another.

Example:

```text
P1 holds R1, waits R2

P2 holds R2, waits R1
```

Neither progresses.

---

# 25. Four Conditions for Deadlock

Memorize:

```text
M H N C
```

```text
Mutual Exclusion
Hold and Wait
No Preemption
Circular Wait
```

All four are required for deadlock.

---

# 26. Deadlock vs Starvation

```text
Deadlock
→ Processes wait on one another

Starvation
→ One process repeatedly doesn't get resource

Deadlock
→ Involved processes stop

Starvation
→ Other processes continue
```

---

# 27. What is Paging?

> Paging divides virtual memory into fixed-size **pages** and physical memory into fixed-size **frames**.

```text
Page → Virtual Memory
Frame → Physical Memory
```

Page table maps:

```text
Page → Frame
```

---

# 28. What is Virtual Memory?

> Virtual memory gives processes their own large address space even though only part of it may currently exist in physical RAM.

Benefits:

```text
Process isolation
Efficient RAM usage
Programs can exceed available physical RAM
Demand paging
```

---

# 29. What is a Page Fault?

> A page fault occurs when a process accesses a page that is not currently loaded in physical memory.

Flow:

```text
Access Page
 ↓
Not in RAM
 ↓
Page Fault
 ↓
OS loads page
 ↓
Update mapping
 ↓
Resume execution
```

Important:

> A page fault is not necessarily an error.

It can be normal in demand paging.

---

# 30. What is TLB?

TLB = **Translation Lookaside Buffer**.

> It is a fast cache storing recently used virtual-page-to-physical-frame translations.

```text
Virtual Address
 ↓
TLB

Hit → Fast
Miss → Check Page Table
```

---

# 31. Internal vs External Fragmentation

```text
Internal Fragmentation
→ Wasted space inside allocated block

External Fragmentation
→ Free memory exists but is scattered
```

Paging mainly suffers from internal fragmentation.

Variable-size allocation/segmentation can suffer from external fragmentation.

---

# 32. What is Thrashing?

> Thrashing occurs when the system spends most of its time handling page faults and moving pages instead of performing useful execution.

```text
Too many page faults
        ↓
Heavy disk activity
        ↓
Poor performance
```

---

# PART 2 — COMPUTER NETWORKS

# 33. What is a Computer Network?

> A computer network is a collection of interconnected devices that communicate and share data or resources using networking protocols.

---

# 34. What is a Protocol?

> A protocol is a set of rules defining how devices communicate.

Examples:

```text
HTTP
TCP
UDP
IP
DNS
```

---

# 35. OSI Model

Memorize:

```text
7 Application
6 Presentation
5 Session
4 Transport
3 Network
2 Data Link
1 Physical
```

Mnemonic:

```text
All
People
Seem
To
Need
Data
Processing
```

---

# 36. What happens at each OSI layer?

```text
Application
→ HTTP, DNS, application services

Presentation
→ Encoding / encryption / compression

Session
→ Manage communication sessions

Transport
→ TCP / UDP / Ports

Network
→ IP / Routing

Data Link
→ MAC / Frames / Switch

Physical
→ Bits / Signals / Cables
```

---

# 37. TCP/IP Model

```text
Application
Transport
Internet
Network Access
```

TCP/IP is the practical Internet model.

OSI is mainly a conceptual reference model.

---

# 38. What is an IP Address?

> An IP address is a logical network address used to identify a network interface and route packets between networks.

---

# 39. IP vs MAC Address

```text
IP
→ Logical network address
→ Used for routing

MAC
→ Local-link address
→ Used inside LAN
```

Memory:

```text
IP → Across networks
MAC → Local delivery
```

---

# 40. What is a Port?

> A port identifies a particular application or service running on a host.

```text
IP
→ Which machine?

Port
→ Which application?
```

Example:

```text
192.168.1.10:8080
```

---

# 41. What is a Socket?

> A socket is an endpoint of network communication, commonly identified by an IP address and port.

```text
IP + Port
```

---

# 42. TCP vs UDP

### TCP

```text
Connection-oriented
Reliable
Ordered
Retransmission
Flow control
Congestion control
```

### UDP

```text
Connectionless
Best-effort
No built-in ordering guarantee
No built-in retransmission
Lower overhead
```

Typical:

```text
TCP → Web, reliable application communication

UDP → DNS, gaming, voice/video, real-time traffic
```

---

# 43. TCP Three-Way Handshake

Memorize:

```text
Client          Server

SYN     ------>

        <------ SYN-ACK

ACK     ------>
```

Purpose:

```text
Establish connection
Confirm both sides
Synchronize sequence numbers
```

---

# 44. TCP Connection Termination

Usually:

```text
FIN
ACK
FIN
ACK
```

Why four?

> TCP communication is full duplex, so each direction is closed independently.

---

# 45. Flow Control vs Congestion Control

Very common.

```text
Flow Control
→ Protect receiver

Congestion Control
→ Protect network
```

Flow control asks:

> Can the receiver handle more?

Congestion control asks:

> Can the network handle more?

---

# 46. What is HTTP?

> HTTP is an application-layer protocol used for client-server request-response communication.

```text
Client
 ↓ Request
Server
 ↓ Response
Client
```

---

# 47. What is HTTPS?

> HTTPS is HTTP protected using TLS.

Provides:

```text
Encryption
Integrity
Authentication
```

Remember:

```text
HTTPS = HTTP + TLS
```

---

# 48. What happens when you enter a URL?

One of the most important questions.

Remember this exact flow:

```text
1. Browser parses URL

2. DNS resolves domain → IP

3. Client establishes network connection

4. Usually TCP handshake
   or QUIC for HTTP/3

5. HTTPS → TLS handshake

6. Browser sends HTTP request

7. Server processes request

8. Server sends HTTP response

9. Browser renders response
```

For backend explanation:

```text
Browser
 ↓
DNS
 ↓
Server IP
 ↓
TCP/TLS
 ↓
HTTP Request
 ↓
Load Balancer / Reverse Proxy
 ↓
Backend
 ↓
Database
 ↓
HTTP Response
```

---

# 49. What is DNS?

> DNS translates human-readable domain names into IP addresses.

```text
google.com
 ↓
DNS
 ↓
IP Address
```

---

# 50. DNS Resolution

Simplified:

```text
Browser Cache
 ↓
OS Cache
 ↓
DNS Resolver
 ↓
Root
 ↓
TLD
 ↓
Authoritative DNS
 ↓
IP Address
```

Caching may prevent all steps from occurring every time.

---

# 51. What is ARP?

> ARP maps an IPv4 address to a MAC address on a local network.

```text
IP
 ↓
ARP
 ↓
MAC
```

Difference:

```text
DNS
→ Domain → IP

ARP
→ IPv4 → MAC
```

---

# 52. Router vs Switch

```text
Router
→ Connects networks
→ Uses IP routing

Switch
→ Connects devices within LAN
→ Forwards using MAC addresses
```

---

# 53. What is NAT?

> NAT translates private IP addresses to public addresses and vice versa.

Typical home network:

```text
Laptop 192.168.1.2
Phone  192.168.1.3
TV     192.168.1.4
        ↓
      Router
        ↓
   Public IP
```

Main reason:

> Allows many private devices to share limited public IPv4 connectivity.

---

# 54. What is DHCP?

> DHCP automatically provides network configuration to devices.

Such as:

```text
IP Address
Subnet Mask
Gateway
DNS Server
```

Remember:

```text
DORA

Discover
Offer
Request
Acknowledge
```

---

# 55. What is a Subnet Mask?

> A subnet mask tells which part of an IP address represents the network and which part represents the host.

Example:

```text
192.168.1.10/24
```

`/24` means:

> First 24 bits represent the network prefix.

---

# 56. What is Default Gateway?

> The default gateway is the router used when the destination lies outside the device's local network.

---

# 57. Packet vs Frame

```text
Transport
→ TCP Segment / UDP Datagram

Network
→ Packet

Data Link
→ Frame

Physical
→ Bits
```

---

# 58. What is Encapsulation?

> As application data travels down the network stack, each layer adds its own header.

```text
Application Data
 ↓
TCP Header
 ↓
IP Header
 ↓
Ethernet Header
 ↓
Bits
```

Receiver performs decapsulation.

---

# 59. Bandwidth vs Throughput vs Latency

```text
Bandwidth
→ Maximum theoretical capacity

Throughput
→ Actual achieved data rate

Latency
→ Time/delay taken
```

Think road:

```text
Bandwidth → Road width

Throughput → Cars actually passing

Latency → Time car takes to arrive
```

---

# 60. What is a Load Balancer?

> A load balancer distributes incoming requests across multiple backend servers.

```text
          → Server 1
Client → LB → Server 2
          → Server 3
```

Benefits:

```text
Scalability
Availability
Load distribution
```

---

# 61. Forward Proxy vs Reverse Proxy

```text
Forward Proxy
→ Represents clients

Reverse Proxy
→ Represents servers
```

Reverse proxy commonly handles:

```text
Routing
TLS termination
Caching
Load balancing
Security
```

---

# 62. HTTP vs WebSocket

```text
HTTP
→ Request-response

WebSocket
→ Persistent full-duplex connection
```

WebSocket is useful for:

```text
Chat
Live notifications
Ride tracking
Real-time dashboards
```

---

# 63. HTTP Status Codes

Must know:

```text
200 → OK
201 → Created
204 → No Content

400 → Bad Request
401 → Unauthorized
403 → Forbidden
404 → Not Found
409 → Conflict
429 → Too Many Requests

500 → Internal Server Error
502 → Bad Gateway
503 → Service Unavailable
504 → Gateway Timeout
```

---

# 64. 401 vs 403

Very common.

```text
401
→ Authentication missing/invalid

403
→ Identity is known, but permission denied
```

Memory:

```text
401 → Who are you?

403 → I know you, but you cannot access this.
```

---

# 65. HTTP Methods

```text
GET
→ Retrieve

POST
→ Create/submit

PUT
→ Replace/full update

PATCH
→ Partial update

DELETE
→ Delete
```

---

# 66. What is Idempotency?

> An operation is idempotent when performing it multiple times has the same intended effect as performing it once.

Generally:

```text
GET    → Idempotent
PUT    → Idempotent
DELETE → Idempotent

POST → Usually not assumed idempotent
```

---

# PART 3 — SQL / DATABASES

# 67. What is a Database?

> A database is an organized collection of persistent data that allows efficient storage, retrieval, update, and management.

---

# 68. Database vs DBMS

```text
Database
→ Actual collection of data

DBMS
→ Software used to manage that data
```

Examples of DBMS:

```text
MySQL
PostgreSQL
Oracle
```

---

# 69. SQL vs MySQL

```text
SQL
→ Language

MySQL
→ Relational DBMS using SQL
```

---

# 70. What is a Primary Key?

> A primary key uniquely identifies each row in a table and cannot contain NULL.

---

# 71. What is a Foreign Key?

> A foreign key references a key in another table and establishes relationships while maintaining referential integrity.

Example:

```text
Employee.department_id
        ↓
Department.department_id
```

---

# 72. Primary Key vs Unique Key

```text
Primary Key
→ Unique
→ No NULL
→ One PK constraint per table

Unique
→ Enforces uniqueness
→ Multiple unique constraints possible
→ NULL behavior DBMS-dependent
```

---

# 73. What is Normalization?

> Normalization organizes data into appropriate tables to reduce redundancy and avoid insert/update/delete anomalies.

Remember:

```text
1NF
→ Atomic values

2NF
→ No partial dependency

3NF
→ No transitive dependency

BCNF
→ Every determinant must be a superkey
```

---

# 74. What is Functional Dependency?

```text
X → Y
```

means:

> Knowing X uniquely determines Y.

Example:

```text
StudentID → StudentName
```

---

# 75. What is a Non-Trivial Functional Dependency?

```text
X → Y
```

is non-trivial when:

```text
Y is not already contained in X
```

Example:

```text
StudentID → Name
```

Non-trivial.

But:

```text
(StudentID, Name) → StudentID
```

is trivial because `StudentID` is already on the left.

---

# 76. What is GROUP BY?

> `GROUP BY` groups rows having the same value so aggregate calculations can be performed on each group.

```sql
SELECT department, AVG(salary)
FROM Employee
GROUP BY department;
```

Memory:

> **For each X, calculate Y.**

---

# 77. What is HAVING?

> `HAVING` filters groups created by `GROUP BY`.

```sql
SELECT department, AVG(salary)
FROM Employee
GROUP BY department
HAVING AVG(salary) > 50000;
```

Difference:

```text
WHERE
→ Filter rows

HAVING
→ Filter groups
```

---

# 78. ORDER BY

> Sorts the result.

```sql
ORDER BY salary DESC;
```

```text
ASC → Low to high
DESC → High to low
```

---

# 79. LIMIT and OFFSET

```sql
LIMIT N
OFFSET M
```

means:

```text
Skip M
Take N
```

Example:

```sql
SELECT *
FROM Employee
ORDER BY id
LIMIT 10
OFFSET 20;
```

Means:

```text
Skip first 20
Return next 10
```

---

# 80. What is a JOIN?

> A JOIN combines related rows from multiple tables.

Universal syntax:

```sql
SELECT columns
FROM TableA a
JOIN TableB b
ON a.key = b.key;
```

---

# 81. INNER JOIN

> Returns only matching rows from both tables.

```text
A ∩ B
```

---

# 82. LEFT JOIN

> Returns every row from the left table plus matching rows from the right.

No right-side match:

```text
Right columns → NULL
```

---

# 83. Find unmatched records

Very common.

```sql
SELECT a.*
FROM TableA a
LEFT JOIN TableB b
ON a.id = b.id
WHERE b.id IS NULL;
```

Memory:

```text
LEFT JOIN + right.id IS NULL
→ Find missing/unmatched records
```

---

# 84. SELF JOIN

> A table is joined with itself.

Example:

Employee + Manager:

```sql
SELECT e.name AS employee,
       m.name AS manager
FROM Employee e
LEFT JOIN Employee m
ON e.manager_id = m.emp_id;
```

---

# 85. What is a Subquery?

> A query nested inside another query.

Example:

Find employees earning above average:

```sql
SELECT *
FROM Employee
WHERE salary > (
    SELECT AVG(salary)
    FROM Employee
);
```

---

# 86. Second Highest Salary

```sql
SELECT MAX(salary)
FROM Employee
WHERE salary < (
    SELECT MAX(salary)
    FROM Employee
);
```

Logic:

```text
Find maximum
 ↓
Remove it
 ↓
Find next maximum
```

---

# 87. ROW_NUMBER vs RANK vs DENSE_RANK

Given:

```text
90000
80000
80000
70000
```

### ROW_NUMBER

```text
1
2
3
4
```

Unique sequence.

### RANK

```text
1
2
2
4
```

Tie + gap.

### DENSE_RANK

```text
1
2
2
3
```

Tie + no gap.

Memory:

```text
ROW_NUMBER → Unique

RANK → Tie + Gap

DENSE_RANK → Tie + No Gap
```

---

# 88. Nth Highest Salary

```sql
SELECT *
FROM (
    SELECT *,
           DENSE_RANK() OVER (
               ORDER BY salary DESC
           ) AS rnk
    FROM Employee
) t
WHERE rnk = N;
```

---

# 89. Top N Per Department

Very important.

```sql
SELECT *
FROM (
    SELECT *,
           DENSE_RANK() OVER (
               PARTITION BY department_id
               ORDER BY salary DESC
           ) AS rnk
    FROM Employee
) t
WHERE rnk <= 3;
```

Memory:

```text
Top N per group
→ PARTITION BY
→ DENSE_RANK
```

---

# 90. Find Duplicates

```sql
SELECT email, COUNT(*)
FROM Users
GROUP BY email
HAVING COUNT(*) > 1;
```

Memory:

```text
Duplicates
=
GROUP BY
+
HAVING COUNT(*) > 1
```

---

# 91. DELETE vs TRUNCATE vs DROP

```text
DELETE
→ Remove rows
→ Can use WHERE

TRUNCATE
→ Remove all rows quickly

DROP
→ Remove entire table/object
```

---

# 92. UNION vs UNION ALL

```text
UNION
→ Combine results
→ Remove duplicates

UNION ALL
→ Combine results
→ Keep duplicates
```

---

# 93. What is an Index?

> An index is an additional data structure used to speed up data retrieval.

Think:

> Book index → Find page quickly.

Trade-off:

```text
Faster reads
BUT
Extra storage
Slower writes/updates/deletes
```

So don't create indexes blindly.

---

# 94. What is a Transaction?

> A transaction is a group of database operations treated as one logical unit of work.

Example bank transfer:

```text
A -1000
B +1000
```

Both should succeed together.

---

# 95. ACID Properties

Memorize:

```text
A → Atomicity
C → Consistency
I → Isolation
D → Durability
```

### Atomicity

```text
All or nothing
```

### Consistency

```text
Valid state → Valid state
```

### Isolation

```text
Concurrent transactions shouldn't improperly interfere
```

### Durability

```text
Committed changes survive failures
```

---

# 96. COMMIT vs ROLLBACK

```text
COMMIT
→ Permanently save transaction changes

ROLLBACK
→ Undo uncommitted changes
```

---

# FINAL 20 QUESTIONS — MUST REVISE BEFORE INTERVIEW

If you now have only **15–20 minutes left**, revise these:

1. **OS:** What is an Operating System?
2. Process vs Thread.
3. Process states: Ready vs Blocked.
4. What is Context Switching?
5. User Mode vs Kernel Mode + System Calls.
6. Multiprogramming vs Multitasking.
7. Race Condition + Critical Section.
8. Mutex vs Semaphore.
9. Deadlock + four conditions.
10. Paging + Virtual Memory + Page Fault + TLB.
11. **CN:** OSI model and major responsibility of each layer.
12. TCP vs UDP.
13. TCP three-way handshake.
14. What happens when you enter a URL?
15. DNS vs ARP.
16. IP vs MAC + Router vs Switch.
17. HTTP vs HTTPS + 401 vs 403.
18. **SQL:** WHERE vs HAVING + GROUP BY.
19. JOINs + second/Nth highest salary + duplicates.
20. ACID + Index + DELETE/TRUNCATE/DROP.

# 5 End-to-End Stories You Should Be Able to Explain

These five flows connect most concepts.

### 1. Opening a website

```text
Enter URL
 ↓
DNS → Domain to IP
 ↓
TCP connection
 ↓
TLS for HTTPS
 ↓
HTTP request
 ↓
Server
 ↓
Database
 ↓
HTTP response
```

### 2. OS running multiple applications

```text
Chrome + IntelliJ + Spotify
 ↓
Processes/Threads
 ↓
Ready Queue
 ↓
Scheduler
 ↓
CPU
 ↓
Context Switching
```

### 3. Application reading a file

```text
Java Application
 ↓
User Mode
 ↓
System Call
 ↓
Kernel Mode
 ↓
File System / Driver
 ↓
Disk
```

### 4. Database transaction

```text
Transfer ₹1000

A -1000
B +1000
 ↓
Transaction
 ↓
Success → COMMIT
Failure → ROLLBACK
```

ACID protects this process.

### 5. Backend request

```text
Client
 ↓
DNS
 ↓
Load Balancer / Reverse Proxy
 ↓
Spring Boot Server
 ↓
Controller
 ↓
Service
 ↓
Repository
 ↓
SQL Database
 ↓
Response
```

That single flow connects **CN + OS + SQL + backend**.

# Final Memory Sheet

```text
OS
→ Resource Manager

Process
→ Program in execution

Thread
→ Execution unit inside process

Ready
→ Waiting for CPU

Blocked
→ Waiting for I/O/event

Context Switch
→ Save one task, load another

Mutex
→ Lock

Semaphore
→ Counter

Deadlock
→ MHNC

Paging
→ Pages + Frames

TLB
→ Cache page translations

Page Fault
→ Page not currently in RAM


CN
→ Devices communicating

IP
→ Network address

MAC
→ Local-link address

Port
→ Application

TCP
→ Reliable + Ordered

UDP
→ Connectionless + Low overhead

DNS
→ Domain → IP

ARP
→ IPv4 → MAC

Router
→ Network to Network

Switch
→ Device to Device in LAN

HTTPS
→ HTTP + TLS


SQL
→ Query language

WHERE
→ Filter rows

GROUP BY
→ Create groups

HAVING
→ Filter groups

ORDER BY
→ Sort

LIMIT
→ Take

OFFSET
→ Skip

JOIN
→ Combine tables

Index
→ Faster lookup

Transaction
→ Logical unit of work

ACID
→ Atomicity + Consistency + Isolation + Durability
```

For your last hour, **do not add new topics now**. Go through this once slowly, then do a second pass where you try to answer each bold question **without looking at the answer**. The areas worth giving extra attention are **Process vs Thread, Deadlock, Paging/Virtual Memory, TCP vs UDP, URL flow, DNS, JOINs, GROUP BY/HAVING, Indexes, and ACID**.
