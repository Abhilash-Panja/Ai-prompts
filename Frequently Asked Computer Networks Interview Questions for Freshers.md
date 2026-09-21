# Frequently Asked Computer Networks Interview Questions for Freshers

These notes are designed for:

* Freshers
* 0–2 years experience
* Software Engineer interviews
* Java Backend interviews
* Product-based company interviews

The goal is not to memorize networking definitions.

The goal is to understand:

```text
What problem exists?
        ↓
Which protocol/layer solves it?
        ↓
How does the data flow?
        ↓
Can I explain it in 20–30 seconds?
```

---

# 1. What is a Computer Network?

### On-Point Answer

A computer network is a collection of interconnected devices that communicate and share data or resources.

Examples:

```text
Laptop
Phone
Server
Router
Printer
```

connected through:

```text
Wired Network
Wireless Network
Internet
```

---

# 2. Why Do We Need Computer Networks?

### On-Point Answer

Computer networks allow devices to:

* Exchange data
* Share resources
* Access remote services
* Communicate
* Use distributed applications

Example:

```text
Browser
   ↓
Internet
   ↓
Backend Server
   ↓
Database
```

---

# 3. What is a Protocol?

### On-Point Answer

A protocol is a set of rules that defines how devices communicate over a network.

Examples:

```text
HTTP
HTTPS
TCP
UDP
IP
DNS
SMTP
```

### Memory

```text
Protocol
→ Rules of communication
```

---

# 4. What is the OSI Model?

OSI stands for:

> Open Systems Interconnection

### On-Point Answer

The OSI model is a conceptual networking model containing 7 layers.

```text
7. Application
6. Presentation
5. Session
4. Transport
3. Network
2. Data Link
1. Physical
```

---

# 5. OSI Layers in Order

Top to bottom:

```text
Application
Presentation
Session
Transport
Network
Data Link
Physical
```

Memory trick:

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

# 6. What Does the Application Layer Do?

### On-Point Answer

The Application Layer provides network services directly to user applications.

Examples:

```text
HTTP
HTTPS
FTP
SMTP
DNS
```

Example:

```text
Browser
→ HTTP / HTTPS
```

---

# 7. What Does the Presentation Layer Do?

### On-Point Answer

The Presentation Layer handles data representation.

It may deal with:

* Encoding
* Encryption
* Decryption
* Compression
* Serialization formats

### Memory

```text
Presentation
→ How data is represented
```

---

# 8. What Does the Session Layer Do?

### On-Point Answer

The Session Layer manages communication sessions between applications.

Responsibilities may include:

* Establish session
* Maintain session
* Terminate session
* Synchronization

### Memory

```text
Session
→ Manage conversation
```

---

# 9. What Does the Transport Layer Do?

### On-Point Answer

The Transport Layer provides end-to-end communication between applications.

Important protocols:

```text
TCP
UDP
```

Responsibilities include:

* Segmentation
* Reliability
* Flow control
* Port numbers
* Error recovery

---

# 10. What Does the Network Layer Do?

### On-Point Answer

The Network Layer is responsible for logical addressing and routing packets between networks.

Main protocol:

```text
IP
```

Important concept:

```text
IP Address
```

Devices:

```text
Router
```

---

# 11. What Does the Data Link Layer Do?

### On-Point Answer

The Data Link Layer provides communication between devices on the same local network.

It works with:

```text
MAC Addresses
Frames
Ethernet
Switches
```

---

# 12. What Does the Physical Layer Do?

### On-Point Answer

The Physical Layer transmits raw bits through the physical medium.

Examples:

```text
Electrical Signals
Fiber Optic Signals
Radio Waves
Cables
```

---

# 13. OSI Layer → Main Concept Mapping

```text
Application
→ User-facing network services

Presentation
→ Data format / encryption

Session
→ Communication session

Transport
→ Process-to-process delivery

Network
→ IP + Routing

Data Link
→ MAC + Frames

Physical
→ Bits + Signals
```

---

# 14. What is the TCP/IP Model?

### On-Point Answer

The TCP/IP model is the practical networking model used on the Internet.

Common 4-layer version:

```text
Application
Transport
Internet
Network Access
```

---

# 15. OSI vs TCP/IP

| OSI                               | TCP/IP                        |
| --------------------------------- | ----------------------------- |
| 7 layers                          | Usually 4 layers              |
| Conceptual reference model        | Practical Internet model      |
| Presentation and Session separate | Included in Application layer |
| Network layer                     | Internet layer                |
| Data Link + Physical separate     | Network Access layer          |

---

# 16. TCP/IP Layer Mapping

```text
OSI Application
OSI Presentation
OSI Session
        ↓
TCP/IP Application

OSI Transport
        ↓
TCP/IP Transport

OSI Network
        ↓
TCP/IP Internet

OSI Data Link
OSI Physical
        ↓
TCP/IP Network Access
```

---

# 17. What is an IP Address?

### On-Point Answer

An IP address is a logical address used to identify a device or network interface and route packets across networks.

Example:

```text
192.168.1.10
```

---

# 18. What is IPv4?

### On-Point Answer

IPv4 uses a 32-bit address.

Example:

```text
192.168.1.1
```

IPv4 address space:

```text
2^32 addresses
```

approximately 4.3 billion addresses.

---

# 19. What is IPv6?

### On-Point Answer

