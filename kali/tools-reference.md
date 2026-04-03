# Kali Linux — Tools Reference

Source: https://www.kali.org/tools/
Captured: 2026-03-07

This file lists the major tools available in Kali Linux, organized by category, with descriptions sourced from the official Kali tools page.

---

## Network Scanning

| Tool | Description | Key Commands |
|------|-------------|-------------|
| **Nmap** | Port scanner and network mapper | `nmap`, `ncat`, `ndiff`, `nping`, `zenmap` (GUI) |
| **Masscan** | High-speed port scanner (faster than Nmap for large ranges) | `masscan` |
| **Netdiscover** | ARP network device discovery | `netdiscover` |
| **ARP-Scan** | ARP network scanner with device identification | `arp-scan` |
| **Arping** | ARP ping utility for host discovery | `arping` |

## Web Application Testing

| Tool | Description | Key Commands |
|------|-------------|-------------|
| **Burp Suite** | Integrated penetration testing platform for web apps | `burpsuite` |
| **Nikto** | Web server vulnerability scanner | `nikto` |
| **SQLMap** | Automated SQL injection detection and exploitation | `sqlmap` |
| **Gobuster** | Directory and DNS brute-force discovery | `gobuster` |
| **FFuf** | Fast web fuzzer for content discovery | `ffuf` |
| **Dirb** | Web content scanner using wordlists | `dirb` |
| **DirBuster** | Multi-threaded Java-based directory brute-force | `dirbuster` |
| **Dirsearch** | Directory and file discovery tool | `dirsearch` |
| **Feroxbuster** | Recursive directory and file brute-force (Rust-based) | `feroxbuster` |
| **WFuzz** | Web application fuzzing tool | `wfuzz` |
| **Wapiti** | Web application vulnerability scanner | `wapiti` |
| **WAFw00f** | Web application firewall (WAF) detection | `wafw00f` |
| **WhatWeb** | Website identification and fingerprinting | `whatweb` |
| **WPScan** | WordPress vulnerability scanner | `wpscan` |
| **BeEF-XSS** | Browser exploitation framework for XSS testing | `beef-xss` |
| **XSSer** | XSS vulnerability scanner and automated exploiter | `xsser` |
| **SQLNinja** | Blind SQL injection exploitation tool | `sqlninja` |
| **Caido** | Modern web security testing platform | `caido` |
| **WebSploit** | Web penetration testing framework | `websploit` |
| **Arjun** | HTTP parameter discovery for hidden parameters | `arjun` |
| **EyeWitness** | Website screenshot and reconnaissance tool | `eyewitness` |

## Wireless Security

| Tool | Description | Key Commands |
|------|-------------|-------------|
| **Aircrack-ng** | WiFi security auditing suite (20+ tools) | `aircrack-ng`, `airmon-ng`, `airodump-ng`, `aireplay-ng`, `airbase-ng` |
| **Wifite** | Automated WiFi penetration testing | `wifite` |
| **Reaver** | WPS brute-force attack tool | `reaver` |
| **Bully** | Alternative WPS brute-force utility | `bully` |
| **Cowpatty** | WPA/WPA2 PSK password cracking | `cowpatty` |
| **Fern WiFi Cracker** | Graphical WiFi security auditing (GUI) | `fern-wifi-cracker` |
| **WiFiPumpkin3** | Rogue access point and phishing framework | `wifipumpkin3` |
| **WiFiPhisher** | Automated WiFi phishing attacks | `wifiphisher` |
| **Airgeddon** | Comprehensive WiFi penetration testing framework | `airgeddon` |

## Password Attacks

