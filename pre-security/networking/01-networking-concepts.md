# Networking Concepts

**Learning Path:** Pre-Security  
**Platform:** TryHackMe  
**Completed:** March 2026

## What This Room Covers

The OSI (Open Systems Interconnection) model — a 7-layer framework for understanding how network communication works at each stage from physical transmission to user-facing applications.

## My Key Takeaways

The OSI model is not just a memorization exercise — it is a troubleshooting map. When a connectivity issue comes in, knowing which layer is likely at fault narrows the investigation immediately. A physical layer issue looks completely different from a transport layer issue.

I already knew the OSI model from my KPU networking courses and CompTIA certifications, but this room reinforced the security implications of each layer — which is the angle TryHackMe brings that pure infrastructure study does not always emphasize.

## Commands / Concepts Reference

**The 7 Layers (top to bottom):**

| Layer | Name | Key Protocols / Devices |
|---|---|---|
| 7 | Application | HTTP, HTTPS, FTP, DNS, SMTP, SSH |
| 6 | Presentation | TLS/SSL, encoding, compression |
| 5 | Session | NetBIOS, RPC — establishes and maintains sessions |
| 4 | Transport | TCP (reliable), UDP (fast) — port numbers live here |
| 3 | Network | IP, ICMP, IPSec — routers operate here |
| 2 | Data Link | Ethernet (802.3), WiFi (802.11) — MAC addresses, switches |
| 1 | Physical | Cables, WiFi radio bands, hubs — raw bit transmission |

**Mnemonic (top to bottom):** "All People Seem To Need Data Processing"  
**Mnemonic (bottom to top):** "Please Do Not Throw Spinach Pizza Away"

**Additional concepts:**
- Layer 3 switches: handle both switching (L2) and routing (L3) in one device
- Layer 7 firewalls: inspect application-layer content, not just IP/port
- Encapsulation: each layer adds a header as data travels down; decapsulation removes headers as data travels up

## Real World Application

At **ESW IT** and **F12.net**, the OSI model guides how I approach network troubleshooting tickets. A user who cannot reach a website might have a Layer 1 problem (cable unplugged), a Layer 3 problem (wrong default gateway), a Layer 4 problem (firewall blocking the port), or a Layer 7 problem (proxy or content filter blocking the request). Starting at Layer 1 and working up is a systematic method that avoids wasted time checking the wrong thing.

---
*This repository was structured and documented with the assistance of Claude AI (Anthropic) as part of an agentic portfolio workflow.*