IPv6 uses a 128-bit address and was introduced mainly because IPv4 addresses are limited.

Example:

```text
2001:db8::1
```

Advantages include:

* Much larger address space
* Improved addressing design
* Better support for modern networking

---

# 20. IPv4 vs IPv6

| IPv4                         | IPv6                          |
| ---------------------------- | ----------------------------- |
| 32-bit                       | 128-bit                       |
| Around 4.3 billion addresses | Extremely large address space |
| Dotted decimal               | Hexadecimal                   |
| Example: `192.168.1.1`       | Example: `2001:db8::1`        |

---

# 21. What is a MAC Address?

### On-Point Answer

A MAC address is a link-layer address used for communication on the local network.

Example:

```text
00:1A:2B:3C:4D:5E
```

### Memory

```text
IP
→ Logical/network addressing

MAC
→ Local link addressing
```

---

# 22. IP Address vs MAC Address

| IP Address           | MAC Address                                              |
| -------------------- | -------------------------------------------------------- |
| Logical address      | Link-layer address                                       |
| Used across networks | Used on local link                                       |
| Can change           | Usually tied to interface, though can be changed/spoofed |
| Used by routers      | Used by switches/local Ethernet                          |

---

# 23. What is a Port Number?

### On-Point Answer

A port number identifies a specific application or service on a machine.

Example:

```text
IP Address
→ Which machine?

Port
→ Which application/service?
```

Example:

```text
192.168.1.10:8080
```

---

# 24. Common Port Numbers

```text
HTTP   → 80
HTTPS  → 443
SSH    → 22
FTP    → 21
DNS    → 53
SMTP   → 25
MySQL  → 3306
PostgreSQL → 5432
```

---

# 25. What is a Socket?

### On-Point Answer

A socket is an endpoint for network communication.

It is commonly identified by:

```text
IP Address + Port Number
```

Example:

```text
10.0.0.5:8080
```

---

# 26. What is TCP?

TCP stands for:

> Transmission Control Protocol

### On-Point Answer

TCP is a connection-oriented and reliable transport protocol.

It provides:

* Reliable delivery
* Ordered delivery
* Retransmission
* Flow control
* Congestion control
* Error detection

---

# 27. What is UDP?

UDP stands for:

> User Datagram Protocol

### On-Point Answer

UDP is a connectionless transport protocol with low overhead.

It does not inherently guarantee:

* Delivery
* Ordering
* Retransmission

Common use cases:

```text
DNS
VoIP
Gaming
Live Streaming
```

---

# 28. TCP vs UDP

| TCP                      | UDP                        |
| ------------------------ | -------------------------- |
| Connection-oriented      | Connectionless             |
| Reliable                 | Best-effort                |
| Ordered delivery         | No ordering guarantee      |
| Retransmission           | No built-in retransmission |
| More overhead            | Less overhead              |
| Slower in many scenarios | Lower latency/overhead     |
| Web, file transfer       | Streaming, gaming, DNS     |

### Memory

```text
TCP
→ Reliability

UDP
→ Speed / Low overhead
```

---

# 29. Is UDP Always Faster Than TCP?

### On-Point Answer

UDP has less protocol overhead, but saying it is always faster is too absolute.

Actual performance depends on:

* Network conditions
* Application behavior
* Reliability requirements
* Packet loss

---

# 30. What is the TCP Three-Way Handshake?

### On-Point Answer

TCP uses a three-way handshake to establish a connection.

```text
Client            Server

SYN      -------->

         <-------- SYN-ACK

ACK      -------->
```

After this, the TCP connection is established.

---

# 31. Why Do We Need the Three-Way Handshake?

### On-Point Answer

It allows both sides to:

* Confirm connectivity
* Synchronize sequence numbers
* Confirm both sides are ready to communicate

### Memory

```text
SYN
SYN-ACK
ACK
```

---

# 32. What is TCP Connection Termination?

TCP connection termination commonly uses a four-step exchange.

```text
Client          Server

FIN    -------->

       <-------- ACK

       <-------- FIN

ACK    -------->
```

---

# 33. Why Four Steps for TCP Termination?

### On-Point Answer

TCP is full duplex.

Each direction of communication is closed independently.

So one side can stop sending while the other side may still have data to send.

---

# 34. What is a Sequence Number in TCP?

### On-Point Answer

TCP sequence numbers help track byte ordering and detect missing data.

They allow the receiver to reconstruct data in the correct order.

---

# 35. What is an Acknowledgment Number?

### On-Point Answer

An acknowledgment number indicates the next byte the receiver expects.

It confirms successful receipt of previous data.

---

# 36. What is Retransmission?

### On-Point Answer

If TCP believes data was lost, it retransmits the missing data.

This contributes to TCP reliability.

---

# 37. What is Flow Control?

### On-Point Answer

Flow control prevents a fast sender from overwhelming a slow receiver.

TCP commonly uses a receiver-advertised window.

### Memory

```text
Sender too fast
      ↓
Receiver overwhelmed
      ↓
Flow Control
```

---

# 38. What is Congestion Control?

### On-Point Answer

Congestion control prevents too much traffic from overwhelming the network.

It adjusts how much data a sender injects into the network based on network conditions.

---

# 39. Flow Control vs Congestion Control

```text
Flow Control
→ Protect receiver

Congestion Control
→ Protect network
```

This is a very common interview question.

