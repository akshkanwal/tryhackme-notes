# Search Skills

**Learning Path:** SEC 101  
**Platform:** TryHackMe  
**Completed:** February 2026

## What This Room Covers

How to search effectively for technical and security information — Google advanced operators, specialized search engines used in security investigations (Shodan, Censys, VirusTotal, Have I Been Pwned), and the CVE vulnerability database.

## My Key Takeaways

This room reframed search as a professional skill rather than something everyone already knows. The specialized tools — Shodan, VirusTotal, HIBP — are ones I was aware of but had not systematically integrated into my workflow. Knowing these exist and when to reach for them makes security investigations significantly more effective.

## Commands / Concepts Reference

**Google Advanced Operators:**
| Operator | Purpose | Example |
|---|---|---|
| `"exact phrase"` | Exact phrase match | `"SonicWall VPN configuration"` |
| `site:` | Limit to specific domain | `site:docs.microsoft.com intune enrollment` |
| `-` (minus) | Exclude term | `WatchGuard firewall -forum` |
| `filetype:` | Search specific file type | `filetype:pdf PCNSE study guide` |
| `intitle:` | Search in page title | `intitle:"login page"` |
| `inurl:` | Search in URL | `inurl:admin` |

**Specialized Security Search Engines:**

**Shodan** (shodan.io)
- Searches internet-connected devices and systems — servers, routers, webcams, industrial controls
- Useful for: understanding your own external attack surface, investigating compromised IPs, research
- Shows: open ports, running services, software versions, geolocation

**Censys** (search.censys.io)
- Searches hosts, websites, and certificates across the internet
- Strong for certificate analysis and tracking infrastructure changes
- More structured API than Shodan — useful for programmatic investigation

**VirusTotal** (virustotal.com)
- Scans files and URLs against 70+ antivirus engines simultaneously
- Useful for: investigating suspicious files received by clients, checking URLs before visiting, analysing email attachments
- Hash lookup: if you have an MD5/SHA256 hash of a suspicious file, check it without running the file

**Have I Been Pwned** (haveibeenpwned.com)
- Checks whether an email address or domain appears in known data breaches
- Useful for: advising clients whose credentials may have been exposed, breach investigation
- Domain search shows all breached accounts under a given domain

**CVE — Common Vulnerabilities and Exposures**
- Standardized identifier system for publicly known security vulnerabilities
- Format: CVE-[YEAR]-[NUMBER] (e.g. CVE-2021-44228 — Log4Shell)
- Sources: NIST NVD (nvd.nist.gov), vendor security advisories, Mitre CVE database
- Every serious vulnerability gets a CVE — referencing CVEs in documentation ensures everyone is talking about the same issue

## Real World Application

At **ESW IT**, VirusTotal is a practical tool for investigating suspicious email attachments or files flagged by EPDR. Have I Been Pwned is useful when advising clients on password reset requirements following a breach notification. Shodan is relevant for external attack surface assessments — checking what services a client is exposing to the internet before a security review. Google operators save significant time when searching vendor documentation for specific configuration details.

---
*This repository was structured and documented with the assistance of Claude AI (Anthropic) as part of an agentic portfolio workflow.*
