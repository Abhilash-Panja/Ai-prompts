# Computer Networks Interview Preparation for Freshers

## 1. Networking Fundamentals — High Priority

1. What is a computer network, and why do we use networks?
2. What is a network protocol, and why are protocols necessary?
3. How do LAN, MAN, and WAN differ?
4. What is the difference between a client–server network and a peer-to-peer network?
5. How do the internet, an intranet, and the World Wide Web differ?
6. What are bandwidth, throughput, and latency?
7. How does bandwidth differ from throughput?
8. What are jitter and packet loss, and how do they affect a video call?
9. How do simplex, half-duplex, and full-duplex communication differ?
10. How does packet switching differ from circuit switching?
11. Why might a high-bandwidth connection still feel slow?

## 2. OSI and TCP/IP Models — High Priority

1. What are the seven layers of the OSI model, in order?
2. What is the main responsibility of each OSI layer?
3. What are the layers of the TCP/IP model, and how do they map to the OSI model?
4. How does the OSI model differ from the TCP/IP model?
5. What are encapsulation and decapsulation?
6. What are frames, packets, and segments?
7. At which layers do Ethernet, IP, TCP, UDP, HTTP, and DNS operate?
8. How do MAC addresses, IP addresses, and port numbers serve different purposes?
9. What happens to application data as it travels down the network stack?
10. How can a layered model help you troubleshoot a connection problem?

## 3. Network Devices and Local Communication — High Priority

1. How do a hub, switch, and router differ?
2. How does a switch learn which devices are reachable through its ports?
3. How does a router decide where to forward a packet?
4. What is the difference between a modem and a wireless access point?
5. What is a MAC address, and what is its role in a local network?
6. What is the difference between unicast, broadcast, and multicast?
7. What are collision domains and broadcast domains?
8. What is ARP, and why is it needed in IPv4 networks?
9. What happens when a device needs to send a packet but does not know the next hop’s MAC address?
10. When sending data to another network, does a device resolve the destination server’s MAC address or the default gateway’s MAC address?
11. Which addresses normally change when a packet passes through a router?

## 4. IP Addressing and Subnetting — High Priority

1. What is an IP address, and why is it needed?
2. How do IPv4 and IPv6 differ?
3. What is the difference between public and private IPv4 addresses?
4. What are the private IPv4 address ranges?
5. What is the difference between static and dynamic IP addressing?
6. What is a subnet mask, and how does it identify the network and host portions of an address?
7. What is CIDR notation, and what does `/24` mean?
8. Given an IPv4 address and a prefix length, how would you find the network address, broadcast address, and usable host range?
9. How would you determine whether two IPv4 addresses belong to the same subnet?
10. How would you divide a `/24` network into four equal-sized subnets?
11. What is a default gateway, and when does a device use it?
12. What are loopback and link-local addresses?
13. Can two devices have the same private IP address on different networks? What happens if they use the same address on the same local network?

## 5. Transport Layer: TCP and UDP — High Priority

1. What is the role of the transport layer?
2. What is a port number, and why is it needed in addition to an IP address?
3. What is a socket?
4. How do TCP and UDP differ?
5. What does it mean for TCP to be connection-oriented and UDP to be connectionless?
6. How does TCP establish a connection using the three-way handshake?
7. Why does TCP use a three-way handshake instead of a two-way handshake?
8. How do TCP sequence numbers and acknowledgments support reliable delivery?
9. How does TCP detect and recover from lost data?
10. How does TCP handle duplicate and out-of-order segments?
11. What is the difference between flow control and congestion control?
12. What is TCP’s sliding-window mechanism?
13. How is a TCP connection normally closed, and how do `FIN` and `RST` differ?
14. Why is TCP described as a byte stream while UDP preserves message boundaries?
15. Why might an application choose UDP even though it does not guarantee delivery?
16. Can an application build reliable communication on top of UDP?

## 6. HTTP and HTTPS — High Priority

1. What is HTTP, and what is its role in web communication?
2. What are the main parts of an HTTP request and an HTTP response?
3. What is the difference between HTTP and HTTPS?
4. What are the purposes of `GET`, `POST`, `PUT`, `PATCH`, and `DELETE`?
5. How do `PUT` and `PATCH` differ?
6. What does it mean for an HTTP method to be safe or idempotent?
7. What do the `1xx`, `2xx`, `3xx`, `4xx`, and `5xx` status-code categories represent?
8. When would you expect `200`, `201`, `204`, `301`, `302`, `400`, `401`, `403`, `404`, and `500`?
9. Why is HTTP called stateless, and how do applications maintain login state?
10. What is the difference between cookies and server-side sessions?
11. What is an HTTP persistent connection, and why is it useful?
12. What is HTTP caching, and what are the purposes of `Cache-Control`, `ETag`, and `304 Not Modified`?
13. At a basic level, how do HTTP/1.1, HTTP/2, and HTTP/3 differ?
14. Does HTTPS guarantee that a website itself is trustworthy?

## 7. DNS, DHCP, and Essential Protocols — High Priority

1. What is DNS, and why is it needed?
2. What happens during a DNS lookup when the answer is not already cached?
3. What are recursive resolvers, root servers, top-level domain servers, and authoritative name servers?
4. How does a recursive DNS query differ from an iterative query?
5. What are `A`, `AAAA`, `CNAME`, and `MX` records used for?
6. What is DNS caching, and what does a record’s TTL control?
7. Does DNS use UDP, TCP, or both?
8. What is DHCP, and what configuration can it provide to a device?
9. What are the Discover, Offer, Request, and Acknowledge steps in DHCP?
10. What is a DHCP lease, and why must it be renewed?
11. What is ICMP, and how is it used by network diagnostic tools?
12. What are the common default ports for HTTP, HTTPS, DNS, SSH, FTP, SMTP, and DHCP?

