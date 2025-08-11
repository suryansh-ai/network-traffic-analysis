# Capture and Analyze Network Traffic Using Wireshark

## Objective
Capture live network packets on Linux using **Wireshark**, identify at least three different protocols, and analyze their packet details.

---

## Tools Used
- **Operating System:** Linux
- **Wireshark** (v4.2.5, Linux)
- **ping** command (for ICMP traffic generation)
- **Mozilla Firefox** (for HTTP & DNS traffic)
---

## Steps Followed

### 1. **Launched Wireshark** on Linux:
```bash
sudo wireshark
```
### 2. Selected the active network interface: 
```
wlan0
```
### 3. Started the capture and generated traffic by:

- Visiting http://google.com in a browser.

- Running:
```bash
ping -c 3 google.com
```
### 4. Stopped the capture after approximately 1 minute.

### 5. Applied protocol filters: 
- http
- dns 
- tcp


## Protocols Identified
| Protocol | Description                                                                                |
| -------- | ------------------------------------------------------------------------------------------ |
| **HTTP** | Hypertext Transfer Protocol – used for transferring web content between client and server. |
| **DNS**  | Domain Name System – resolves domain names to IP addresses.                                |
| **TCP**  | Transmission Control Protocol – reliable, connection-oriented protocol for data delivery.  |


## Packet Analysis
### HTTP
- Sample Packet: 1634

- Source IP: 192.168.1.35

- Destination IP: 35.186.224.24

- Protocol: HTTP

- Length: 391 bytes

- Info: GET / HTTP/1.1

- Observation: This is an HTTP GET request from your machine (192.168.1.35) to the web server (35.186.224.24) requesting the root page (/).

### DNS
- Sample Packet: 1615

- Source IP: 192.168.1.35

- Destination IP: 163.53.87.74

- Protocol: DNS

- Length: 71 bytes

- Info: Standard query 0x2042 A

- Observation: This packet is a DNS query asking for the IPv4 address (A record) of 35.186.224.24. It was sent from the client (192.168.1.35) to the DNS server (163.53.87.74) during the process of resolving a domain name before establishing a TCP connection.

### TCP
- Sample Packet: 1619

- Source IP: 192.168.1.35

- Destination IP: 35.186.224.24

- Protocol: TCP

- Length: 74 bytes

- Info: SYN - Initiates a TCP three-way handshake with the server

- Observation: This is an HTTP GET request from your machine (192.168.1.35) to the web server (35.186.224.24) requesting the root page (/).

## Traffic Summary
### During the capture:

- DNS queries were performed to resolve domain names to IP addresses.

- TCP three-way handshakes were established with web servers.

- HTTP GET requests were used to fetch web pages.

- Network activity matched typical patterns of browsing and pinging a domain.

```
## Repository Structure


basic-vulnerability-scan/
│
├── README.md
├── wireshark_scan.pcapng              
├── screenshots/                 
│   ├── ss-1.png
│   ├── ss-2.png
│   ├── ss-3.png
│   ├── ss-4.png
│   ├── ss-5.png
│   ├── ss-6.png
│   ├── ss-7.png
---

## Created By

**Name:** Suryansh Pandey

**Internship:** Cyber Security Internship – Task 5  

**Date:** [11/08/2025]