---

# 40. What is HTTP?

HTTP stands for:

> Hypertext Transfer Protocol

### On-Point Answer

HTTP is an application-layer protocol used for communication between clients and servers.

Example:

```text
Browser
  ↓
HTTP Request
  ↓
Server
  ↓
HTTP Response
```

---

# 41. What is HTTPS?

### On-Point Answer

HTTPS is HTTP secured using TLS.

It provides:

* Encryption
* Integrity
* Server authentication

### Memory

```text
HTTPS
=
HTTP
+
TLS
```

---

# 42. HTTP vs HTTPS

| HTTP                           | HTTPS                                        |
| ------------------------------ | -------------------------------------------- |
| Unencrypted application data   | Encrypted using TLS                          |
| Port 80 commonly               | Port 443 commonly                            |
| No built-in transport security | Confidentiality + integrity + authentication |

---

# 43. What is TLS?

TLS stands for:

> Transport Layer Security

### On-Point Answer

TLS is a security protocol used to protect data in transit.

It provides:

* Encryption
* Integrity
* Authentication

HTTPS uses TLS.

---

# 44. What Happens When You Enter a URL in a Browser?

This is one of the most important networking interview questions.

### On-Point Flow

```text
1. Browser parses URL

2. DNS resolves domain name to IP address

3. Client connects to server
   → usually TCP
   → or QUIC for HTTP/3

4. If HTTPS:
   TLS handshake occurs

5. Browser sends HTTP request

6. Server processes request

7. Server sends HTTP response

8. Browser renders content
```

---

# 45. Example: Entering `https://example.com`

Conceptual flow:

```text
example.com
    ↓
DNS Lookup
    ↓
IP Address
    ↓
Connect to server
    ↓
TLS Handshake
    ↓
HTTP Request
    ↓
Server Response
    ↓
Browser Rendering
```

---

# 46. What is DNS?

DNS stands for:

> Domain Name System

### On-Point Answer

DNS translates human-readable domain names into IP addresses.

Example:

```text
google.com
    ↓
DNS
    ↓
IP Address
```

### Memory

```text
DNS
→ Internet's naming system
```

---

# 47. Why Do We Need DNS?

### On-Point Answer

Humans remember names like:

```text
google.com
```

more easily than IP addresses.

DNS maps names to network addresses.

---

# 48. What Happens During DNS Resolution?

Simplified flow:

```text
Browser/OS Cache
      ↓
DNS Resolver
      ↓
Root Server
      ↓
TLD Server
      ↓
Authoritative DNS Server
      ↓
IP Address
```

Not every lookup reaches all levels because caching may return the result earlier.

---

# 49. What is a DNS Resolver?

### On-Point Answer

A DNS resolver receives DNS queries from clients and performs or coordinates the lookup needed to return the DNS result.

---

# 50. What is a DNS Record?

Common DNS records:

```text
A
AAAA
CNAME
MX
NS
TXT
```

---

# 51. What is an A Record?

### On-Point Answer

An A record maps a domain name to an IPv4 address.

```text
example.com
→ IPv4 address
```

---

# 52. What is an AAAA Record?

### On-Point Answer

An AAAA record maps a domain name to an IPv6 address.

---

# 53. What is CNAME?

### On-Point Answer

A CNAME record maps one domain name to another canonical domain name.

Example:

```text
www.example.com
→ example.com
```

---

# 54. What is an MX Record?

### On-Point Answer

An MX record specifies the mail server responsible for receiving email for a domain.

---

# 55. What is ARP?

ARP stands for:

> Address Resolution Protocol

### On-Point Answer

ARP is used in IPv4 local networks to map an IP address to a MAC address.

Example:

```text
IP Address
    ↓
ARP
    ↓
MAC Address
```

---

# 56. Why Do We Need ARP?

Suppose a machine wants to send data to another machine on the same LAN.

It knows:

```text
Destination IP
```

But Ethernet delivery needs:

```text
Destination MAC
```

ARP helps find that MAC address.

---

# 57. DNS vs ARP

```text
DNS
→ Domain name → IP Address

ARP
→ IPv4 Address → MAC Address
```

Very useful distinction.

---

# 58. What is a Router?

### On-Point Answer

A router forwards packets between different networks.

It primarily makes forwarding decisions using IP addresses.

### Memory

```text
Router
→ Network to Network
```

---

# 59. What is a Switch?

### On-Point Answer

A switch connects devices within a local network and forwards Ethernet frames based primarily on MAC addresses.

### Memory

```text
Switch
→ Device to Device inside LAN
```

---

# 60. Router vs Switch

| Router            | Switch                  |
| ----------------- | ----------------------- |
| Connects networks | Connects devices in LAN |
| Uses IP addresses | Uses MAC addresses      |
| Network Layer     | Mainly Data Link Layer  |
| Routes packets    | Forwards frames         |

---

# 61. What is a Hub?

### On-Point Answer

A hub is a simple networking device that sends incoming data to all connected ports.

It does not intelligently forward data based on MAC addresses.

---

# 62. Hub vs Switch

```text
Hub
→ Broadcasts to all ports

Switch
→ Sends frame toward relevant destination port based on learned MAC addresses
```

---

# 63. What is a LAN?

LAN stands for:

> Local Area Network

### On-Point Answer

A LAN connects devices within a limited geographical area.

Examples:

