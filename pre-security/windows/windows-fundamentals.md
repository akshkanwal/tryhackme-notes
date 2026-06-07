# Windows Fundamentals

**Learning Path:** Pre-Security  
**Platform:** TryHackMe  
**Completed:** February 2026

## What This Room Covers

The Windows operating system from a foundational perspective — edition history, desktop GUI components, display and personalization settings, and key operational details relevant to both end-user support and IT administration.

## My Key Takeaways

Much of this room was a structured review of knowledge I already use in production. Seeing it framed for a security-oriented audience was useful — TryHackMe approaches Windows from the angle of "what does an attacker need to understand about this environment" which is a different lens than pure administration.

## Commands / Concepts Reference

**Windows Edition History:**
- Windows XP (2001) → Vista (2006) → 7 (2009) → 8/8.1 (2012/2013) → 10 (2015) → 11 (2021)
- Windows 10 **End of Support: October 14, 2025** — critical for MSP client planning
- Windows Server: 2016, 2019, 2022, 2025

**Desktop GUI Components:**
| Component | Description |
|---|---|
| Desktop | Primary workspace — icons, background, widgets |
| Start Menu | Application launcher and search |
| Search Box | Quick file and application search |
| Task View | Virtual desktops and timeline |
| Taskbar | Open applications and system tray |
| Notification Area | System clock, volume, network, background app icons |

**Display Settings:**
- Resolution, orientation, and refresh rate — accessed via Settings > System > Display
- Multi-monitor setup: extend, duplicate, or use as main display
- Night Light and HDR settings for display comfort

**Remote Desktop:**
- RDP (Remote Desktop Protocol) — port 3389
- A user can only have one active local session at a time; RDP sessions run separately
- RDP is a core administration tool in Windows Server environments — and a common attack target

**Key Operational Notes:**
- File system: NTFS — supports permissions, encryption (EFS), journaling, and large file sizes
- User Account Control (UAC): prompts for elevation when admin rights are needed
- Windows Defender: built-in AV and firewall — relevant to endpoint security baseline

## Real World Application

Windows is the primary operating system across all of the MSP client environments I work in. This room's coverage of Remote Desktop limitations, edition end-of-life dates, and GUI components is directly relevant to the end-user support and migration planning work at **ESW IT** and **F12.net**. Windows 10 EOL planning is an active conversation with multiple clients — October 2025 is a firm deadline that creates real project work.

---
*This repository was structured and documented with the assistance of Claude AI (Anthropic) as part of an agentic portfolio workflow.*
