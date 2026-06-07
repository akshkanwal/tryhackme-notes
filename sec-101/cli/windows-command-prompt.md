# Windows Command Prompt

**Learning Path:** SEC 101  
**Platform:** TryHackMe  
**Completed:** March 2026

## What This Room Covers

The Windows Command Prompt (CMD) — why it is still relevant alongside PowerShell and GUI tools, key commands for system information gathering, network diagnostics, and the advantages of CLI over GUI in IT and security work.

## My Key Takeaways

CMD is something I use regularly in IT work, but this room framed it in a security context — specifically how attackers and defenders use the same commands to gather system information, enumerate network configuration, and understand the environment. Knowing what `systeminfo` reveals, for example, is relevant both for troubleshooting and for understanding what an attacker would learn from it.

## Commands / Concepts Reference

**Why CMD Still Matters:**
- Lower resource usage than GUI tools — critical on resource-constrained or degraded systems
- Scriptable — batch files automate repetitive tasks
- Efficient remote management via SSH — no GUI required
- Many legacy enterprise applications still rely on CMD-based operations

**System Information:**
```cmd
ver                   :: OS version
systeminfo            :: Full system details — OS, hardware, network adapters, hotfixes
set                   :: View all environment variables
set PATH              :: View the PATH variable specifically
hostname              :: Computer name
whoami                :: Current user and domain
```

**Network Commands:**
```cmd
ipconfig              :: Basic IP configuration for all adapters
ipconfig /all         :: Full details including MAC, DHCP server, DNS servers
ipconfig /release     :: Release DHCP lease
ipconfig /renew       :: Renew DHCP lease
ipconfig /flushdns    :: Clear DNS resolver cache
ping [host]           :: Test connectivity to host
tracert [host]        :: Trace route to host
nslookup [domain]     :: Query DNS for domain
netstat -an           :: Show active connections and listening ports
arp -a                :: Show ARP table
```

**Process and Service Management:**
```cmd
tasklist              :: List running processes
taskkill /PID [id]    :: Terminate process by PID
sc query              :: List services and their states
net start [service]   :: Start a service
net stop [service]    :: Stop a service
```

## Real World Application

These commands are part of my daily toolkit for diagnosing issues in client environments at **ESW IT** and **F12.net**. `ipconfig /all` is the first thing I run when a client has a connectivity issue — it immediately shows whether they have an IP, what their gateway and DNS servers are, and whether DHCP is working. `netstat -an` is useful for confirming whether a service is listening on the expected port. `systeminfo` provides a fast overview of a new system — patches installed, domain membership, hardware specs.

---
*This repository was structured and documented with the assistance of Claude AI (Anthropic) as part of an agentic portfolio workflow.*