```text
Home
Office
College Lab
```

---

# 64. What is a WAN?

WAN stands for:

> Wide Area Network

### On-Point Answer

A WAN connects networks across large geographic areas.

The Internet is the largest example.

---

# 65. LAN vs WAN

```text
LAN
→ Small/local area

WAN
→ Large geographical area
```

---

# 66. What is a Subnet?

### On-Point Answer

A subnet is a logical division of an IP network.

Subnetting helps:

* Organize networks
* Reduce broadcast scope
* Improve address management
* Improve routing design

---

# 67. What is a Subnet Mask?

### On-Point Answer

A subnet mask identifies which part of an IPv4 address represents the network and which part represents the host.

Example:

```text
IP:
192.168.1.10

Mask:
255.255.255.0
```

Equivalent:

```text
192.168.1.10/24
```

---

# 68. What Does `/24` Mean?

### On-Point Answer

`/24` means the first 24 bits belong to the network prefix.

Example:

```text
192.168.1.0/24
```

typically has:

```text
256 total addresses
```

with some addresses reserved for network/broadcast in traditional IPv4 subnetting.

---

# 69. What is CIDR?

CIDR stands for:

> Classless Inter-Domain Routing

### On-Point Answer

CIDR represents network prefixes using slash notation.

Example:

```text
10.0.0.0/8
192.168.1.0/24
```

---

# 70. What is a Default Gateway?

### On-Point Answer

A default gateway is the router a device sends packets to when the destination is outside its local network.

Flow:

```text
Laptop
  ↓
Destination outside LAN?
  ↓
Default Gateway
  ↓
Other Network / Internet
```

---

# 71. What is NAT?

NAT stands for:

> Network Address Translation

### On-Point Answer

NAT translates private IP addresses into public IP addresses and vice versa.

It is commonly used so multiple devices can share one public IP.

---

# 72. Why Do We Need NAT?

### On-Point Answer

NAT helps conserve IPv4 addresses and allows private networks to communicate with external networks.

Example:

```text
Phone   → 192.168.1.2
Laptop  → 192.168.1.3
TV      → 192.168.1.4

        ↓ Router/NAT

One Public IP
```

---

# 73. What are Private IP Addresses?

Common private IPv4 ranges:

```text
10.0.0.0/8

172.16.0.0/12

192.168.0.0/16
```

These are not globally routed on the public Internet.

---

# 74. Private IP vs Public IP

```text
Private IP
→ Used inside local/private network

Public IP
→ Routable on public Internet
```

---

# 75. What is DHCP?

DHCP stands for:

> Dynamic Host Configuration Protocol

### On-Point Answer

DHCP automatically assigns network configuration to devices.

It may provide:

* IP address
* Subnet mask
* Default gateway
* DNS server

---

# 76. DHCP Process

Common memory sequence:

```text
DORA

Discover
Offer
Request
Acknowledge
```

---

# 77. What is ICMP?

ICMP stands for:

> Internet Control Message Protocol

### On-Point Answer

ICMP is used for network control and diagnostic messages.

Example:

```text
ping
```

uses ICMP Echo Request / Echo Reply.

---

# 78. What is Ping?

### On-Point Answer

Ping checks whether a destination is reachable and measures round-trip time using ICMP messages.

---

# 79. What is Traceroute?

### On-Point Answer

Traceroute helps identify the path packets take through routers toward a destination.

It relies on TTL / Hop Limit behavior and ICMP responses, though implementation differs by OS.

---

# 80. What is TTL?

TTL stands for:

> Time To Live

### On-Point Answer

TTL limits how many router hops an IP packet can traverse.

Each router decreases the TTL.

When it reaches zero, the packet is discarded.

### Why?

To prevent packets from circulating forever due to routing loops.

---

# 81. What is a Packet?

### On-Point Answer

A packet is a unit of data used at the network layer.

In simple terms:

```text
Data
+
Network-layer headers
=
Packet
```

---

# 82. What is a Frame?

### On-Point Answer

A frame is a Data Link Layer unit used for transmission on a local link.

It may contain:

```text
Source MAC
Destination MAC
Payload
Error-checking information
```

---

# 83. Segment vs Packet vs Frame

```text
Transport Layer
→ Segment (TCP) / Datagram (UDP)

Network Layer
→ Packet

Data Link Layer
→ Frame

Physical Layer
→ Bits
```

---

# 84. What is Encapsulation?

### On-Point Answer

Encapsulation is the process of adding protocol headers as data moves down the network stack.

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

---

# 85. What is Decapsulation?

### On-Point Answer

Decapsulation is the reverse process at the receiver.

```text
Bits
 ↓
Frame
 ↓
Packet
 ↓
Segment
 ↓
Application Data
```

---

# 86. What is Bandwidth?

### On-Point Answer

Bandwidth is the maximum theoretical data-transfer capacity of a network link.

Example:

```text
100 Mbps
1 Gbps
```

---

# 87. What is Throughput?

### On-Point Answer

Throughput is the actual amount of useful data transferred over a network in a given time.

### Memory

```text
Bandwidth
→ Maximum capacity

Throughput
→ Actual achieved rate
```

---

# 88. What is Latency?

### On-Point Answer

Latency is the delay taken for data to travel from source to destination.

It may include:

* Propagation delay
* Transmission delay
* Processing delay
* Queueing delay

---

