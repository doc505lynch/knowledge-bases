# Kali Linux Docker Container - Security Tools Knowledge Base

Generated: 2026-03-07
Container: `kali` on server 83.136.219.237
Kali version: 2026.1 (kali-linux-headless)

## Overview

This knowledge base documents the security tools installed in the Kali Linux Docker container. Tools are organized by category.

## Tool Categories

| File | Category | Tools Documented |
|------|----------|-----------------|
| [scanning-recon.md](scanning-recon.md) | Scanning & Reconnaissance | nmap, masscan, nikto, gobuster, dirb, wfuzz, dnsrecon, fierce, whois, whatweb, wafw00f, netdiscover, arp-scan, amass |
| [web-exploitation.md](web-exploitation.md) | Web Exploitation | sqlmap, wpscan, ffuf, commix, davtest, wfuzz |
| [exploitation.md](exploitation.md) | Exploitation Frameworks | msfconsole, msfvenom, searchsploit, msfpc |
| [password-attacks.md](password-attacks.md) | Password Attacks | john, hashcat, hydra, crunch, cewl, hashid |
| [wireless.md](wireless.md) | Wireless Attacks | aircrack-ng, airodump-ng, airmon-ng, reaver, wifite, bully, kismet |
| [smb-active-directory.md](smb-active-directory.md) | SMB & Active Directory | netexec, enum4linux, smbmap, rpcclient, impacket-scripts, crackmapexec |
| [sniffing-mitm.md](sniffing-mitm.md) | Sniffing & MITM | tcpdump, tshark, responder, ettercap, dsniff |
| [forensics.md](forensics.md) | Forensics | binwalk, sleuthkit, bulk-extractor, scalpel, testdisk |
| [misc.md](misc.md) | Miscellaneous | netcat, socat, curl, wget, proxychains4, hydra |

## Notable Installed Packages (Security-Focused)

### Frameworks
- `metasploit-framework` 6.4.112
- `powershell-empire` 6.4.1
- `exploitdb` (searchsploit) 20260212

### Scanning
- `nmap` 7.98
- `masscan` 1.3.2
- `nikto` 2.5.0
- `gobuster` 3.8.2
- `amass` 5.0.1
- `ffuf` 2.1.0

### Web
- `sqlmap` 1.10.2
- `wpscan` 3.8.28
- `wfuzz` 3.1.0
- `commix` 4.1
- `whatweb` 0.6.3
- `wafw00f` 2.3.2

### Password
- `john` 1.9.0-Jumbo-1
- `hashcat` 7.1.2
- `hydra` 9.6
- `crunch` 3.6
- `cewl` 6.2.1

### Wireless
- `aircrack-ng` 1.7
- `reaver` 1.6.6
- `wifite` 2.8.2
- `kismet` 2025.09.R1
- `bully` 1.4.00

### SMB/AD
- `netexec` 1.5.1 (successor to crackmapexec)
- `enum4linux` 0.9.1
- `smbmap` 1.10.7
- `impacket-scripts` 1.10 (60+ scripts)
- `samba` / `smbclient`

### Sniffing
- `tcpdump` 4.99.5
- `tshark` 4.6.4 (Wireshark CLI)
- `responder` 3.2.2.0
- `ettercap` 0.8.4

### Forensics
- `binwalk` 2.4.3 + `binwalk3` 3.1.0
- `sleuthkit` 4.12.1
- `bulk-extractor` 2.1.1
- `testdisk` 7.2
- `scalpel` 1.60

## Tools NOT Found / Not Installed
- `feroxbuster` — not installed (ffuf serves similar purpose)
- `bettercap` — not installed
- `medusa` — not installed
- `foremost` — not installed (scalpel is similar)
- `volatility3` / `autopsy` — not installed
- `dnsx` — not installed
- `crackmapexec` — replaced by `netexec`

## Wordlists
- Package `wordlists` 2026.1.2 is installed
- Default wordlists available at `/usr/share/wordlists/`