| Tool | Description | Key Commands |
|------|-------------|-------------|
| **Hydra** | Fast network logon cracker (parallel) | `hydra`, `hydra-wizard`, `dpl4hydra`, `pw-inspector` |
| **Hashcat** | GPU-accelerated password cracker (most formats) | `hashcat` |
| **John the Ripper** | Offline password cracker (90+ format converters) | `john`, `unshadow`, `unique` |
| **Medusa** | Fast parallel network login cracker | `medusa` |
| **Crunch** | Wordlist generator for custom password lists | `crunch` |
| **CeWL** | Custom wordlist generator scraped from target websites | `cewl` |
| **Hash-Identifier** | Identify hash types from hash strings | `hash-identifier` |

## Exploitation Frameworks

| Tool | Description | Key Commands |
|------|-------------|-------------|
| **Metasploit Framework** | Comprehensive penetration testing framework | `msfconsole`, `msfvenom`, `msfrpc` |
| **Armitage** | Graphical Metasploit front-end with team server | `armitage`, `teamserver` |
| **SET (Social Engineer Toolkit)** | Social engineering attacks and phishing campaigns | `setoolkit` |

## Post-Exploitation

| Tool | Description | Key Commands |
|------|-------------|-------------|
| **BloodHound** | Active Directory attack path visualization | `bloodhound` |
| **SharpHound** | Active Directory data collector for BloodHound | `sharphound` |
| **Impacket-Scripts** | 70+ scripts for Windows/AD attacks | `impacket-*` (many scripts) |
| **Mimikatz** | Windows credential extraction (password hashes, tickets) | `mimikatz` |
| **NetExec** | Network exploitation suite (CrackMapExec successor) | `netexec`, `nxc` |
| **CrackMapExec** | Windows network penetration testing framework | `crackmapexec`, `cme` |
| **Evil-WinRM** | WinRM shell for Windows Remote Management exploitation | `evil-winrm` |
| **Rubeus** | Kerberos ticket manipulation and attacks | `rubeus` |
| **BloodyAD** | Active Directory privilege escalation | `bloodyad` |

## OSINT / Reconnaissance

| Tool | Description | Key Commands |
|------|-------------|-------------|
| **theHarvester** | Email, subdomain, and IP gathering from public sources | `theHarvester` |
| **Sherlock** | Social media username enumeration across platforms | `sherlock` |
| **Maltego** | Data mining, link analysis, and graphical OSINT | `maltego` |
| **Recon-ng** | Modular web reconnaissance framework | `recon-ng` |
| **SpiderFoot** | Automated OSINT intelligence gathering | `spiderfoot` |
| **Amass** | Subdomain enumeration and network mapping | `amass` |
| **Subfinder** | Fast passive subdomain discovery | `subfinder` |
| **Sublist3r** | Subdomain enumeration using search engines | `sublist3r` |
| **Assetfinder** | Subdomain and related domain enumeration | `assetfinder` |
| **EmailHarvester** | Email address harvesting from public sources | `emailharvester` |
| **Dmitry** | Passive information gathering (whois, ports, emails) | `dmitry` |

## DNS Tools

| Tool | Description | Key Commands |
|------|-------------|-------------|
| **DNSenum** | DNS enumeration and subdomain discovery | `dnsenum` |
| **DNSRecon** | DNS auditing, zone transfers, brute-force | `dnsrecon` |
| **DNSChef** | DNS proxy and spoofing tool | `dnschef` |
| **Fierce** | DNS reconnaissance and subdomain enumeration | `fierce` |

## Network Analysis / Traffic

| Tool | Description | Key Commands |
|------|-------------|-------------|
| **Wireshark** | GUI packet analyzer | `wireshark`, `tshark`, `stratoshark` |
| **TCPDump** | Command-line packet capture and analysis | `tcpdump` |
| **Scapy** | Python packet manipulation and crafting library | `scapy` |
| **HPing3** | TCP/IP packet crafting for network testing | `hping3` |
| **Netcat** | Network Swiss army knife (read/write TCP/UDP) | `nc`, `ncat` |
| **Socat** | Advanced relay for bidirectional data streams | `socat` |

## Man-in-the-Middle / Network Attacks

