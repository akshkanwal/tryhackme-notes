# Networking Secure Protocols

**Learning Path:** Pre-Security  
**Platform:** TryHackMe  
**Completed:** March 2026

## What This Room Covers

How encryption and secure protocol layers protect network communication: TLS/SSL history and handshake, the CIA triad as a security framework, secure versions of common protocols, SSH versus Telnet, and how VPNs create secure tunnels over untrusted networks.

## My Key Takeaways

This room framed security protocols in terms of what they protect against — not just what they do. TLS is not just "HTTPS is padlock good" — it provides specific confidentiality, integrity, and authenticity guarantees. Understanding what each protocol actually prevents makes it easier to explain security decisions to clients and to identify gaps in an environment.

## Commands / Concepts Reference

**CIA Triad**
- **Confidentiality** — only authorized parties can read the data (addressed by encryption)
- **Integrity** — data has not been tampered with in transit (addressed by MACs and digital signatures)
- **Authenticity** — the sender is who they claim to be (addressed by certificates and PKI)

**TLS — Transport Layer Security**

| Version | Year | Status |
|---|---|---|
| SSL 2.0 | 1995 | Deprecated (broken) |
| SSL 3.0 | 1996 | Deprecated (POODLE attack) |
| TLS 1.0 | 1999 | Deprecated |
| TLS 1.1 | 2006 | Deprecated |
| TLS 1.2 | 2008 | Acceptable (still widely used) |
| TLS 1.3 | 2018 | Current standard — faster, more secure |

**Secure protocol equivalents:**
| Cleartext | Secure Version | Port |
|---|---|---|
| HTTP | HTTPS (HTTP over TLS) | 443 |
| SMTP | SMTPS | 465 |
| POP3 | POP3S | 995 |
| IMAP | IMAPS | 993 |

**SSH vs Telnet**
- Telnet sends all data in cleartext — credentials are visible on the wire
- SSH encrypts the entire session — industry standard for remote management
- SSH default port: **22**
- Key-based authentication is stronger than password-based SSH

**VPN**
- Creates an encrypted tunnel over an untrusted network (internet)
- Types: IPSec (site-to-site and remote access), SSL/TLS (client VPN, e.g. OpenVPN), WireGuard
- Does not make traffic anonymous — the VPN endpoint sees all traffic

## Real World Application

At **ESW IT**, enforcing TLS 1.2 minimum and disabling older SSL/TLS versions is part of M365 and Exchange security hardening. SSH is the standard for any remote device management. VPN configuration on SonicWall and WatchGuard platforms is a regular project deliverable — the protocol knowledge from this room informs how I select VPN types and troubleshoot handshake failures.

---
*This repository was structured and documented with the assistance of Claude AI (Anthropic) as part of an agentic portfolio workflow.*