# 89. Bandwidth vs Latency

```text
Bandwidth
→ How much data can flow

Latency
→ How long data takes to travel
```

Analogy:

```text
Bandwidth
→ Width of road

Latency
→ Travel time
```

---

# 90. What is Packet Loss?

### On-Point Answer

Packet loss occurs when packets fail to reach their destination.

Possible causes:

* Network congestion
* Faulty hardware
* Wireless interference
* Routing issues

---

# 91. What is Jitter?

### On-Point Answer

Jitter is variation in packet delay over time.

It matters especially for:

* Voice calls
* Video calls
* Real-time streaming

---

# 92. What is a URL?

URL stands for:

> Uniform Resource Locator

Example:

```text
https://example.com:443/api/users?id=10
```

Parts:

```text
https
→ Scheme

example.com
→ Host

443
→ Port

/api/users
→ Path

id=10
→ Query Parameter
```

---

# 93. What is a URI?

URI stands for:

> Uniform Resource Identifier

### On-Point Answer

A URI identifies a resource.

A URL is a type of URI that also tells us how/location to access the resource.

For interviews:

```text
URL
→ Location/address of resource

URI
→ Broader identifier concept
```

---

# 94. What are HTTP Methods?

Common methods:

```text
GET
POST
PUT
PATCH
DELETE
HEAD
OPTIONS
```

---

# 95. What is GET?

### On-Point Answer

`GET` is used to retrieve a resource.

Example:

```http
GET /users/10
```

---

# 96. What is POST?

### On-Point Answer

`POST` is commonly used to submit data or create a new resource.

Example:

```http
POST /users
```

---

# 97. PUT vs PATCH

### PUT

Commonly used for complete replacement/update of a resource representation.

### PATCH

Used for partial update.

### Memory

```text
PUT
→ Replace/update whole representation

PATCH
→ Partial update
```

Actual API semantics depend on API design.

---

# 98. What is DELETE?

### On-Point Answer

`DELETE` requests deletion of a resource.

Example:

```http
DELETE /users/10
```

---

# 99. What is Idempotency?

### On-Point Answer

An operation is idempotent when performing the same request multiple times has the same intended effect as performing it once.

Common examples:

```text
GET
PUT
DELETE
```

are generally designed to be idempotent.

`POST` is generally not assumed to be idempotent.

---

# 100. Common HTTP Status Codes

## 2xx — Success

```text
200 → OK
201 → Created
204 → No Content
```

## 3xx — Redirection

```text
301 → Moved Permanently
302 → Found / Temporary Redirect
304 → Not Modified
```

## 4xx — Client Errors

```text
400 → Bad Request
401 → Unauthorized
403 → Forbidden
404 → Not Found
409 → Conflict
429 → Too Many Requests
```

## 5xx — Server Errors

```text
500 → Internal Server Error
502 → Bad Gateway
503 → Service Unavailable
504 → Gateway Timeout
```

---

# 101. 401 vs 403

Very common backend interview question.

```text
401 Unauthorized
→ Authentication is missing/invalid

403 Forbidden
→ Identity may be known, but access is not allowed
```

### Memory

```text
401
→ Who are you?

403
→ I know who you are, but you cannot access this.
```

---

# 102. 200 vs 201 vs 204

```text
200
→ Successful request with response

201
→ Resource created successfully

204
→ Successful request but no response body
```

---

# 103. What is Statelessness in HTTP?

### On-Point Answer

HTTP is stateless because each request should contain enough information for the server to understand and process it independently.

The protocol itself does not require the server to remember previous requests.

---

# 104. If HTTP is Stateless, How Do Login Sessions Work?

### On-Point Answer

Applications add state-management mechanisms such as:

* Cookies
* Session IDs
* Tokens
* JWTs

Example:

```text
Login
 ↓
Server issues session/token
 ↓
Client sends it with future requests
```

---

# 105. What is a Cookie?

### On-Point Answer

A cookie is small data stored by the browser and sent with matching HTTP requests according to cookie rules.

Cookies are commonly used for:

* Sessions
* Preferences
* Authentication-related state

---

# 106. What is a Session?

### On-Point Answer

A session is server-side state associated with a particular client.

Common flow:

```text
Login
 ↓
Server creates session
 ↓
Session ID sent to client
 ↓
Client sends Session ID
 ↓
Server retrieves session
```

---

# 107. Cookie vs Session

```text
Cookie
→ Stored on client

Session
→ Usually stored on server

Cookie may contain:
→ Session ID
```

---

# 108. What is a Proxy?

### On-Point Answer

A proxy is an intermediary between a client and another server.

Flow:

```text
Client
  ↓
Proxy
  ↓
Destination Server
```

---

# 109. What is a Forward Proxy?

### On-Point Answer

A forward proxy represents clients when accessing external servers.

```text
Clients
   ↓
Forward Proxy
   ↓
Internet
```

---

# 110. What is a Reverse Proxy?

### On-Point Answer

A reverse proxy sits in front of backend servers and receives requests on their behalf.

```text
Client
   ↓
Reverse Proxy
   ↓
Backend Servers
```

Uses:

* Load balancing
* TLS termination
* Caching
* Routing
* Security

---

# 111. Forward Proxy vs Reverse Proxy

```text
Forward Proxy
→ Represents clients

Reverse Proxy
→ Represents servers
```

---

# 112. What is a Load Balancer?

