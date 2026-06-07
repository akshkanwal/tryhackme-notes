# Linux Fundamentals

**Learning Path:** Pre-Security  
**Platform:** TryHackMe  
**Completed:** February 2026

## What This Room Covers

The foundational Linux command-line skills needed for security and IT work: navigating the filesystem, reading and finding files, using operators to chain commands, and understanding why Linux is prevalent in IT infrastructure.

## My Key Takeaways

Linux runs a significant portion of the internet's infrastructure — web servers, network devices, cloud VMs, containers. Even in a Windows-dominant MSP environment, Linux appears constantly: in Azure VMs, network appliances, security tools, and monitoring platforms. Being comfortable at the Linux CLI is increasingly non-negotiable for senior IT and security roles.

## Commands / Concepts Reference

**Why Linux Matters in IT:**
- Powers the majority of web servers, cloud infrastructure, and network appliances
- Embedded in cars, PoS systems, IoT devices, and security tools
- Lightweight, open-source, and highly configurable
- Popular distributions: Ubuntu, Debian (general purpose); Kali (security); Alpine (containers)

**Core Navigation Commands:**
| Command | Purpose |
|---|---|
| `pwd` | Print working directory — where am I? |
| `ls` | List directory contents |
| `ls -la` | List all files including hidden, with permissions and sizes |
| `cd [dir]` | Change directory |
| `cd ..` | Go up one directory |
| `cd ~` | Go to home directory |

**File Operations:**
| Command | Purpose |
|---|---|
| `cat [file]` | Display file contents |
| `echo [text]` | Output text to screen or redirect to file |
| `whoami` | Show current user |
| `cp [src] [dest]` | Copy file |
| `mv [src] [dest]` | Move or rename file |
| `rm [file]` | Delete file |
| `mkdir [name]` | Create directory |

**Finding Files:**
```bash
find / -name passwords.txt          # Find file by exact name
find /home -name *.txt              # Wildcard search for .txt files
find / -type d -name config         # Find directories named config
```

**Searching Within Files:**
```bash
grep "password" config.txt          # Search for term in file
grep -R "admin" /etc/               # Recursive search in directory
grep -i "error" /var/log/syslog     # Case-insensitive search
```

**Linux Operators:**
| Operator | Purpose |
|---|---|
| `>` | Redirect output to file (overwrites) |
| `>>` | Append output to file |
| `&` | Run command in background |
| `&&` | Run second command only if first succeeds |
| `|` | Pipe — pass output of one command as input to next |

## Real World Application

At **ESW IT**, Linux appears in Azure VM workloads and in network appliance management. The grep and find commands are directly applicable to log analysis and configuration file searches. The operator chaining concepts map directly to PowerShell pipeline logic on the Windows side, making Linux fundamentals a natural complement to existing Windows CLI skills.

---
*This repository was structured and documented with the assistance of Claude AI (Anthropic) as part of an agentic portfolio workflow.*
