# Compiled Knowledge — Offensive Security, Pentest & Red Team

> Material compiled and organized from ~160 sources (personal notes, course slides, and lecture PDFs), structured by increasing complexity — from fundamentals to advanced exploitation. Functional exploit code (shellcode, complete binary exploits) has been deliberately omitted or catalogued by name and purpose only — this document is study material, not an attack toolkit.

## Table of Contents

1. [Fundamentals](#fundamentals)
   - [1.1 Information Security vs Cybersecurity](#11-information-security-vs-cybersecurity)
   - [1.2 Security Principles](#12-security-principles)
   - [1.3 Operating System and Command Line (Linux)](#13-operating-system-and-command-line-linux)
   - [1.4 Shell Script](#14-shell-script)
   - [1.5 Virtualization](#15-virtualization)
   - [1.6 Computer Networking Fundamentals](#16-computer-networking-fundamentals)
   - [1.7 Cryptography and Hashing](#17-cryptography-and-hashing)
2. [Pentest and Red Team Methodology](#pentest-and-red-team-methodology)
   - [2.1 Cyber Kill Chain](#21-cyber-kill-chain)
   - [2.2 Pentest Phases (detailed view — CISCO)](#22-pentest-phases-detailed-view--cisco)
   - [2.3 Pentest Modalities](#23-pentest-modalities)
   - [2.4 Offensive Mindset](#24-offensive-mindset)
   - [2.5 Security Best Practices](#25-security-best-practices-defense-but-essential-to-know)
   - [2.6 Purple Team — Context and Fundamentals](#26-purple-team--context-and-fundamentals)
   - [2.7 Leadership Applied to Offensive Security](#27-leadership-applied-to-offensive-security)
   - [2.8 Leadership Fundamentals](#28-leadership-fundamentals-base-reference)
3. [Reconnaissance and Enumeration](#reconnaissance-and-enumeration)
   - [3.1 Information Gathering (OSINT)](#31-information-gathering-osint)
   - [3.2 Advanced Information Gathering](#32-advanced-information-gathering)
   - [3.3 Subdomain Enumeration](#33-subdomain-enumeration)
   - [3.4 Web Content Discovery](#34-web-content-discovery)
   - [3.5 Directory/Domain Scanning Tools](#35-directorydomain-scanning-tools)
   - [3.6 Scanning](#36-scanning)
   - [3.7 Service Enumeration](#37-service-enumeration)
   - [3.8 Traffic Capture](#38-traffic-capture)
   - [3.9 Vulnerability Databases](#39-vulnerability-databases)
   - [3.10 Vulnerability Scanning Tools](#310-vulnerability-scanning-tools)
4. [Web Vulnerabilities](#web-vulnerabilities)
   - [4.1 Overview — OWASP Top 10 (2021)](#41-overview--owasp-top-10-2021)
   - [4.2 A01 — Broken Access Control](#42-a01--broken-access-control)
   - [4.3 A02 — Cryptographic Failures](#43-a02--cryptographic-failures)
   - [4.4 A03 — Injection](#44-a03--injection)
   - [4.5 A04 — Insecure Design](#45-a04--insecure-design)
   - [4.6 A05 — Security Misconfiguration](#46-a05--security-misconfiguration)
   - [4.7 A06 — Vulnerable and Outdated Components](#47-a06--vulnerable-and-outdated-components)
   - [4.8 A07 — Identification and Authentication Failures](#48-a07--identification-and-authentication-failures)
   - [4.9 A08 — Software and Data Integrity Failures](#49-a08--software-and-data-integrity-failures)
   - [4.10 A09 — Security Logging and Monitoring Failures](#410-a09--security-logging-and-monitoring-failures)
   - [4.11 A10 — SSRF (Server-Side Request Forgery)](#411-a10--ssrf-server-side-request-forgery)
   - [4.12 OWASP API Security Top 10 (summary)](#412-owasp-api-security-top-10-summary)
   - [4.13 DevTools — Storage Tab](#413-devtools--storage-tab-browser-inspection-tool)
5. [Offensive Tools](#offensive-tools)
   - [5.1 Burp Suite](#51-burp-suite)
   - [5.2 SQLMap](#52-sqlmap)
   - [5.3 Hydra](#53-hydra)
   - [5.4 John the Ripper / Hashcat](#54-john-the-ripper--hashcat)
   - [5.5 Metasploit Framework](#55-metasploit-framework)
   - [5.6 CyberChef](#56-cyberchef)
   - [5.7 Other Useful Tools](#57-other-useful-tools-quick-reference)
6. [Exploitation and Post-Exploitation](#exploitation-and-post-exploitation)
   - [6.1 Exploitation — Fundamentals](#61-exploitation--fundamentals)
   - [6.2 Shells (Reverse, Bind, Web)](#62-shells-reverse-bind-web)
   - [6.3 Post-Exploitation — Linux](#63-post-exploitation--linux)
   - [6.4 Post-Exploitation — Windows](#64-post-exploitation--windows)
   - [6.5 Command and Control (C2) and Botnets](#65-command-and-control-c2-and-botnets)
7. [Binary Exploitation (Advanced)](#binary-exploitation-advanced)
   - [7.1 x86 Architecture Fundamentals](#71-x86-architecture-fundamentals)
   - [7.2 Buffer Overflow — Concept](#72-buffer-overflow--concept)
   - [7.3 SEH Based Exploitation](#73-seh-based-exploitation)
   - [7.4 Egg Hunter](#74-egg-hunter)
   - [7.5 Reference Script Catalog](#75-reference-script-catalog-theory-without-reproducing-functional-code)
8. [API Security](#api-security)
   - [8.1 API Basics](#81-api-basics)
   - [8.2 OWASP API Security Top 10](#82-owasp-api-security-top-10)
   - [8.3 Pentest API Tools](#83-pentest-api-tools)
   - [8.4 Exploiting APIs](#84-exploiting-apis)
9. [Blue Team / Defense](#blue-team--defense)
   - [9.1 SOC (Security Operation Center)](#91-soc-security-operation-center)
   - [9.2 SIEM (Security Information and Event Management)](#92-siem-security-information-and-event-management)
   - [9.3 Firewall](#93-firewall)
   - [9.4 IDS/IPS](#94-idsips)
   - [9.5 Log Fundamentals](#95-log-fundamentals)
   - [9.6 Vulnerability Management (defensive view)](#96-vulnerability-management-defensive-view)
   - [9.7 Incident Response](#97-incident-response-detailed)
   - [9.8 Detection Case Study — CVE-2025-68613 (n8n)](#98-detection-case-study--cve-2025-68613-n8n)
10. [Digital Forensics and Malware Analysis](#digital-forensics-and-malware-analysis)
    - [10.1 Digital Forensics Fundamentals](#101-digital-forensics-fundamentals)
    - [10.2 Malware Analysis — Fundamentals](#102-malware-analysis--fundamentals)
    - [10.3 Static Analysis](#103-static-analysis)
    - [10.4 Dynamic Analysis](#104-dynamic-analysis)
    - [10.5 Malware Protection and Obfuscation Techniques](#105-malware-protection-and-obfuscation-techniques)
    - [10.6 Reverse Engineering Tools](#106-reverse-engineering-tools)
    - [10.1 Digital Forensics — Fundamentals (supplementary)](#101-digital-forensics--fundamentals-1)
    - [10.2 Malware Fundamentals](#102-malware-fundamentals)
    - [10.3 Static Analysis (II)](#103-static-analysis-ii)
    - [10.4 Dynamic Analysis (II)](#104-dynamic-analysis-ii)
    - [10.5 Advanced Analysis — Reverse Engineering](#105-advanced-analysis--reverse-engineering)
    - [10.6 Malware Obfuscation](#106-malware-obfuscation)
11. [Intelligence (OSINT / Cyber Intel)](#intelligence-osint--cyber-intel)
    - [11.1 Counter-Intelligence and CTI](#111-counter-intelligence-and-cti)
    - [11.2 Advanced OSINT Tools](#112-advanced-osint-tools)
12. [AI Applied to Offensive Security](#ai-applied-to-offensive-security)
    - [12.1 AI in Offensive and Defensive Security](#121-ai-in-offensive-and-defensive-security)
    - [12.2 Data Poisoning Attacks](#122-data-poisoning-attacks)
    - [12.3 Machine Learning Fundamentals Applied to Security](#123-machine-learning-fundamentals-applied-to-security)
13. [Digital Law and Legal Aspects](#digital-law-and-legal-aspects)
    - [13.1 Introduction to Digital Law](#131-introduction-to-digital-law)
    - [13.2 Digital Crimes — Law 12.737/2012 (Carolina Dieckmann Law)](#132-digital-crimes--law-127372012-carolina-dieckmann-law)
    - [13.3 Marco Civil da Internet — Law 12.965/2014](#133-marco-civil-da-internet--law-129652014)
    - [13.4 LGPD — General Data Protection Law (Law 13.709/2018)](#134-lgpd--general-data-protection-law-law-137092018)
    - [13.5 Legal Aspects of Information Security](#135-legal-aspects-of-information-security)
    - [13.6 AI and Legislation — EU AI Act and PL 2338/2023 (Brazil)](#136-ai-and-legislation--eu-ai-act-and-pl-23382023-brazil)
14. [Reporting and Communication](#reporting-and-communication)
    - [14.1 Pentest Report Structure (PTES)](#141-pentest-report-structure-ptes)
    - [14.2 Report Writing Tips](#142-report-writing-tips)
15. [Management and Culture](#management-and-culture)
16. [Appendix](#appendix)
    - [A.1 Practice Platforms](#a1-practice-platforms)
    - [A.2 Essential Online Resources](#a2-essential-online-resources)
    - [A.3 Grouped Tool Catalog](#a3-grouped-tool-catalog)
    - [A.4 Default Wordlists](#a4-default-wordlists)
    - [A.5 Books and Bibliographic References](#a5-books-and-bibliographic-references)
    - [A.6 Legal References (Brazil)](#a6-legal-references-brazil)

---

# Fundamentals

*Level: Basic. Prerequisite for all remaining material.*

## 1.1 Information Security vs Cybersecurity

Cybersecurity is a segment within the broader field of Information Security. The **Information Security triad** consists of **People, Processes, and Technology** — and the weakest link is usually the human element.

Some common myths: the more secure, the more "locked down"; privileges must be minimal; access restricted to administrators. In practice, over-restricting users can harm the business — the solution is usually awareness (e.g., allowing installation only from known software catalogs) rather than total blocking.

Information goes through a lifecycle: **create → collect → process → store → transmit or dispose**. Not knowing what happens with information at each stage (restriction level, risks, vulnerabilities) is itself a risk.

The **ISO/IEC 27002:2022** standard organizes controls into 4 categories: Organizational (37), People (8), Physical (14), and Technology (34).

### Cybersecurity Concept
Cybersecurity is defined in various ways, but they converge on: safeguarding networks and information against intrusion, damage, or disruption; reducing the risk of attacks on software, computers, and networks; and a set of tools, policies, training, and technologies used to protect the cyber environment. It is broader than just a technological solution — it also involves human and process aspects.

**Most common attack vectors** (Hackmageddon 2021 data): Malware (39.4%), unknown causes (18.7%), Account Takeover (13%) — identity appropriation (username/password) for unauthorized actions.

## 1.2 Security Principles

- **PIM (Privileged Identity Management)**: minimum access each individual user should receive according to their role.
- **PAM (Privileged Access Management)**: management of privileges a role/department holds — password policies, auditing, attack surface reduction.
- **Least privilege**: grant only what is necessary for the function.

### Threat Modeling (STRIDE)
Process of reviewing and testing security protocols, including: preparation, identification, mitigation, and analysis.

| Threat | Description |
|---|---|
| **S**poofing | Identity falsification — remediated with API keys, cryptographic signatures |
| **T**ampering | Data alteration — anti-tampering measures ensure integrity |
| **R**epudiation | Denial of actions — mitigated via activity logs |
| **I**nformation disclosure | Information exposure — show only relevant data to the owner |
| **D**enial of Service | Service denial — protect resources against abuse |
| **E**levation of privilege | Privilege escalation — worst case, user escalates to admin |

**PASTA** methodology: Process for Attack Simulation and Threat Analysis.

### Incident Response — 6 Phases (SANS, also used by NIST)
"PICERL": **P**reparation → **I**dentification → **C**ontainment → **E**radication → **R**ecovery → **L**essons Learned.

A security breach is an **incident**; the team that responds is the **CSIRT** (Computer Security Incident Response Team).

## 1.3 Operating System and Command Line (Linux)

Operating System: software that manages hardware, applications, and system resources.
- **Kernel space**: privileged area with direct hardware access.
- **User space**: common applications, limited permissions.
- **GUI** vs **CLI**: graphical interface vs command line.

Directory structure (FHS — Filesystem Hierarchy Standard):
- `/etc` → configuration files
- `/dev/root` → main disk
- `tmpfs` → temporary filesystem in RAM
- `/dev/shm` → shared memory
- `/var/log` → system logs (`auth.log` = authentication attempts; `syslog`)

### Essential Process Management Commands
```
ps            # running processes
ps -e         # all system processes
ps -ef        # detailed information
kill [PID]    # terminate process; kill -9 forces
killall name  # terminates all processes of a program
top           # real-time process monitor
jobs / fg / bg  # foreground/background processes
pstree        # process tree
locate / updatedb  # file search by name (indexed database)
which cmd     # path of the executable
dmesg         # boot log
tail -f file  # follow a file in real time
```

Remote connection: `ssh -X user@ip` (graphical X forwarding — what runs graphically runs on the remote machine, displayed locally).

File transfer with `scp` (Secure Copy, uses SSH):
```
# Local → Remote (send file to remote machine)
scp file user@ip:/destination/directory

# Remote → Local (download file from remote machine to local — useful in post-exploitation)
scp user@ip:/path/remote_file /local/directory/

# Copy entire directory (flag -r)
scp -r user@ip:/remote_directory/ /local_directory/
```

### Regular Expressions (REGEX) and Text Manipulation
Essential for log analysis and CTFs.

```
grep [options] regex file     # filter lines by pattern
egrep                         # grep + metacharacters +,?,|,()
fgrep                         # literal search (no regex), faster
sed [options] {script}        # text editing/transformation
```

Practical examples:
```
grep '^1' access.log                 # lines starting with 1
grep '^[aeiou]' access.log           # lines starting with a vowel
egrep -i '.m.a' access.log           # 2nd letter m, 4th letter a (any char = '.')
sed -n '/http/p' access.log          # lines containing "http"
sed -n '/http/p' access.log | egrep -i -v "Mozilla|dirbuster"  # suppress terms
for i in {1..100}; do echo $i >> nfile.txt; done     # generate sequence
for i in $(cat nfile.txt); do total=$((2*$i)); echo $total; done  # process line by line
```

Regex are useful for validating/searching: IPs, emails, URLs, data between HTML tags, tax IDs, dates.

## 1.4 Shell Script

A shell script begins with a **shebang** (`#!/bin/bash`), indicating the interpreter. Lines with `#` are comments.

```bash
#!/bin/bash
#My script
echo "Hello World"
```

Make executable: `chmod 755 script.sh` (everyone can execute) or `700` (owner only). Run: `./script.sh`.

Conventional locations: `~/bin` (personal scripts), `/usr/local/bin` (general use), `/usr/local/sbin` (administration). To run from anywhere, add to `PATH` in `/etc/profile`.

### Conditionals
```bash
if [ CONDITION ]; then
  ACTION
fi
```
Arithmetic operators: `-eq` (equal), `-ne` (not equal), `-lt` (less than), `-le` (less or equal), `-gt` (greater than), `-ge` (greater or equal).
File operators: `-s` (not empty), `-f` (exists and is not a directory), `-d` (is a directory), `-w` (writable), `-r` (readable), `-x` (executable).

User input: `read variable`. Scripts can be nested (`if` inside `if`).

### PowerShell (Windows)
Microsoft .NET-based platform for Windows automation and administration. Object-oriented — each command returns an object, not just text. Relevant for red team as a **Living off the Land (LotL)** vector: uses native OS tools without leaving additional artifacts.

**Verb-Noun Convention (Cmdlets):**
```powershell
Get-Service                                          # list all services
Get-Service -Name "ByteBank" -ComputerName "SRV01"  # specific service on remote host
Get-Command                                          # list all available cmdlets
Get-Help Get-Service -Full                           # complete documentation
```

**Variables and pipeline:**
```powershell
$service = Get-Service -Name GamingServices          # store in variable
$service | Get-Member                                # inspect methods and properties

# List files recursively, filter by name and display size in KB
gci -Recurse -File | Where-Object Name -like "*_script_*" | Select-Object Name, Length

# Convention: FILTER LEFT, FORMAT RIGHT (better performance)
gci -Recurse -File | ? Name -Like "*_script_*" | Select-Object Name, Length
```

**Post-exploitation enumeration and reconnaissance:**
```powershell
Get-Service                                          # all services + status
Get-Process                                          # running processes
Get-LocalUser                                        # local users
Get-LocalGroup                                       # local groups
Get-NetIPConfiguration                               # network configuration
Get-ChildItem C:\Users -Recurse -File                # recursive files
$env:computername                                    # machine hostname
```

**Remote execution (lateral movement):**
```powershell
# Open interactive remote session
New-PSSession -ComputerName SERVER01
Enter-PSSession -ComputerName SERVER01

# Execute code block in existing session
$sess = New-PSSession -ComputerName SERVER01
Invoke-Command -Session $sess -ScriptBlock { Get-Service }

# Create remote drive mapping (filesystem access)
New-PSDrive -Root \\SERVER01\D$\ -Name G -PSProvider FileSystem
```

**Jobs — parallel background execution:**
```powershell
$job = Start-Job -ScriptBlock { Get-Process }
Receive-Job -Job $job    # collect result
Remove-Job -Job $job
```

**Exporting results:**
```powershell
Get-Service | ConvertTo-Json | Out-File report.json
Get-Service | ConvertTo-Csv -NoTypeInformation | Out-File report.csv
Get-Service | ConvertTo-Html -Title "Report" | Out-File report.html
```

**CmdLet vs Function:**
| | CmdLet | Function |
| --- | --- | --- |
| Implementation | Compiled in .NET (C#/F#) | PowerShell script |
| Performance | High — optimized for large volumes | Adequate for simple tasks |
| Ideal use | Complex tasks, .NET integration, production | Quick automation, prototyping, one-off scripts |

**Red team — offensive context:**
- **LotL (Living off the Land):** `Invoke-Command`, `New-PSSession`, `Get-WmiObject` are native — require no external binaries.
- **Per-session execution policy bypass:** `powershell.exe -ExecutionPolicy Bypass -File script.ps1`
- **In-memory loading:** scripts can run without writing to disk via `IEX (Invoke-Expression)` + payload download.
- **Detection:** PowerShell logs (Event ID 4103/4104 — Script Block Logging) are monitored in mature environments (see Section 9.5).

## 1.5 Virtualization

Abstraction layer over physical hardware, allowing division of resources (CPU, RAM, disk) into one or more independent **virtual machines (VMs)**, each with its own OS.

### Hypervisors
- **Type 1 (Bare Metal)**: installed directly on hardware, without an underlying OS. Used in corporate datacenters. More efficient.
- **Type 2 (Hosted)**: installed as an application on top of a host OS. Easier to configure (reuses host network/storage), but less efficient with more failure points (restarting the host shuts down all VMs).

Basic hypervisor functions: provide an environment identical to physical; minimal performance overhead; retain full control of system resources.

## 1.6 Computer Networking Fundamentals

### Layered Model (OSI vs TCP/IP)
Layered models distribute the stages of message transmission, making protocols responsible for specific functions at their layer, avoiding bottlenecks. Each layer leverages resources from the layer below and provides resources to the layer above.

- **Protocol model** (e.g., TCP/IP): corresponds to the structure of a specific protocol suite — describes what actually occurs.
- **Reference model** (e.g., OSI): describes what needs to be done at each layer, without prescribing how — offers consistency across different protocol types.

The TCP/IP model (created in the 1970s, also called the "Internet model") is an open standard, publicly discussed via RFCs, not controlled by a single company.

OSI → TCP/IP mapping: OSI layers 1-2 (physical/data link) → network access; layer 3 (network) → Internet layer; layer 4 (transport) → transport; layers 5-7 (session/presentation/application) → application.

### Encapsulation and Segmentation
Transmitting an entire message as a continuous stream would block the network for other devices and, if a link failed, the entire message would be lost. Therefore data is divided into smaller **segments**, which allows:
- **Multiplexing**: multiple different conversations interleaved on the same network.
- Greater efficiency: only lost parts need retransmission.

At each layer, protocol information is added to the data — the process of **encapsulation**. The format data takes at each layer is the **PDU (Protocol Data Unit)**.

Network layer addresses (IP) deliver the packet from source to final destination (same or remote network). Data link layer addresses (MAC) deliver the frame from one NIC to another on the same local network.

### Three-Way Handshake (TCP)
1. Client sends packet with **SYN** bit (connection initiation).
2. Server responds with **SYN + ACK**.
3. Client responds with **ACK**, confirming establishment.

Ensures reliable transmission — lost or corrupted data is retransmitted.

### Network Protocols (summary by layer/port)

| Protocol | Layer | Port | Function |
|---|---|---|---|
| TELNET | 7 (App) | 23 | Remote connection (plain text, insecure) |
| SSH | 7 | 22 | Secure remote connection; SFTP base |
| DHCP | 7 | — | Distributes IPs (DORA flow: Discover, Offer, Request, Acknowledge) |
| ARP | 3 (Network) | — | Translates IP → MAC |
| ICMP | 3 | — | Diagnostics (ping, traceroute) |
| NAT | 3 | — | Translates private ↔ public addresses |
| WHOIS | 7 | — | Domain registration data |
| DNS | 7 | 53 (TCP/UDP) | Translates domain name ↔ IP (types A, AAAA, CNAME, MX) |
| HTTP/HTTPS | 7 | 80/443 (8080/8443) | Browser-server communication |
| FTP | 7 | 21 | File transfer (commands USER, PASS, RETR, STOR) |
| SMTP | 7 | 25 | Email sending (HELO/EHLO, MAIL FROM, RCPT TO, DATA) |
| POP3 | 7 | 110 | Retrieves email (single device only) |
| IMAP | 7 | 143 | Syncs email across multiple devices |
| TLS/SSL | 4 (Transport) | — | Encryption (HTTP→HTTPS, POP3→POP3S etc.) |

Secure ports: HTTPS 443, POP3S 995, SMTPS 465/587, IMAPS 993, FTPS 990, SSH/SFTP 22.

**VPN**: "V" (virtual) uses the public internet infrastructure to connect geographically distant networks; "P" (private) ensures confidentiality and integrity of data entering/leaving.

### Network Services — SMB
**SMB (Server Message Block)**: client-server protocol for file/printer sharing, based on NetBIOS over TCP/IP. **Samba** is the open-source implementation for Linux/Unix, compatible with Windows, enabling user directories accessible over the network with configurable disk quotas.

## 1.7 Cryptography and Hashing

### Basic Concepts
- **Plaintext**: readable content.
- **Ciphertext**: content after encryption.
- **Cipher**: algorithm used to encrypt/decrypt.
- **Key**: value used in the process.
- **Cryptanalysis**: study of methods to break encryption without knowing the key.
- Common attacks: **brute force** (try all possible keys) and **dictionary** (try common words).

### Types
- **Symmetric** (private key): same key encrypts/decrypts. Examples: DES, 3DES, AES.
- **Asymmetric** (public key): key pair — public key encrypts, private key decrypts. Examples: RSA, Diffie-Hellman, ECC.

**RSA**: based on the difficulty of factoring a large number that is the product of two primes.
- **Public key** = (n, e)
- **Private key** = (n, d)
- **Encrypt**: c = m^e mod n
- **Decrypt**: m = c^d mod n

**Diffie-Hellman**: allows two parties to establish a shared secret over an insecure channel, without prior secret exchange. Uses public variables (prime p, generator g) and individual private keys; the final key is calculated by both sides arriving at the same value.

Calculation (example with Alice and Bob):
1. Agreed public parameters: **p** (large prime number) and **g** (generator, primitive root of p)
   > Combined and known to all — not secret.

2. Alice chooses private key **a** and calculates her public key, sending it to Bob:
   > `A = g^a mod p`

3. Bob chooses private key **b** and calculates his public key, sending it to Alice:
   > `B = g^b mod p`

4. Alice calculates the shared secret using Bob's public key:
   > `s = B^a mod p`

5. Bob calculates the shared secret using Alice's public key:
   > `s = A^b mod p`
6. Both arrive at the same value: **s = g^(a×b) mod p**

A passive observer who sees p, g, A, and B cannot calculate `s` without solving the **discrete logarithm problem** — computationally infeasible for large values of p.

**SSH** uses RSA keys by default for authentication. `ssh-keygen` generates keys with algorithms such as DSA, ECDSA, ECDSA-SK, ED25519, ED25519-SK.

**PGP/GPG**: implementations for file encryption, digital signatures, and email confidentiality. Private keys protected by a passphrase can be cracked with John the Ripper + gpg2john.

### Hash Function
Unlike encryption: there is no key, and it must not be possible to reverse the output to the input. Any-size input → fixed-size output. Used for integrity (1 bit changed = completely different hash) and passwords.

- **Rainbow table**: pre-computed table of hashes for plaintexts, allowing rapid password discovery.
- **Salt**: random prefix/suffix added before hashing, increasing security.
- Current secure functions: **Argon2, Scrypt, Bcrypt, PBKDF2**. Avoid MD5/SHA1 (obsolete).
- Linux: hashes in `/etc/shadow` (format `$prefix$options$salt$hash`), readable only by root.
- Windows: passwords in **NTLM** (MD4 variant), stored in **SAM**; split into NT and LM hashes. Tools like `mimikatz` attempt to extract them.

**HMAC** (Keyed-Hash Message Authentication Code): combines a cryptographic hash with a secret key to verify authenticity and integrity. `HMAC(K,M) = H((K⊕opad) || H((K⊕ipad) || M))`.

### Digital Signature
Combines hash function + asymmetric cryptography to ensure **authenticity**, **integrity**, and **non-repudiation** of a message/document.

---

# Pentest and Red Team Methodology

*Level: Basic/Intermediate.*

## 2.1 Cyber Kill Chain

Framework describing the stages of an attack, from reconnaissance to exfiltration:

1. **Reconnaissance**: search public sources (social networks) for information about the target.
2. **Weaponization**: create a payload/lure (website, email, file) based on what was gathered.
3. **Delivery**: the means by which weaponization reaches the victim.
4. **Exploitation**: activation of the weaponization by the victim.
5. **Installation/Persistence**: maintain access even with disconnections (backdoors).
6. **Command and Control**: channels to command the victim's machine (e.g., HTTP/HTTPS).
7. **Actions on Objectives/Exfiltration**: data collection and export, privilege escalation.

General pentest methodology steps (summary view):
1. Information gathering
2. Enumeration / Scanning
3. Exploitation
4. Privilege escalation
5. Post-exploitation

## 2.2 Pentest Phases (detailed view — CISCO)

1. **Planning**: information gathering, vulnerability research, passive/active reconnaissance.
2. **Scanning**: active reconnaissance — port scanning, vulnerability verification, enumeration.
3. **Gaining Access**: exploitation via payload, social engineering, web/software vulnerabilities, Wi-Fi cracking.
4. **Maintaining Access**: backdoors, trojans, rootkits — without being detected, collecting valuable data.
5. **Analysis and Reporting**: product recommendations, policies, and training.

Alternative variant (6 phases):
1. Scope definition
2. Information gathering
3. Vulnerability analysis
4. Exploitation
5. Post-exploitation
6. Reporting

### Practical Applied Example (real case study)
1. Enumeration is fundamental — vulnerabilities are only detected because time was dedicated to mapping structure, headers, endpoints.
2. Small flaws accumulate: IDOR + weak password reset + upload bypass, in isolation, seem trivial, but together produce complete compromise.
3. Client-side restrictions are not real security — validation must always be server-side, with allowlists.
4. Password reset mechanisms deserve extra attention (a single design error can lead to account takeover).
5. Think like an attacker, report like a consultant — clear documentation with severity and recommendations is what adds value to the client.

## 2.3 Pentest Modalities

- **Black Box**: tester has no prior information about the target — simulates an external attacker.
- **White Box**: tester has full access to source code, architecture, and credentials — deep assessment.
- **Grey Box**: partial knowledge — balance between realism and depth.

## 2.4 Offensive Mindset

Offensive Security encompasses Vulnerability Analysis, Pentest, and Red Teaming — with increasing depth and scope in that order. Pentest seeks not only to find flaws, but to validate their real exploitability and business impact.

## 2.5 Security Best Practices (defense, but essential to know)

1. Risk assessment (knowing the value of what is protected).
2. Clear security policy (rules, responsibilities).
3. Physical security (access to servers/network cabinets).
4. HR background checks.
5. Regular and tested backups.
6. Constant patches and updates.
7. Access controls and strong authentication.
8. Incident response testing.
9. Network monitoring and management (SIEM/DLP).
10. Network security devices (next-generation firewalls).
11. Endpoint protection (enterprise anti-malware).
12. User training.
13. Encryption of sensitive data, including email.

## 2.6 Purple Team — Context and Fundamentals

The idea of "Blue" and "Red" teams comes from military lexicon, born in the war games of the 1960s to evaluate defensive readiness, analytical thinking, and decision-making.

**Red Teaming** is not exactly a team — it is a **way of thinking**: a flexible cognitive approach adapted to each organization and situation.

### Finite vs Infinite Games
Attacking and defending are asymmetric activities:
- **Attacking** is a **finite game**: time-limited, there is a winner, known players, fixed rules, pre-agreed objective.
- **Defending** is an **infinite game**: no time boundary, no winners, known and unknown players, non-fixed rules, the objective is to keep playing.

Consequences of this asymmetry:
1. **Different strategies**: defenders need continuous 24x7x365 effort, surface-level attention, prolonged task → alert fatigue. Attackers have monopoly on initiative, surprise factor, stealth.
2. **Team friction**: defense team tired and pressured over failures; attack team pressured for not finding vulnerabilities; both subject to hindsight bias from managers and peers.
3. **Rivalry**: friction between teams harms communication, creates professional divides, hinders overall security maturity.

Adversary emulation (tools like **VECTR**) and **Purple Team** exercises seek to break this rivalry, uniting attack and defense in a collaborative cycle of continuous improvement.

## 2.7 Leadership Applied to Offensive Security

The senior Red Team professional accumulates functions beyond the technical: leads teams, sells the value of the work to management, negotiates scope with clients, guides juniors, and sustains the team's credibility before the Blue Team. The competencies below emerge directly from these contexts.

**Communicate risk, not just vulnerability:**
> C-level doesn't make decisions based on CVSS 9.8 — they make them based on business impact. The senior professional translates technical findings into executive language: "this flaw allows an external attacker to access all customers' payment data in under 20 minutes, without credentials." This translation is a leadership skill, not just a technical one.

**Build trust before having authority:**
> Red Team frequently operates without formal authority over the teams it tests. The credibility that allows the Blue Team to receive a critical finding without going into defensive mode comes from a relationship built over time — not from a title. Teams that mutually respect each other produce quality Purple Team work; teams with rivalry produce reports no one reads.

**Guide without creating dependency:**
> A junior analyst who only runs tools is an operational risk — if they leave, the team loses capacity. The senior who teaches the reasoning behind the technique (why this payload, why this vector, why this sequence) multiplies team capacity rather than concentrating it.

**Prioritize impact, not volume:**
> In a pentest with limited time, finding 40 low-severity vulnerabilities has less value than finding 3 high-severity ones and demonstrating them with proof of concept. Knowing what to discard is just as important as knowing what to exploit — and this requires judgment, not just technique.

**Sustain pace without burning the team:**
> Red Team work has intensity peaks (long exercises, report deadlines, incident response). Leaders who don't manage this produce high turnover in roles where accumulated knowledge is critical. Building sustainable cadence — including lessons-learned reviews after each exercise — is management, not weakness.

**Accept that technical authority has limits:**
> The most technically skilled professional is not always the best person to lead the project. Recognizing this — and placing the right person in the right role, even if it's someone else — is what separates the specialist from the leader.

---

## 2.8 Leadership Fundamentals (base reference)

Summary of "Leadership Laws" (John Maxwell):
- **Law of the Lid**: leadership ability determines a person's level of effectiveness.
- **Law of Influence**: leadership is, above all, influence.
- **Law of Process**: leadership develops daily, not overnight.
- **Law of Solid Foundation**: trust is the foundation of leadership.
- **Law of Connection**: leaders touch the heart before asking for a hand.
- **Law of the Inner Circle**: a leader's potential is defined by those closest to them.
- **Law of Empowerment**: only secure leaders empower others.
- **Law of Victory**: leaders find ways for the team to win — celebrate together.
- **Law of Priorities**: movement is not the same as accomplishment.
- **Law of Sacrifice**: leading requires giving up, it is a two-way street.

A **Leader** inspires, motivates alongside, listens, guides, and develops people. A **Boss** commands, demands, imposes top-down decisions, and controls people. Core qualities: character, experience, relationships, empathy, resilience, self-awareness, emotional intelligence.

---

# Reconnaissance and Enumeration

*Level: Intermediate. "It is the most important phase of Pentest."*

## 3.1 Information Gathering (OSINT)

Information Gathering is the collection of data about people and systems using open sources.

### Google Hacking / Dorking
Advanced search operators:

| Operator | Function |
|---|---|
| `site:` | restricts results to a domain |
| `inurl:` | searches for term in the URL |
| `filetype:` | searches by file extension |
| `intitle:` | searches for term in page title |
| `intext:` | searches for term in body text |
| `cache:` | displays Google's cached version |

Subdomain enumeration example: `site:*.target.com -site:www.target.com`.

### Other OSINT Sources
- **[Hunter.io](https://hunter.io)**: collects corporate emails associated with a domain.
- **[Have I Been Pwned](https://haveibeenpwned.com)** / **[leak-lookup.com](https://leak-lookup.com)**: checks credential breaches.
- **[Pastebin](https://pastebin.com)**: search for publicly posted content (often leaked credentials).
- **[TheHarvester](https://github.com/laramies/theHarvester)**: collects emails, subdomains, hosts, employee names, open ports, and banners from multiple public sources (search engines, PGP servers, Shodan).
- **[Tor](https://www.torproject.org)**: anonymous browsing for research without exposing origin.
- **[Maltego](https://www.maltego.com)**: visually correlates data from open sources (people, companies, domains, IPs, files).
- **[Recon-ng](https://github.com/lanmaster53/recon-ng)**: Python web reconnaissance framework with convenience functions and integrated database.

## 3.2 Advanced Information Gathering

### Internet Infrastructure
- **IANA** (Internet Assigned Numbers Authority): authority managing global IP address allocation.
- **Root Servers**: root DNS servers.
- **RIR/NIR** (Regional/National Internet Registry): distribute IP blocks regionally.
- **WHOIS**: query domain registration data (`whois domain.com`).

### Passive/Active Reconnaissance Tools
- **[Shodan](https://www.shodan.io)**: search engine for internet-connected devices (servers, cameras, industrial systems).
  - Available filters: `country:`, `port:`, `org:`, `hostname:`
  - E.g.: `apache 2.4.1` returns servers announcing that version — useful combined with known CVEs
- **[Censys](https://censys.io)**: similar to Shodan, indexes hosts and certificates.
- **[VirusTotal](https://www.virustotal.com)**: aggregates 70+ antivirus engines for analyzing suspicious files/links.
- **robots.txt**: reveals which directories the site asks not to index (may point to sensitive areas).
- **curl -v**: displays detailed HTTP headers (server, language/version).
- **WhatWeb**: identifies technologies, versions, emails, SQL errors on a domain.
- **Wappalyzer**: browser extension that identifies frameworks, CMS, payment processors, and other technologies used on a site.

## 3.3 Subdomain Enumeration

Three main methods: **Brute Force, OSINT, and Virtual Hosts**.

- **Certificate Transparency (CT)**: public records of SSL/TLS certificates issued for a domain, searchable at **[crt.sh](https://crt.sh)** — reveals historically registered subdomains.
- **DNS Brute Force**: testing thousands of subdomains from a wordlist.
- **[Sublist3r](https://github.com/aboul3la/Sublist3r)**: tool that accelerates discovery via OSINT.
- **Virtual Hosts**: subdomains are not always in public DNS — they may be in the developer's `/etc/hosts`. Servers host multiple sites on a single IP, differentiating by `Host` header. Tested with `ffuf -H "Host: FUZZ.domain.com"`.

## 3.4 Web Content Discovery

Hidden content: team pages, old versions, backups, configuration files, admin panels.

### Manual Verification
- `/robots.txt`, `/sitemap.xml` — clues about site structure.
- **Favicon**: can identify the framework used (OWASP icon database).
- HTTP headers (`Server`, `X-Powered-By`) reveal the tech stack.

### OSINT
- **[WayBack Machine](https://web.archive.org)**: archived page history, may reveal old content still accessible.
- **GitHub**: searching by company name may reveal repositories with credentials or leaked code in commit history.
- **S3 Buckets**: `https://{name}.s3.amazonaws.com` — common patterns: `{company}-assets`, `-backup`, `-www`, `-dev`. Misconfigured permissions expose public files.

### Automated Discovery
```
ffuf -w wordlist -u http://IP/FUZZ
dirb http://IP/ wordlist
gobuster dir --url http://IP/ -w wordlist
```

## 3.5 Directory/Domain Scanning Tools

- **[WHATWEB](https://github.com/urbanadventurer/WhatWeb)**: collects systems, versions, emails, SQL errors on a domain.
- **[DNSMAP](https://github.com/resurrecting-open-source-projects/dnsmap)**: checks common subdomains via wordlist.
- **[DIRB](https://github.com/v0re/dirb)**: folder/file brute-force, simple, no threads.
- **[DIRBUSTER](https://github.com/KajanM/DirBuster)**: brute-force with GUI (Java), supports threads and recursion.
- **[GOBUSTER](https://github.com/OJ/gobuster)**: written in Go, popular, supports threads but no native recursion.
- **[FEROXBUSTER](https://github.com/epi052/feroxbuster)**: written in Rust, stable, performance-focused.
- **[DIRSEARCH](https://github.com/maurosoria/dirsearch)**: allows pausing/resuming scanning, but sequential.

### Gobuster — Main Flags
```
gobuster dir -u URL -w wordlist -t 64       # directory mode
gobuster dns -d domain.com -w wordlist     # enumerate subdomains
gobuster vhost -u URL -w wordlist          # virtual host brute force
```
Useful flags: `-x` (extensions), `-c` (cookie), `-H` (header), `-s`/`-b` (filter status codes), `-r` (follow redirects), `--delay` (avoid detection).

## 3.6 Scanning

- **Network Scanner**: discovers structure, active/inactive hosts.
- **Port Scanner**: identifies open/closed ports, services, and versions.

**Ping Sweep:**
- Sending ICMP Echo Request packets to an IP range;
- Those that respond with Echo Reply are active.

> ⚠️ **Warning:** no response does not confirm a host is offline (there may be a firewall or host configured to ignore ICMP).

ICMP packet TTL: Linux = 64, Windows = 128.

Incomplete handshake:
- **Closed** port → returns **RA (RST-ACK)**.
- Port **filtered** by firewall → **no response**.

### NMAP
Network scanning/security auditing tool for host and service discovery.
```
nmap -sS -sV -sC target       # SYN scan + version + default scripts
```
NSE (Nmap Scripting Engine): scripts test common problems, brute force, protocol analysis, and basic vulnerability detection.

## 3.7 Service Enumeration

**Objectives:**
- Identify service banner/version;
- Identify web technologies used, framework/CMS;
- Analyze source code for leaks (usernames, passwords, comments).

| Service (port) | Tools |
|---|---|
| HTTP/HTTPS (80/443) | DIRB, DIRBUSTER, GOBUSTER, FEROXBUSTER, NIKTO, DIRSEARCH |
| SMB/RPC (445/139) | SMBCLIENT, ENUM4LINUX, SMBMAP, CRACKMAPEXEC, RPCCLIENT |
| FTP (21) | native FTP client |
| SSH (22) | HYDRA (brute force) |
| SMTP (25) | SMTP-USER-ENUM |
| SNMP (161) | SNMP-CHECK, ONESIXTYONE |
| NFS (111) | NFS-COMMON, SHOWMOUNT |

- **[NIKTO](https://github.com/sullo/nikto):**
  - Tests web servers for configuration errors, default/insecure files, outdated servers;
  - Not stealthy, prioritizes thoroughness.

- **[SMBClient](https://www.samba.org/samba/docs/current/man-html/smbclient.1.html) / [SMBMap](https://github.com/ShawnDEvans/smbmap):**
  - Interact with SMB shares (download/upload, permissions);
  - Anonymous login frequently reveals public read access.

- **[ENUM4LINUX](https://github.com/CiscoCXSecurity/enum4linux):**
  - Automates SMB/RPC enumeration (shares, users, groups).

- **[CRACKMAPEXEC](https://github.com/byt3bl33d3r/CrackMapExec):**
  - Post-exploitation tool focused on Active Directory environments, supports multiple protocols (SMB, WinRM, MSSQL, LDAP, SSH);
  - Enumeration: OS version, shares, users, groups, password policies, SMB signing;
  - Authentication: tests credentials across multiple hosts simultaneously (credential spraying), supports Pass-the-Hash;
  - Remote code execution via WMI, schtasks, MMC, or PSExec;
  - Credential dumping: SAM, LSA, NTDS.dit, LSASS (via modules like Mimikatz);
  - BloodHound integration for mapping attack paths in AD.

- **SNMP ([onesixtyone](https://github.com/trailofbits/onesixtyone) / [snmp-check](https://gitlab.com/kalilinux/packages/snmpcheck)):**
  - Network management protocol;
  - Default community strings (`"public"`) frequently expose system information.

- **MySQL Enumeration ([NSE scripts](https://nmap.org/nsedoc/categories/discovery.html)):**
  - Via NSE scripts (`--script nmap*`) reveals anonymous/root access without password;
  - Also possible via Metasploit.

## 3.8 Traffic Capture

- **[WIRESHARK](https://www.wireshark.org)**: GUI for detecting network problems, security anomalies (intruding hosts, abnormal ports), inspecting protocols. Allows marking/commenting packets, exporting, and using "Follow TCP Stream".
- **[TCPDUMP](https://www.tcpdump.org)**: command line, captures and filters packets.
```
tcpdump -i eth0 -w capture.pcap          # saves capture
tcpdump -r capture.pcap                  # reads file
tcpdump host IP and port 80              # combined filter
tcpdump -nn -v                           # no name resolution, verbose
```
**Logical operators:** `and`, `or`, `not`

**Filters:**
- `src/dst host` — filter by source/destination IP
- `src/dst port` — filter by source/destination port
- Protocol: `ip`, `tcp`, `udp`, `icmp`
- `greater`/`less` — filter by packet size

### Sniffing and MITM (network attacks)
Sniffing captures unencrypted traffic (credentials, messages). More difficult today with TLS widely adopted, but effective against internal networks without encryption, legacy systems, IoT.
Tools:
- [TCPDUMP](https://www.tcpdump.org)
- [WIRESHARK](https://www.wireshark.org)
- [TSHARK](https://tshark.dev)
- [TCPFLOW](https://github.com/simsong/tcpflow)
- [NGREP](https://github.com/jpr5/ngrep)
- [NETWORKMINER](https://www.netresec.com/?page=NetworkMiner)

**Man-in-the-Middle:**

Techniques:
- **ARP Spoofing**: associates the attacker's MAC with the gateway's IP
- **DNS Spoofing**: false DNS responses redirect traffic
- **Rogue Access Points**: fake Wi-Fi access point
- **BGP Hijacking**: interception at routing level

Mitigations: HSTS, Certificate Transparency, Certificate Pinning, DANE

Tools:
- [Bettercap](https://www.bettercap.org)
- [Ettercap](https://www.ettercap-project.org)
- [mitmproxy](https://mitmproxy.org)
- [Responder](https://github.com/lgandx/Responder)

