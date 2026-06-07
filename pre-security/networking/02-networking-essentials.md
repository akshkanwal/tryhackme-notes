# Networking Essentials

**Learning Path:** Pre-Security  
**Platform:** TryHackMe  
**Completed:** March 2026

## What This Room Covers

Core networking protocols that make IP networks function: DHCP for automatic IP assignment, ARP for MAC-to-IP resolution, NAT for IP address sharing, and ICMP for network diagnostics.

## My Key Takeaways

This room covered protocols I use and troubleshoot regularly in production environments. Seeing them laid out from a security perspective — how each can be abused, what information each exposes — was a useful addition to the purely operational knowledge I already had.

## Commands / Concepts Reference

**DHCP — Dynamic Host Configuration Protocol**

The DORA process:
1. **Discover** — client broadcasts: "Is there a DHCP server out there?"
2. **Offer** — server responds: "Here is an available IP address for you"
3. **Request** — client accepts: "I will take that IP"
4. **Acknowledge** — server confirms: "It is yours, here are the lease details"

Ports: DHCP server listens on **UDP 67**, client listens on **UDP 68**

**ARP — Address Resolution Protocol**
- Purpose: resolve an IP address to a MAC address on the local network
- Process: broadcast "Who has IP X?" → device with that IP replies with its MAC
- ARP table: cached IP-to-MAC mappings (view with `arp -a` on Windows/Linux)
- Security note: ARP has no authentication — ARP spoofing/poisoning is a real attack vector

**NAT — Network Address Translation**
- Allows multiple private IP devices to share a single public IP
- Router rewrites source IP on outbound packets and tracks the mapping
- Hides internal network topology from external observers

**ICMP — Internet Control Message Protocol**
- Used for diagnostics and error reporting
- `ping` sends ICMP Echo Request, expects ICMP Echo Reply
- `traceroute` / `tracert` uses TTL manipulation to map the path to a destination
- ICMP is often blocked at firewalls — lack of ping response does not mean host is down

## Real World Application

DHCP troubleshooting is a weekly occurrence in MSP work. Understanding the DORA process makes it straightforward to diagnose whether a client is failing to get an IP (no DHCP server reachable), getting the wrong IP (wrong scope or rogue DHCP), or getting an address but with incorrect options (wrong gateway or DNS).

ARP issues — particularly duplicate IPs — are a common source of intermittent connectivity complaints that are easy to miss without knowing to check the ARP table.

---
*This repository was structured and documented with the assistance of Claude AI (Anthropic) as part of an agentic portfolio workflow.*