## 8. End-to-End Communication and Troubleshooting — High Priority

1. What happens from a networking perspective when you enter an HTTPS URL in a browser and press Enter?
2. How does a device decide whether to send traffic directly to a destination or through its default gateway?
3. If a server is reachable by IP address but not by hostname, what would you investigate?
4. If your device is connected to Wi-Fi but cannot access the internet, how would you troubleshoot it?
5. If a website works for others but not on your device, what would you check?
6. What does `ping` test, and what can a successful or failed result tell you?
7. How does `traceroute` or `tracert` help investigate a network path?
8. What would you use `nslookup` or `dig` to investigate?
9. How would you use `ipconfig` or `ip addr` to inspect a device’s network configuration?
10. How would you use `curl` to investigate an HTTP connection or response?
11. What is the difference between a connection timeout and a connection-refused error?
12. If `ping` succeeds but a website does not load, what could explain the problem?

## 9. Routing and NAT — Medium Priority

1. What is routing, and what information does a routing table contain?
2. How does static routing differ from dynamic routing?
3. What is a default route?
4. What is longest-prefix matching?
5. What is the purpose of IPv4’s TTL or IPv6’s Hop Limit?
6. What is NAT, and why is it commonly used?
7. How does Port Address Translation (PAT) allow multiple devices to share one public IPv4 address?
8. What is port forwarding, and when might it be needed?
9. How does NAT differ from a firewall?
10. At a basic level, how do distance-vector and link-state routing differ?

## 10. Network Security Basics — Medium Priority

1. What are confidentiality, integrity, and authentication in network communication?
2. How do encryption, hashing, and encoding differ?
3. How does symmetric encryption differ from asymmetric encryption?
4. What is TLS, and what does it protect?
5. What is a digital certificate, and what is the role of a Certificate Authority?
6. At a high level, what happens during a TLS handshake?
7. What is a firewall, and how can it filter traffic?
8. What is a man-in-the-middle attack, and how does correctly validated TLS help prevent it?
9. What is the difference between a DoS attack and a DDoS attack?
10. What is a VPN, and what traffic does it protect?

## 11. Data Link Layer and Error Handling — Medium Priority

1. What is framing, and why is it necessary?
2. How does error detection differ from error correction?
3. What are parity checks, checksums, and Cyclic Redundancy Checks (CRC)?
4. Does detecting a corrupted frame automatically mean that the frame can be repaired?
5. What is an MTU, and how does it differ from TCP’s MSS?
6. What is IP fragmentation, and why can it affect performance?
7. How do Ethernet and Wi-Fi differ in how devices access the shared medium?
8. What is the difference between CSMA/CD and CSMA/CA?
9. Why is CSMA/CD generally unnecessary on modern switched, full-duplex Ethernet links?

## 12. Application Protocols and Traffic Intermediaries — Medium Priority

1. What are the roles of SMTP, POP3, and IMAP?
2. How do POP3 and IMAP differ?
3. How do FTP, FTPS, and SFTP differ?
4. Why is SSH preferred over Telnet for remote access?
5. What is a proxy server, and how does a forward proxy differ from a reverse proxy?
6. What is a load balancer, and why do applications use one?
7. What is a Content Delivery Network (CDN), and how can it reduce loading time?
8. How does WebSocket communication differ from a typical HTTP request–response interaction?

## 13. Optional Advanced Topics — Low Priority

1. What is a VLAN, and how does it divide a switched network?
2. What is the purpose of the Spanning Tree Protocol?
3. What is BGP, and what role does it play on the internet?
4. What is TCP slow start?
5. What is head-of-line blocking, and how does its impact differ between HTTP/2 and HTTP/3?
6. What is QUIC, and why is it built on UDP?
7. What are TCP’s `TIME_WAIT` and `CLOSE_WAIT` states?
8. How does a Layer 4 load balancer differ from a Layer 7 load balancer?
9. What are the same-origin policy and CORS, and why do browsers enforce them?
10. How does IPv6 Neighbor Discovery differ from IPv4 ARP?

## Must-Prepare Checklist

- [ ] Bandwidth, throughput, latency, jitter, and packet loss.
- [ ] Packet switching vs circuit switching.
- [ ] OSI layers and their responsibilities.
- [ ] TCP/IP model and its mapping to OSI.
- [ ] Encapsulation and decapsulation.
- [ ] MAC addresses vs IP addresses vs port numbers.
- [ ] Hubs, switches, routers, and access points.
- [ ] ARP and local-network delivery.
- [ ] Public vs private IP addresses.
- [ ] IPv4 vs IPv6.
- [ ] Subnet masks and CIDR notation.
- [ ] Basic subnetting and address-range calculations.
- [ ] Default gateways and default routes.
- [ ] TCP vs UDP.
- [ ] TCP three-way handshake and connection termination.
- [ ] Sequence numbers, acknowledgments, and retransmissions.
- [ ] Flow control vs congestion control.
- [ ] Ports and sockets.
- [ ] HTTP methods and common status codes.
- [ ] HTTP vs HTTPS.
- [ ] Statelessness, cookies, and sessions.
- [ ] DNS resolution, records, and caching.
- [ ] DHCP and its four-step exchange.
- [ ] Common protocols and their default ports.
- [ ] What happens when you open a website.
- [ ] Basic troubleshooting with `ping`, `traceroute`, `nslookup`, and `curl`.
- [ ] NAT, PAT, and port forwarding.
- [ ] TLS, certificates, and firewalls.
- [ ] Error detection, MTU, and MSS.
- [ ] Forward proxies, reverse proxies, load balancers, and CDNs.