| Tool | Description | Key Commands |
|------|-------------|-------------|
| **Bettercap** | Advanced network attack framework (MITM, sniffing) | `bettercap` |
| **Ettercap** | MITM framework with ARP poisoning (GUI and CLI) | `ettercap`, `ettercap-graphical` |
| **Responder** | LLMNR/NBT-NS/MDNS poisoning and credential capture | `responder` |
| **Mitm6** | IPv6 man-in-the-middle via DHCPv6 | `mitm6` |

## Vulnerability Scanning

| Tool | Description | Key Commands |
|------|-------------|-------------|
| **Nuclei** | Template-based vulnerability scanner | `nuclei` |
| **Legion** | Automated penetration testing orchestration | `legion` |
| **SARA** | Security auditor's research assistant | `sara` |
| **Snort** | Network intrusion detection and prevention system | `snort` |

## Forensics

| Tool | Description | Key Commands |
|------|-------------|-------------|
| **Autopsy** | Digital forensics platform (GUI) | `autopsy` |
| **TestDisk** | Disk recovery and partition repair | `testdisk`, `photorec` |

## Steganography

| Tool | Description | Key Commands |
|------|-------------|-------------|
| **Steghide** | Embed/extract data hidden in image/audio files | `steghide` |
| **StegoSuite** | GUI-based steganography tool | `stegosuite` |

## Network Utilities

| Tool | Description | Key Commands |
|------|-------------|-------------|
| **Macchanger** | MAC address spoofing and randomization | `macchanger` |

## Fuzzing

| Tool | Description | Key Commands |
|------|-------------|-------------|
| **SPIKE** | Protocol fuzzing framework (30+ protocol handlers) | `spike-generic_*` |
| **BED** | Fuzzing tool for network daemons | `bed` |

## System Auditing

| Tool | Description | Key Commands |
|------|-------------|-------------|
| **Tiger** | Security auditing and system hardening | `tiger` |
| **YARA** | Malware pattern matching and identification | `yara`, `yarac` |

## SSL/TLS Testing

| Tool | Description | Key Commands |
|------|-------------|-------------|
| **SSLScan** | SSL/TLS configuration and cipher enumeration | `sslscan` |

## WebDAV

| Tool | Description | Key Commands |
|------|-------------|-------------|
| **Cadaver** | Command-line WebDAV client | `cadaver` |

## Training / Labs

| Tool | Description |
|------|-------------|
| **DVWA** | Damn Vulnerable Web Application — intentionally vulnerable web app for learning |

---

## Installing Individual Tools

All Kali tools are available via `apt`:

```bash
sudo apt update
sudo apt install -y <tool-name>
```

For example:

```bash
sudo apt install -y metasploit-framework
sudo apt install -y nmap
sudo apt install -y burpsuite
```

## Metapackages (Install Groups of Tools)

Install curated groups of tools:

```bash
# Default Kali toolset
sudo apt install -y kali-linux-default

# Headless (no GUI tools)
sudo apt install -y kali-linux-headless

# Top 10 tools
sudo apt install -y kali-tools-top10

# All tools (very large)
sudo apt install -y kali-linux-everything

# Category-specific metapackages
sudo apt install -y kali-tools-web           # Web application tools
sudo apt install -y kali-tools-wireless      # Wireless tools
sudo apt install -y kali-tools-passwords     # Password attack tools
sudo apt install -y kali-tools-exploitation  # Exploitation tools
sudo apt install -y kali-tools-forensics     # Digital forensics tools
sudo apt install -y kali-tools-sniffing-spoofing  # MITM and sniffing
sudo apt install -y kali-tools-post-exploitation   # Post-exploitation tools
```

## Full Tool Listing

For the complete, always-up-to-date tool listing, see: https://www.kali.org/tools/

Each tool page includes:
- Tool description and version
- All included commands
- Screenshots (where applicable)
- Links to upstream documentation
