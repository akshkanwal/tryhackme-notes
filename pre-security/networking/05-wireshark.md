# Wireshark

**Learning Path:** Pre-Security  
**Platform:** TryHackMe  
**Completed:** April 2026

## What This Room Covers

Wireshark — the industry-standard open-source packet analyser. How to capture, navigate, and filter network traffic to identify protocols, diagnose issues, and investigate anomalies.

## My Key Takeaways

Wireshark is a tool I knew existed but had not used in depth before this room. As an infrastructure professional, I primarily troubleshoot at the configuration level — but packet capture is the ground truth when you need to verify what is actually being transmitted versus what should be. This room gave me a practical working knowledge of the interface and filter syntax.

## Commands / Concepts Reference

**Interface Overview — Three Panes:**
1. **Packet List** — chronological list of all captured packets with summary info (time, source, destination, protocol, length, info)
2. **Packet Details** — expandable tree showing all protocol layers for the selected packet
3. **Packet Bytes** — raw hex and ASCII representation of the selected packet

**Display Filter Syntax (examples):**
| Filter | What it shows |
|---|---|
| `ip.addr == 192.168.1.10` | All traffic to/from this IP |
| `ip.src == 10.0.0.1` | Traffic sourced from this IP |
| `tcp.port == 443` | HTTPS traffic |
| `dns` | DNS queries and responses only |
| `http` | HTTP traffic |
| `tcp.flags.syn == 1` | TCP SYN packets (connection initiations) |
| `!(arp or dns)` | Exclude ARP and DNS (reduce noise) |

**Colouring Rules:** Wireshark colour-codes traffic by protocol by default — green for TCP, blue for DNS, etc. Custom rules can highlight specific traffic patterns.

**PCAP files:** Packet captures are saved as .pcap or .pcapng files and can be shared for offline analysis.

**Important distinction:** Wireshark is a passive capture tool — it reads packets off the wire but does not alert or block. It is **not** an IDS/IPS.

## Real World Application

In MSP and consulting work, Wireshark (or similar tools) is the last resort for diagnosing network issues that cannot be explained by configuration review alone. If a client reports intermittent connectivity or a protocol is behaving unexpectedly, a packet capture at the relevant point in the network tells the exact story. This room gave me the practical foundation to conduct and interpret those captures.

---
*This repository was structured and documented with the assistance of Claude AI (Anthropic) as part of an agentic portfolio workflow.*