### On-Point Answer

A load balancer distributes incoming requests across multiple backend servers.

Example:

```text
             ┌→ Server 1
Client → LB ─┼→ Server 2
             └→ Server 3
```

Purpose:

* Scalability
* Availability
* Better resource utilization

---

# 113. Layer 4 vs Layer 7 Load Balancer

### Layer 4

Works mainly using:

```text
IP
Port
TCP/UDP
```

### Layer 7

Understands application protocols such as HTTP.

Can route based on:

```text
URL path
Host
Headers
Cookies
```

---

# 114. What is a Firewall?

### On-Point Answer

A firewall controls network traffic based on security rules.

It can allow or block traffic based on:

* IP
* Port
* Protocol
* Connection state
* Application-layer rules in advanced systems

---

# 115. What is a CDN?

CDN stands for:

> Content Delivery Network

### On-Point Answer

A CDN caches and serves content from geographically distributed edge servers closer to users.

Benefits:

* Lower latency
* Reduced origin-server load
* Better availability
* Faster content delivery

---

# 116. What is Caching?

### On-Point Answer

Caching stores frequently used data closer to where it is needed so future requests can be served faster.

Examples:

```text
Browser Cache
CDN Cache
DNS Cache
Proxy Cache
```

---

# 117. What is WebSocket?

### On-Point Answer

WebSocket provides a persistent, full-duplex communication channel between client and server.

After connection establishment:

```text
Client ⇄ Server
```

Both can send data at any time.

Use cases:

* Chat
* Real-time notifications
* Live dashboards
* Multiplayer applications

---

# 118. HTTP vs WebSocket

| HTTP                             | WebSocket                         |
| -------------------------------- | --------------------------------- |
| Request-response model           | Persistent full-duplex connection |
| Client usually initiates request | Both sides can send anytime       |
| Good for REST APIs               | Good for real-time communication  |

---

# 119. What is Polling?

### On-Point Answer

Polling means the client repeatedly asks the server for new data.

Example:

```text
Client → Any update?
Client → Any update?
Client → Any update?
```

---

# 120. Polling vs WebSocket

```text
Polling
→ Repeated requests

WebSocket
→ Persistent connection
```

WebSocket is often more efficient for frequent real-time updates.

---

# 121. What is Keep-Alive?

### On-Point Answer

Keep-alive allows a network connection to remain open and be reused instead of creating a new connection for every request.

This reduces connection-establishment overhead.

---

# 122. What is HTTP/1.1?

### On-Point Answer

HTTP/1.1 supports persistent connections and request/response communication over TCP.

A major limitation is head-of-line behavior at the application/request level when pipelining/multiple requests are involved.

---

# 123. What is HTTP/2?

### On-Point Answer

HTTP/2 improves efficiency by supporting multiplexing multiple streams over one TCP connection.

Features include:

* Multiplexing
* Header compression
* Binary framing

---

# 124. What is HTTP/3?

### On-Point Answer

HTTP/3 uses QUIC instead of TCP.

QUIC runs over UDP and provides:

* Secure transport
* Multiplexed streams
* Faster connection establishment in many cases
* Reduced transport-level head-of-line blocking between streams

---

# 125. HTTP/1.1 vs HTTP/2 vs HTTP/3

```text
HTTP/1.1
→ TCP
→ Simpler request/response connections

HTTP/2
→ TCP
→ Multiplexing

HTTP/3
→ QUIC over UDP
→ Multiplexing without TCP-level HOL blocking between streams
```

---

# 126. What is Head-of-Line Blocking?

### On-Point Answer

Head-of-line blocking happens when one delayed item prevents following items from being processed promptly.

In TCP, lost data can delay later data delivery because TCP delivers an ordered byte stream.

---

# 127. What is a Client-Server Architecture?

### On-Point Answer

In client-server architecture:

* Client sends requests
* Server processes requests
* Server sends responses

Example:

```text
Browser
   ↓
Backend Server
   ↓
Database
```

---

# 128. What is Peer-to-Peer Networking?

### On-Point Answer

In peer-to-peer networking, devices can communicate directly and act as both clients and servers.

Example:

```text
Peer A ⇄ Peer B
```

---

# 129. Client-Server vs Peer-to-Peer

```text
Client-Server
→ Centralized server

Peer-to-Peer
→ Peers communicate directly
```

---

# 130. What is Network Topology?

### On-Point Answer

Network topology describes how devices are connected.

Common types:

```text
Bus
Star
Ring
Mesh
Tree
```

---

# 131. What is Star Topology?

### On-Point Answer

In star topology, all devices connect to a central networking device.

```text
       PC
       |
PC — Switch — PC
       |
      PC
```

Common in Ethernet LANs.

---

# 132. What is a Broadcast?

### On-Point Answer

Broadcast sends data to all devices in a broadcast domain.

Example:

ARP requests in IPv4 Ethernet LANs commonly use broadcast.

---

# 133. What is Unicast?

### On-Point Answer

Unicast means one sender communicates with one specific receiver.

```text
A → B
```

---

# 134. What is Multicast?

### On-Point Answer

Multicast sends traffic to a selected group of receivers.

```text
A → Group
```

---

# 135. Unicast vs Broadcast vs Multicast

```text
Unicast
→ One to one

Broadcast
→ One to all in broadcast domain

Multicast
→ One to selected group
```

