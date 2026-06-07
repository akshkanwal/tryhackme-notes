# Networking Core Protocols

**Learning Path:** Pre-Security  
**Platform:** TryHackMe  
**Completed:** March 2026

## What This Room Covers

The application-layer protocols that underpin internet communication: DNS for name resolution, HTTP and FTP for file and web transfer, and the email protocols (SMTP, POP3, IMAP).

## My Key Takeaways

DNS is the most practically relevant topic in this room for day-to-day IT and security work. DNS misconfigurations cause a huge proportion of connectivity and email delivery issues. Understanding DNS record types, the resolution process, and tools like nslookup is essential for any IT professional.

## Commands / Concepts Reference

**DNS — Domain Name System**

| Record Type | Purpose |
|---|---|
| A | Maps hostname to IPv4 address |
| AAAA | Maps hostname to IPv6 address |
| CNAME | Alias — maps one name to another name |
| MX | Mail exchanger — directs email to the right server |
| TXT | Text records — used for SPF, DKIM, DMARC, domain verification |

- Default transport: **UDP port 53** (fast, for standard queries)
- Fallback: **TCP port 53** (for large responses or zone transfers)
- Tool: `nslookup [domain]` — query DNS records from the command line

**WHOIS**
- Queries domain registration information: registrant, registrar, registration and expiry dates
- Useful for investigating suspicious domains

**HTTP — HyperText Transfer Protocol**
- Port 80 (HTTP), port 443 (HTTPS)
- Request methods: GET (retrieve), POST (submit data), PUT (update), DELETE
- Status codes: 2xx success, 3xx redirect, 4xx client error, 5xx server error

**FTP — File Transfer Protocol**
- Port 21 (control), port 20 (data — active mode)
- Transmits data in cleartext — replaced by SFTP (port 22) and FTPS in secure environments

**Email Protocols**
| Protocol | Port | Purpose |
|---|---|---|
| SMTP | 25, 587 | Sending email |
| POP3 | 110 | Receiving email (downloads and deletes from server) |
| IMAP | 143 | Receiving email (syncs with server, multi-device) |

## Real World Application

DNS is the first thing I check when users report they "cannot connect to" something. `nslookup` is a daily tool — checking whether a domain resolves correctly, whether MX records are pointed to the right place, and whether a new DNS record has propagated. Email delivery issues at **ESW IT** (SPF, DKIM, DMARC failures) all come back to DNS TXT records.

---
*This repository was structured and documented with the assistance of Claude AI (Anthropic) as part of an agentic portfolio workflow.*
