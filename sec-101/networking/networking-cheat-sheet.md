# Networking Cheat Sheet

**Learning Path:** SEC 101  
**Platform:** TryHackMe  
**Completed:** February 2026

## What This Room Covers

A consolidated networking reference covering network identification, addressing, topologies, protocols, and the key concepts that underpin both infrastructure and security work.

## Commands / Concepts Reference

**Network Identification:**
- **IP Address** — logical address identifying a device on a network (Layer 3)
- **MAC Address** — physical address burned into the NIC, unique per device (Layer 2)
- **IPv4:** 32-bit, written as four octets (e.g. 192.168.1.10) — approximately 4.3 billion addresses
- **IPv6:** 128-bit, written in hex groups (e.g. 2001:0db8::1) — effectively unlimited

**Network Topologies:**
| Topology | Description |
|---|---|
| Star | All devices connect to a central switch — enterprise standard, easy to manage and troubleshoot |
| Bus | All devices share a single cable — obsolete, single point of failure |
| Ring | Each device connects to two others in a loop — obsolete in LANs, still used in some WANs (SONET) |
| Mesh | Every device connects to every other — used in WANs and wireless backhaul for resilience |

**Subnetting:**
- Subnets divide a network into smaller segments for efficiency and security
- CIDR notation: /24 = 254 usable hosts, /25 = 126, /26 = 62, /30 = 2 (point-to-point links)
- Subnetting separates broadcast domains — critical for controlling traffic in enterprise networks

**Key Protocols:**
| Protocol | Purpose |
|---|---|
| ARP | Maps IP addresses to MAC addresses on the local network |
| DHCP | Automatic IP address assignment (DORA process) |
| DNS | Resolves hostnames to IP addresses |
| ICMP | Network diagnostics — ping and traceroute |

**OSI Model Summary:**
| Layer | Name | Examples |
|---|---|---|
| 7 | Application | HTTP, DNS, FTP, SMTP |
| 6 | Presentation | TLS, encoding |
| 5 | Session | NetBIOS, RPC |
| 4 | Transport | TCP, UDP |
| 3 | Network | IP, ICMP, Routers |
| 2 | Data Link | Ethernet, MAC, Switches |
| 1 | Physical | Cables, WiFi radio |

**IP Packet Headers (key fields):**
- **TTL (Time to Live)** — decremented by 1 at each router hop; packet dropped at 0 (prevents loops)
- **Source IP** — where the packet originated
- **Destination IP** — where the packet is going
- **Checksum** — error detection for the header

**TCP Three-Way Handshake:**
```
Client → Server:  SYN      (I want to connect)
Server → Client:  SYN/ACK  (OK, I acknowledge)
Client → Server:  ACK      (Connection established)
```

**Common Ports:**
| Port | Protocol | Service |
|---|---|---|
| 22 | TCP | SSH |
| 25 | TCP | SMTP |
| 53 | UDP/TCP | DNS |
| 80 | TCP | HTTP |
| 110 | TCP | POP3 |
| 143 | TCP | IMAP |
| 443 | TCP | HTTPS |
| 3389 | TCP | RDP |

**Port Forwarding:** Exposes an internal service to external access by mapping an external port on the public IP to an internal IP:port. Common for hosted services and remote access.

**Firewalls:** Filter traffic at the network perimeter based on rules. Can be stateless (packet filter), stateful (tracks connection state), or application-layer (inspects Layer 7 content).

## Real World Application

This cheat sheet consolidates the networking knowledge I apply daily. The three-way handshake, port numbers, and subnetting are foundational to firewall rule creation, network troubleshooting, and security analysis at **ESW IT** and **F12.net**.

---
*This repository was structured and documented with the assistance of Claude AI (Anthropic) as part of an agentic portfolio workflow.*