---

# 136. What is MTU?

MTU stands for:

> Maximum Transmission Unit

### On-Point Answer

MTU is the maximum packet/frame payload size that can be transmitted over a link without needing fragmentation at that layer.

Ethernet commonly uses an IP MTU of:

```text
1500 bytes
```

---

# 137. What is Fragmentation?

### On-Point Answer

Fragmentation occurs when an IP packet is too large for the network path/link MTU and is split into smaller pieces where supported.

IPv4 routers may fragment in some cases.

IPv6 routers do not perform router fragmentation; endpoints handle packet sizing differently.

---

# 138. What is Routing?

### On-Point Answer

Routing is the process of selecting a path for packets to travel from source network to destination network.

Routers use routing tables.

---

# 139. What is a Routing Table?

### On-Point Answer

A routing table contains information about where packets should be forwarded.

Typical entries include:

```text
Destination Network
Next Hop
Interface
Metric
```

---

# 140. What is Default Route?

### On-Point Answer

A default route is used when no more specific routing-table entry matches the destination.

IPv4 representation:

```text
0.0.0.0/0
```

---

# Most Important Comparison Questions

## TCP vs UDP

```text
TCP
→ Reliable + ordered + connection-oriented

UDP
→ Connectionless + low overhead
```

---

## IP vs MAC Address

```text
IP
→ Network-level logical address

MAC
→ Local-link address
```

---

## Router vs Switch

```text
Router
→ Connects networks using IP

Switch
→ Connects LAN devices using MAC
```

---

## HTTP vs HTTPS

```text
HTTP
→ Application protocol

HTTPS
→ HTTP secured by TLS
```

---

## HTTP vs WebSocket

```text
HTTP
→ Request-response

WebSocket
→ Persistent full-duplex
```

---

## Flow Control vs Congestion Control

```text
Flow Control
→ Protect receiver

Congestion Control
→ Protect network
```

---

## DNS vs ARP

```text
DNS
→ Name to IP

ARP
→ IPv4 to MAC on LAN
```

---

## Bandwidth vs Throughput

```text
Bandwidth
→ Maximum capacity

Throughput
→ Actual achieved transfer rate
```

---

## Bandwidth vs Latency

```text
Bandwidth
→ How much

Latency
→ How long
```

---

## Forward Proxy vs Reverse Proxy

```text
Forward Proxy
→ Represents client

Reverse Proxy
→ Represents server
```

---

# Top 30 CN Questions to Prioritize

If preparation time is limited, master these first:

```text
1. What is a Computer Network?

2. What is a Protocol?

3. OSI Model

4. TCP/IP Model

5. OSI vs TCP/IP

6. IP Address

7. MAC Address

8. IP vs MAC

9. Port Number

10. TCP

11. UDP

12. TCP vs UDP

13. TCP Three-Way Handshake

14. TCP Connection Termination

15. Flow Control vs Congestion Control

16. HTTP

17. HTTPS

18. HTTP vs HTTPS

19. What happens when you enter a URL?

20. DNS

21. ARP

22. Router vs Switch

23. NAT

24. DHCP

25. Subnet / Subnet Mask

26. HTTP Methods

27. Common HTTP Status Codes

28. 401 vs 403

29. WebSocket

30. Load Balancer / Reverse Proxy
```

---

# Most Common Interview Traps

## Trap 1

### Wrong

```text
MAC Address is used across the Internet for end-to-end routing.
```

### Correct

```text
IP
→ Used for routing across networks

MAC
→ Used for local-link delivery
```

---

## Trap 2

### Wrong

```text
UDP guarantees faster communication.
```

### Correct

```text
UDP has lower protocol overhead,
but actual performance depends on the application and network.
```

---

## Trap 3

### Wrong

```text
HTTPS is a completely different protocol from HTTP.
```

### Better

```text
HTTPS
=
HTTP carried over TLS-protected transport
```

---

## Trap 4

### Wrong

```text
DNS directly gives us a MAC address.
```

### Correct

```text
DNS
→ Domain → IP

ARP
→ IPv4 → MAC on local network
```

---

## Trap 5

### Wrong

```text
Router uses MAC addresses for Internet routing.
```

### Correct

```text
Router routing decisions
→ IP / network prefixes

Local-link forwarding
→ MAC addresses
```

---

## Trap 6

### Wrong

```text
401 means user is authenticated but doesn't have permission.
```

### Correct

```text
401
→ Authentication missing/invalid

403
→ Authenticated/identified but not allowed
```

---

## Trap 7

### Wrong

```text
HTTP is stateful.
```

### Correct

```text
HTTP itself is stateless.

Applications add state using:
Cookies
Sessions
Tokens
```

---

## Trap 8

### Wrong

```text
Bandwidth and latency are the same.
```

### Correct

```text
Bandwidth
→ Capacity

Latency
→ Delay
```

---

# Interview Wording → Networking Concept

