# tcpdump Basics

**Learning Path:** Pre-Security  
**Platform:** TryHackMe  
**Completed:** May 2026

## What This Room Covers

tcpdump — the CLI-based packet capture tool for Linux. Where Wireshark provides a GUI, tcpdump provides the same packet capture capability from the command line, making it essential for headless server environments and remote troubleshooting sessions.

## My Key Takeaways

tcpdump is the tool to reach for when you are SSH'd into a Linux server or network device and need to see what traffic is actually hitting the interface. No GUI, no remote desktop — just the command line and the raw packet stream. This room gave me a working command reference I can use in production.

## Commands / Concepts Reference

**Library:** tcpdump is built on libpcap — the same library Wireshark uses. PCAP files captured with tcpdump can be opened in Wireshark for analysis.

**List network interfaces:**
```bash
ip a s
```

**Key Flags:**

| Flag | Purpose |
|---|---|
| `-i [interface]` | Specify interface (e.g. `-i eth0`). Use `-i any` to capture all interfaces |
| `-w [file.pcap]` | Write capture to file instead of printing to screen |
| `-r [file.pcap]` | Read and analyse from a saved PCAP file |
| `-c [count]` | Stop after capturing N packets |
| `-n` | Disable DNS resolution (show IPs instead of hostnames) |
| `-nn` | Disable DNS resolution AND port name resolution (show port numbers) |
| `-v` / `-vv` | Verbose output (more protocol detail) |
| `-A` | Print packet content in ASCII |
| `-X` | Print packet content in hex and ASCII |

**Common usage examples:**
```bash
# Capture traffic on eth0, show IPs and ports (no resolution)
tcpdump -i eth0 -nn

# Capture HTTP traffic only
tcpdump -i eth0 -nn port 80

# Capture traffic to/from a specific host
tcpdump -i eth0 host 192.168.1.10

# Write capture to file
tcpdump -i any -w /tmp/capture.pcap

# Read from file
tcpdump -r /tmp/capture.pcap -nn
```

## Real World Application

When troubleshooting server-side connectivity issues in Azure VMs or Linux-based network appliances, tcpdump is often the fastest way to verify whether traffic is reaching the interface as expected. Capturing and saving a PCAP for later analysis in Wireshark is a common workflow when you need to share evidence of a network issue with a team or vendor.

---
*This repository was structured and documented with the assistance of Claude AI (Anthropic) as part of an agentic portfolio workflow.*
