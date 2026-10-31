# Offensive Security Knowledge Base — Pentest & Red Team

> **Author:** Pedro Henrique Gonçalves  
> **Language:** Portuguese 🇧🇷 · English 🇺🇸 (translated version available)

---

## What is this?

This is a structured knowledge base compiled from roughly **170 sources** — personal notes, course slides, lecture PDFs, and hands-on practice — covering offensive security from first principles to advanced exploitation techniques.

The material is organized by **increasing complexity**: it starts with operating systems and networking fundamentals and progresses through web vulnerabilities, binary exploitation, malware analysis, OSINT, and AI-assisted attack research. Each section builds on the one before it.

---

## Motivation

I've been accumulating notes across dozens of courses, certifications, CTF writeups, and research papers. This compilation is my attempt to turn scattered material into a single, navigable reference — one I can search, link to, and share with others who are on the same learning path.

The goal isn't to provide a ready-made attack toolkit. It's to document *how things work*, *why they matter*, and *how to think about them* — so that the knowledge sticks and can be applied in real engagements or defended against.

---

## Files

| File | Language | Description |
|------|----------|-------------|
| `compilado-pentest-redteam.md` | 🇧🇷 Portuguese | Main knowledge base |
| `compilado-pentest-redteam-en.md` | 🇺🇸 English | Translated version |

---

## Structure

The document is divided into 16 parts, organized from foundational to advanced:

| # | Section | Topics |
|---|---------|--------|
| 1 | **Fundamentals** | CIA triad, threat modeling, Linux CLI, shell scripting, PowerShell, networking, cryptography |
| 2 | **Pentest & Red Team Methodology** | Cyber Kill Chain, pentest phases, Black/Grey/White box, offensive mindset, Purple Team |
| 3 | **Reconnaissance & Enumeration** | OSINT, Google Dorking, subdomain brute-force, port scanning, service enumeration (incl. hands-on NFS, SMTP and MySQL exploitation), vulnerability categories & scoring (CVSS, VPR), traffic capture |
| 4 | **Web Vulnerabilities** | OWASP Top 10 (2021) in depth — SQLi, XSS, IDOR, CSRF, SSRF, file upload bypass, race conditions, JWT attacks |
| 5 | **Offensive Tools** | Burp Suite, SQLMap, Hydra, John / Hashcat, Metasploit / MSFVenom, CyberChef |
| 6 | **Exploitation & Post-Exploitation** | Reverse/bind/web shells (incl. Socat, named pipes, staged vs. stageless payloads, shell stabilization), Linux privilege escalation (kernel, sudo misconfig, SUID/SGID, capabilities, cron, PATH hijacking, NFS), Windows privilege escalation (credential hunting, AlwaysInstallElevated, scheduled tasks, service misconfigurations, dangerous privileges, unpatched software), Active Directory dMSA abuse (BadSuccessor), pivoting, C2 frameworks, botnets |
| 7 | **Binary Exploitation (Advanced)** | x86 architecture, stack buffer overflows, SEH-based exploitation, egg hunters |
| 8 | **API Security** | REST/GraphQL/gRPC, OWASP API Top 10, API pentest tooling |
| 9 | **Blue Team / Defense** | SOC, SIEM, firewall, IDS/IPS, log analysis, incident response |
| 10 | **Digital Forensics & Malware Analysis** | Forensic acquisition, static/dynamic analysis, obfuscation, reverse engineering tools |
| 11 | **Intelligence (OSINT / Cyber Intel)** | Counter-intelligence, CTI, advanced OSINT tooling |
| 12 | **AI Applied to Offensive Security** | Adversarial ML, data poisoning, AI-assisted attack research |
| 13 | **Digital Law & Legal Aspects** | Brazilian cybercrime law (Lei 12.737), Marco Civil, LGPD, EU AI Act |
| 14 | **Reporting & Communication** | PTES report structure, executive vs. technical findings, writing tips |
| 15 | **Management & Culture** | Purple Team philosophy, adversary emulation, MITRE ATT&CK, VECTR |
| 16 | **Appendix** | Practice platforms, cheat sheets, wordlists, tool catalog, bibliography |

---

## What's included vs. what's deliberately omitted

This is a **study document**, not an attack package.

**Included:**
- Conceptual explanations of how vulnerabilities work
- Methodology frameworks and checklists
- Command-line references and tool flags
- Code snippets for educational demonstration (detection, proof-of-concept)
- Defensive context for each offensive technique
- Real-world attack case studies, documented at the mechanism level (e.g. a CVE's root cause and exploitation logic), with the original researcher/source always linked

**Deliberately omitted / catalogued by name only:**
- Functional shellcode and complete binary exploits
- Python scripts for buffer overflow exploitation (listed as methodological reference only, not as a usable package)
- Full exploit scripts for specific CVEs (e.g. RPC-based local privilege escalation chains) — the vulnerability mechanism and protocol are documented, the ready-to-run code is not
- CTF challenge writeups with full flag extraction

---

## How to read it

- **Start at Part 1** if you're new to the field — the networking and Linux fundamentals section is a prerequisite for everything else.
- **Jump to a specific part** using the Table of Contents at the top of the document — all section and subsection links are clickable.
- **Use it as a cheat sheet** for specific tools or vulnerabilities during engagements.
- **Cross-reference Parts 2 and 15** for methodology and mindset — they frame how all the technical content fits together.

---

## Platforms referenced

Practice environments mentioned throughout: **TryHackMe**, **HackTheBox**, **PortSwigger Web Security Academy**, **PicoCTF**, **Root-Me**, **IppSec (YouTube)**, **VulnHub**.

---

## License & disclaimer

This material is for **educational and authorized security research purposes only**. Nothing in this document authorizes the use of these techniques against systems you do not have explicit permission to test.

> "Know your enemy and know yourself; in a hundred battles, you will never be defeated." — Sun Tzu