| Interview Wording                            | Think              |
| -------------------------------------------- | ------------------ |
| Reliable delivery                            | TCP                |
| Low-latency / low-overhead transport         | UDP                |
| Domain to IP                                 | DNS                |
| IPv4 to MAC                                  | ARP                |
| Identify application on host                 | Port               |
| Identify machine/network interface logically | IP                 |
| Local-link identifier                        | MAC                |
| Connect networks                             | Router             |
| Connect LAN devices                          | Switch             |
| Automatically get IP configuration           | DHCP               |
| Private → public address translation         | NAT                |
| Secure HTTP                                  | HTTPS / TLS        |
| Establish TCP connection                     | 3-way handshake    |
| Protect receiver                             | Flow control       |
| Protect network                              | Congestion control |
| Client requests server                       | HTTP               |
| Persistent two-way channel                   | WebSocket          |
| Distribute requests                          | Load Balancer      |
| Server-side intermediary                     | Reverse Proxy      |
| Client-side intermediary                     | Forward Proxy      |
| Actual data-transfer rate                    | Throughput         |
| Delay                                        | Latency            |
| Maximum link capacity                        | Bandwidth          |

---

# Full Web Request Flow

This is one of the most important flows to remember.

```text
User enters:
https://example.com
        ↓
Browser checks cache
        ↓
DNS resolves domain
        ↓
Gets server IP
        ↓
Routing sends packets toward server
        ↓
Transport connection established
        ↓
For HTTPS:
TLS handshake
        ↓
HTTP request sent
        ↓
Reverse Proxy / Load Balancer
        ↓
Backend Server
        ↓
Database / Other Services
        ↓
HTTP Response
        ↓
Browser receives response
        ↓
Browser renders page
```

---

# Backend Request Flow

For Java Backend interviews, remember this:

```text
Client
   ↓
DNS
   ↓
Internet
   ↓
Load Balancer / Reverse Proxy
   ↓
Spring Boot Backend
   ↓
Controller
   ↓
Service
   ↓
Repository
   ↓
Database
   ↓
Response
   ↓
Client
```

---

# Final Computer Networks Memory Map

```text
Computer Networks
│
├── Models
│   ├── OSI
│   └── TCP/IP
│
├── Addressing
│   ├── IP
│   ├── MAC
│   ├── Port
│   ├── Subnet
│   └── CIDR
│
├── Transport
│   ├── TCP
│   ├── UDP
│   ├── Handshake
│   ├── Flow Control
│   └── Congestion Control
│
├── Application Protocols
│   ├── HTTP
│   ├── HTTPS
│   ├── DNS
│   ├── DHCP
│   └── WebSocket
│
├── Network Devices
│   ├── Router
│   ├── Switch
│   ├── Hub
│   ├── Proxy
│   └── Load Balancer
│
├── Network Services
│   ├── NAT
│   ├── DNS
│   ├── DHCP
│   └── CDN
│
└── Performance
    ├── Bandwidth
    ├── Throughput
    ├── Latency
    ├── Jitter
    └── Packet Loss
```

---

# One-Line Revision Sheet

```text
Network
→ Connected devices exchanging data

Protocol
→ Rules of communication

OSI
→ 7-layer reference model

TCP/IP
→ Practical Internet model

IP
→ Logical network address

MAC
→ Local-link address

Port
→ Identifies application/service

TCP
→ Reliable + ordered

UDP
→ Connectionless + low overhead

TCP Handshake
→ SYN → SYN-ACK → ACK

Flow Control
→ Protect receiver

Congestion Control
→ Protect network

HTTP
→ Client-server application protocol

HTTPS
→ HTTP + TLS

TLS
→ Encryption + Integrity + Authentication

DNS
→ Domain → IP

ARP
→ IPv4 → MAC on LAN

Router
→ Connect networks

Switch
→ Connect devices in LAN

Subnet
→ Divide network

Gateway
→ Exit from local network

NAT
→ Private ↔ Public address translation

DHCP
→ Automatic network configuration

ICMP
→ Diagnostics/control messages

Ping
→ Reachability + RTT

TTL
→ Prevent infinite routing loops

Packet
→ Network-layer data unit

Frame
→ Data-link-layer data unit

Encapsulation
→ Add headers down the stack

Bandwidth
→ Maximum capacity

Throughput
→ Actual transfer rate

Latency
→ Delay

Jitter
→ Delay variation

Cookie
→ Client-side stored HTTP state data

Session
→ Server-side state

Proxy
→ Intermediary

Reverse Proxy
→ Represents backend servers

Load Balancer
→ Distributes traffic

WebSocket
→ Persistent full-duplex communication
```

---

# Final Interview Strategy

For every Computer Networks question, ask yourself:

```text
1. Which layer does this concept belong to?

2. What problem is it solving?

3. What identifiers are involved?
   IP?
   MAC?
   Port?

4. Is communication:
   Reliable?
   Connectionless?
   Local?
   End-to-end?

5. Can I explain the packet/request flow?
```

Example:

```text
Why TCP?
→ Need reliable ordered delivery.

How?
→ Sequence numbers + ACKs + retransmissions.

Connection setup?
→ 3-way handshake.
```

Another:

```text
Why DNS?
→ Humans use names, networks use IP addresses.

Solution?
→ Resolve domain name to IP.
```

Another:

```text
Why NAT?
→ Private devices need Internet access and IPv4 addresses are limited.

Solution?
→ Translate private addresses to public address/ports.
```

Another:

```text
Why HTTPS?
→ HTTP data should not travel in plaintext.

Solution?
→ Protect HTTP using TLS.
```

> For fresher Computer Networks interviews, focus heavily on **data flow**. If you can clearly explain how a request goes from browser → DNS → TCP/TLS → HTTP → server → response, you will naturally connect many networking concepts together.
