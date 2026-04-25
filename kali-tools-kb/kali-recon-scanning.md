# Kali Linux Reconnaissance & Scanning Tools Knowledge Base

**Classification:** Authorized Penetration Testing and Security Research Use Only  
**Last Updated:** 2026-04-25  
**Scope:** Comprehensive reference for all major recon and scanning tools in Kali Linux

---

## Table of Contents

1. [Nmap](#1-nmap)
2. [Nessus / OpenVAS](#2-nessus--openvas)
3. [theHarvester](#3-theharvester)
4. [recon-ng](#4-recon-ng)
5. [Maltego](#5-maltego)
6. [Shodan](#6-shodan)
7. [enum4linux / enum4linux-ng](#7-enum4linux--enum4linux-ng)
8. [LDAP Enumeration](#8-ldap-enumeration)
9. [DNS Recon](#9-dns-recon)
10. [OSINT Tools](#10-osint-tools)
11. [Network Discovery](#11-network-discovery)

---

## 1. Nmap

Nmap (Network Mapper) is the de facto standard for network discovery and security auditing. It sends crafted packets and analyzes responses to discover hosts, open ports, running services, OS types, and more.

**Installation:** Pre-installed on Kali. Update with `sudo apt update && sudo apt install nmap`.

**Basic syntax:**
```
nmap [scan type] [options] {target specification}
```

---

### 1.1 Scan Types

#### -sS — SYN (Stealth) Scan
The default and most popular scan. Sends a SYN packet; a SYN/ACK response indicates open, RST indicates closed. Never completes the TCP handshake, so it is faster and less likely to be logged by older systems.

```bash
sudo nmap -sS 192.168.1.0/24
sudo nmap -sS -p 80,443,8080 10.10.10.5
```

- Requires root/sudo (raw socket access)
- Does NOT appear in application-level logs (no full connection)
- Still visible to modern firewalls and IDS

#### -sT — TCP Connect Scan
Completes the full 3-way handshake. Slower and more detectable. Used when raw sockets are unavailable (non-root).

```bash
nmap -sT 10.10.10.5
nmap -sT -p 1-1000 192.168.50.10
```

- Will appear in target application logs
- Works without root privileges
- Use when running as unprivileged user

#### -sU — UDP Scan
Scans UDP ports. Much slower than TCP scans (no reliable open/closed response). Open ports return service data; closed ports return ICMP port unreachable.

```bash
sudo nmap -sU 10.10.10.5
sudo nmap -sU -p 53,67,68,69,123,161,500 10.10.10.5
sudo nmap -sU --top-ports 100 192.168.1.1
```

- ICMP rate limiting on targets makes UDP scanning very slow
- Combine with `-sV` to increase accuracy
- Consider `--max-retries 1` to speed up

#### -sA — ACK Scan
Sends ACK packets. Cannot determine open/closed — only filtered (firewall drops) vs. unfiltered (RST returned). Used for firewall rule mapping.

```bash
sudo nmap -sA 10.10.10.5
sudo nmap -sA -p 80,443 192.168.1.0/24
```

- All open AND closed ports return RST (unfiltered)
- Stateful firewalls drop packets silently (filtered)
- Use to map firewall rules, not to find services

#### -sN — NULL Scan
Sends packets with no TCP flags set. On RFC-compliant systems: open/filtered = no response, closed = RST. Evades some non-stateful firewalls.

```bash
sudo nmap -sN 10.10.10.5
sudo nmap -sN -p- --open 192.168.1.100
```

- Does not work against Windows (Windows always sends RST regardless)
- Works well against Unix/Linux targets
- Useful when SYN scans are blocked

#### -sF — FIN Scan
Sends packets with only the FIN flag. Same response logic as NULL scan — RST means closed, no response means open|filtered.

```bash
sudo nmap -sF 10.10.10.5
sudo nmap -sF -T2 -p 20-25,80,110,443 10.0.0.50
```

#### -sX — Xmas Scan
Sets FIN, PSH, and URG flags simultaneously (lights the packet up like a Christmas tree). Same interpretation as NULL and FIN scans.

```bash
sudo nmap -sX 10.10.10.5
sudo nmap -sX --open -p 22,80,443,8080,8443 10.10.10.0/24
```

---

### 1.2 Timing Templates (-T0 to -T5)

Controls the aggressiveness and speed of scanning. Affects retransmission delays, parallelism, and scan timeouts.

| Template | Name | Description | Use Case |
|----------|------|-------------|----------|
| -T0 | Paranoid | 5-minute wait between probes | IDS evasion, maximum stealth |
| -T1 | Sneaky | 15-second wait | Slow IDS evasion |
| -T2 | Polite | Slows down to consume less bandwidth | Avoid overloading targets |
| -T3 | Normal | Default; adaptive | Standard scans |
| -T4 | Aggressive | Faster, assumes fast reliable network | LAN, CTF, pentest engagements |
| -T5 | Insane | Sacrifices accuracy for speed | Fastest possible, may miss results |

```bash
# Stealthy external scan — evade IDS
sudo nmap -sS -T1 -p 80,443 203.0.113.10

# Fast internal network scan
sudo nmap -sS -T4 -p- 10.10.10.0/24

# CTF / lab environment
sudo nmap -sS -T5 192.168.56.0/24
```

**Tip:** `-T4` is the most commonly used in authorized pentests on reliable networks. Never use `-T5` against production systems — it can cause service disruption.

---

### 1.3 Port Specification

#### -p — Specify Port(s)
```bash
nmap -p 80                    # Single port
nmap -p 80,443,8080           # Multiple ports
nmap -p 1-1000                # Range
nmap -p 22,80,100-200,8000-9000  # Mixed
nmap -p U:53,T:80,443         # Protocol-specific
nmap -p "*"                   # All 65535 ports (same as -p-)
```

#### -p- — All 65535 Ports
```bash
sudo nmap -p- -T4 10.10.10.5
sudo nmap -p- --open -sV 192.168.1.100
```

#### --top-ports — Most Common Ports
```bash
nmap --top-ports 100 10.10.10.5    # Top 100 most common
nmap --top-ports 1000 192.168.1.0/24
nmap --top-ports 20 10.10.10.0/24  # Quick sweep
```

Port frequency data comes from `/usr/share/nmap/nmap-services`.

---

### 1.4 Output Formats

#### -oN — Normal Output
Human-readable, as displayed on screen.
```bash
nmap -sS 10.10.10.5 -oN scan_results.txt
```

#### -oX — XML Output
Structured XML, machine-parseable. Used by Metasploit, Dradis, and other tools.
```bash
nmap -sS 10.10.10.5 -oX scan_results.xml
# Parse with: xsltproc scan_results.xml -o scan_results.html
```

#### -oG — Grepable Output
One line per host, easy to parse with grep/awk.
```bash
nmap -sS 10.10.10.0/24 -oG scan_results.gnmap
grep "80/open" scan_results.gnmap | awk '{print $2}'
```

#### -oA — All Formats Simultaneously
Saves .nmap, .xml, and .gnmap in one command.
```bash
nmap -sS -sV -O -p- 10.10.10.5 -oA full_scan_target
# Creates: full_scan_target.nmap, full_scan_target.xml, full_scan_target.gnmap
```

---

### 1.5 OS Detection (-O)

Sends TCP/IP probes and compares fingerprints against the nmap-os-db database. Requires at least one open and one closed port for accuracy.

```bash
sudo nmap -O 10.10.10.5
sudo nmap -O --osscan-guess 10.10.10.5    # Aggressive guess
sudo nmap -O --max-os-tries 1 10.10.10.0/24  # Faster, one attempt
```

**Output interpretation:**
```
OS details: Linux 4.15 - 5.6
Network Distance: 1 hop
```

- `Aggressive OS guesses` appear when confidence is below 90%
- Works best with a direct routed path (no NAT between you and target)

---

### 1.6 Version Detection (-sV)

Probes open ports with service-specific payloads to identify the running application and version.

```bash
nmap -sV 10.10.10.5
nmap -sV --version-intensity 9 10.10.10.5   # Maximum probing (slow)
nmap -sV --version-intensity 0 10.10.10.5   # Version light (fast)
nmap -sV --version-light 10.10.10.5         # Alias for intensity 2
nmap -sV --version-all 10.10.10.5           # Alias for intensity 9
```

**`--version-intensity` levels:**
- 0-2: Only most likely probes (fast)
- 3-6: Default behavior
- 7-9: All probes including rare ones (slow, thorough)

**Output example:**
```
80/tcp  open  http    Apache httpd 2.4.51 ((Debian))
22/tcp  open  ssh     OpenSSH 8.4p1 Debian
443/tcp open  ssl/http nginx 1.18.0
```

---

### 1.7 Nmap Scripting Engine (NSE)

NSE scripts are Lua programs that extend nmap functionality. Located at `/usr/share/nmap/scripts/`.

#### Running Scripts
```bash
nmap --script=http-title 10.10.10.5
nmap --script=http-title,http-headers 10.10.10.5
nmap --script="http-*" 10.10.10.5           # All http scripts
nmap -sC 10.10.10.5                          # Default scripts
nmap --script default 10.10.10.5             # Same as -sC
```

#### Script Categories

| Category | Description | Examples |
|----------|-------------|---------|
| `auth` | Authentication bypass or default creds | `ftp-anon`, `http-auth-finder`, `ssh-auth-methods` |
| `brute` | Brute-force credential attacks | `ftp-brute`, `ssh-brute`, `http-brute`, `smb-brute` |
| `default` | Safe, useful scripts run with -sC | `banner`, `ssh-hostkey`, `http-title` |
| `discovery` | Network/service enumeration | `dns-brute`, `smb-enum-shares`, `snmp-info` |
| `exploit` | Exploit known vulnerabilities | `ms17-010`, `http-shellshock`, `smb-vuln-ms08-067` |
| `vuln` | Check for known CVEs (non-exploiting) | `smb-vuln-ms17-010`, `http-vuln-cve2017-5638` |
| `safe` | Low-risk scripts | Most of `discovery` and `default` |
| `intrusive` | May crash or affect target | Most `brute` and `exploit` |
| `malware` | Detect malware/backdoors | `http-malware-host`, `smtp-strangeport` |
| `fuzzer` | Send malformed/random data | `dns-fuzz`, `http-form-fuzzer` |

#### Script Arguments
```bash
nmap --script http-brute --script-args http-brute.path=/admin 10.10.10.5
nmap --script smb-brute --script-args brute.mode=user,brute.firstonly=true 10.10.10.5
nmap --script ftp-brute --script-args userdb=/usr/share/wordlists/usernames.txt,passdb=/usr/share/wordlists/rockyou.txt 10.10.10.5
```

#### High-Value Script Examples

```bash
# SMB vulnerability checks
sudo nmap -p 445 --script=smb-vuln-ms17-010 10.10.10.5
sudo nmap -p 445 --script="smb-vuln-*" 10.10.10.5

# Web application enumeration
nmap -p 80,443 --script="http-*" --script-args http.useragent="Mozilla/5.0" 10.10.10.5

# Find default credentials across all services
nmap --script=default,auth 10.10.10.5

# DNS zone transfer attempt
nmap -p 53 --script dns-zone-transfer --script-args dns-zone-transfer.domain=example.com 10.10.10.53

# FTP anonymous login
nmap -p 21 --script ftp-anon 10.10.10.5

# SNMP community string brute force
nmap -p 161 -sU --script snmp-brute 10.10.10.5

# MySQL enumeration
nmap -p 3306 --script="mysql-*" 10.10.10.5

# SSH host key and auth methods
nmap -p 22 --script ssh-hostkey,ssh-auth-methods 10.10.10.5
```

#### -A — Aggressive Scan
Combines OS detection (-O), version detection (-sV), script scanning (-sC), and traceroute.
```bash
sudo nmap -A 10.10.10.5
sudo nmap -A -T4 -p- 10.10.10.5     # Full aggressive scan
sudo nmap -A --open 10.10.10.0/24    # All hosts, open ports only
```

---

### 1.8 Traceroute
```bash
nmap --traceroute 10.10.10.5
sudo nmap -sS --traceroute -p 80 203.0.113.10
```

Reveals routing path — useful for understanding network topology and identifying intermediate filtering devices.

---

### 1.9 Evasion Techniques

#### -f — Fragment Packets
Splits packets into 8-byte fragments. Older IDS/firewalls struggle to reassemble.
```bash
sudo nmap -sS -f 10.10.10.5
sudo nmap -sS -f -f 10.10.10.5    # 16-byte fragments
sudo nmap --mtu 24 10.10.10.5     # Custom MTU (must be multiple of 8)
```

#### -D — Decoy Scanning
Sends scans appearing to originate from multiple decoy IPs, hiding the real source among them. `ME` is a placeholder for your real IP.
```bash
sudo nmap -sS -D 10.0.0.1,10.0.0.2,ME,10.0.0.3 10.10.10.5
sudo nmap -sS -D RND:10 10.10.10.5    # 10 random decoys
```

**Warning:** Decoy IPs must be live on the network for best effect. Dead IPs stand out in target logs.

#### --source-port — Spoof Source Port
Some firewalls allow traffic from "trusted" ports (53/DNS, 67/DHCP). Spoofing these can bypass filters.
```bash
sudo nmap --source-port 53 10.10.10.5
sudo nmap -g 443 10.10.10.5            # -g is shorthand for --source-port
```

#### --data-length — Append Random Data
Adds random payload data to packets, defeating some signature-based detection.
```bash
sudo nmap --data-length 25 10.10.10.5
sudo nmap -sS --data-length 50 192.168.1.0/24
```

#### --spoof-mac — Spoof MAC Address
Changes the MAC address in outgoing frames. Effective only on same-layer-2 segment.
```bash
sudo nmap --spoof-mac 00:11:22:33:44:55 10.10.10.5
sudo nmap --spoof-mac Apple 10.10.10.5       # Random Apple OUI
sudo nmap --spoof-mac 0 10.10.10.5           # Completely random MAC
```

---

### 1.10 Input / Special Options

#### -iL — Input from File
```bash
nmap -iL targets.txt
nmap -sS -sV -iL scope.txt -oA results/scan
```

`targets.txt` can contain IPs, hostnames, CIDR ranges — one per line. Blank lines and lines beginning with `#` are ignored.

#### --open — Show Only Open Ports
```bash
nmap --open 10.10.10.0/24
nmap -sS -p- --open 10.10.10.5
```

#### -6 — IPv6 Scanning
```bash
nmap -6 fe80::1%eth0
nmap -6 -sS 2001:db8::/32
```

---

### 1.11 Real-World Usage Examples

```bash
# 1. Full host enumeration — authorized pentest starting point
sudo nmap -sS -sV -O -sC -p- -T4 --open -oA /tmp/pentest/full_scan 10.10.10.5

# 2. Quick host sweep to find live hosts on /24
sudo nmap -sn 192.168.1.0/24 -oG alive_hosts.gnmap && grep "Up" alive_hosts.gnmap | awk '{print $2}' > live.txt

# 3. Targeted web app pre-engagement scan
sudo nmap -sS -sV -p 80,443,8080,8443,8000,8888,9090 --script="http-title,http-headers,http-methods,http-server-header" -oN webports_scan.txt 203.0.113.50

# 4. SMB vulnerability check (EternalBlue / WannaCry)
sudo nmap -p 139,445 --script="smb-vuln-ms17-010,smb-vuln-ms08-067,smb-security-mode,smb-enum-shares" -T4 10.10.10.0/24

# 5. Stealth external reconnaissance with evasion
sudo nmap -sS -T2 -f --data-length 25 -D RND:5 --source-port 53 -p 80,443,22,21,25,110,143,3389 --open 203.0.113.10 -oN stealth_scan.txt
```

---

## 2. Nessus / OpenVAS

Both are vulnerability scanners that go beyond port scanning to identify specific CVEs, misconfigurations, and known exploitable conditions.

### 2.1 Nessus

**Installation on Kali:**
```bash
# Download from https://www.tenable.com/downloads/nessus
dpkg -i Nessus-10.x.x-debian10_amd64.deb
sudo systemctl start nessusd
# Access at https://localhost:8834
```

**Concepts:**

- **Scan Policies:** Templates defining which plugins run, credential options, and scan behavior. Tenable ships policies for: Basic Network Scan, Advanced Scan, Credentialed Patch Audit, Web Application Tests, Malware Scan, PCI DSS Audit, etc.
- **Plugin Families:** Nessus organizes its 100,000+ plugins by OS, service, or vulnerability type:
  - `Windows` — Windows-specific vulns, patches, registry checks
  - `CGI Abuses` — Web application flaws (XSS, SQLi, directory traversal)
  - `Backdoors` — Detection of known backdoors and malware
  - `DNS` — DNS server misconfigurations
  - `Databases` — MySQL, MSSQL, Oracle, PostgreSQL vulns
  - `Default Unix Accounts` — Known default credentials
  - `Firewalls` — Firewall and router vulnerabilities
  - `FTP` — FTP service flaws
  - `Gain root remotely` — Unauthenticated RCE plugins
  - `Service detection` — Banner grabbing, service fingerprinting
  - `SMTP problems` — Mail server vulnerabilities
  - `SSL and TLS` — Certificate and cipher suite issues

**Key Scan Settings:**
- **Max simultaneous hosts:** Controls concurrency (reduce for stealth)
- **Max simultaneous checks per host:** Per-host plugin parallelism
- **Network timeout:** Seconds before giving up on a probe
- **Port scanner settings:** Use built-in TCP scanner or rely on nmap
- **Credentials:** Provide SSH, WMI/SMB, SNMP creds for credentialed scans

**Credentialed vs. Uncredentialed:**
Credentialed scans (providing OS-level credentials) dramatically increase accuracy — they can enumerate installed packages, check patch levels, read registry keys, and test local file permissions. Uncredentialed scans rely solely on network-level probes.

---

### 2.2 OpenVAS / Greenbone Vulnerability Manager (GVM)

**Installation on Kali:**
```bash
sudo apt install gvm
sudo gvm-setup         # Initial setup, feeds download (takes 20+ min)
sudo gvm-start
# Access at https://127.0.0.1:9392
# Default user: admin / (password set during setup)
```

**Architecture:**
- **GSA (Greenbone Security Assistant):** Web interface
- **GVM (Greenbone Vulnerability Manager):** Core daemon
- **OSP (OSP Scanner):** Plugin communication layer
- **NVT Feed:** Network Vulnerability Tests (~60,000+ plugins)

**Scan Configurations:**
- `Full and fast` — All checks, optimized for speed (default)
- `Full and very deep` — Thorough, slower
- `System discovery` — OS and service identification only
- `Host discovery` — Just finds live hosts
- `Empty` — Custom base (build your own policy)

**Key Concepts:**
- **Task:** A configured scan job (target + scan config + schedule)
- **Target:** IP/range + port list + credentials
- **Report:** Scan output with severity ratings (Critical/High/Medium/Low/Log)
- **Tickets:** Remediation tracking workflow
- **CVSSv3 scoring:** Used to rate findings (0.0-10.0)

**CLI via gvm-cli:**
```bash
sudo gvm-cli --gmp-username admin --gmp-password PASSWORD socket --socketpath /run/gvmd/gvmd.sock --xml "<get_tasks/>"
```

---

## 3. theHarvester

OSINT tool for gathering emails, subdomains, hostnames, employee names, and IP addresses from public sources.

**Installation:** Pre-installed on Kali. Update: `pip3 install theHarvester`

**Basic syntax:**
```
theHarvester -d <domain> -b <source> [options]
```

### 3.1 Key Flags

| Flag | Description |
|------|-------------|
| `-d` | Target domain (e.g., `example.com`) |
| `-b` | Data source(s) — comma-separated |
| `-l` | Limit results (default: 500) |
| `-f` | Output file (auto-detects .xml or .html extension) |
| `-n` | DNS reverse lookup on discovered IPs |
| `-c` | DNS brute force with default wordlist |
| `-t` | DNS TLD expansion (e.g., .com → .net, .org) |
| `-r` | DNS resolution of discovered names |
| `-s` | Start result index |
| `-v` | Verify discovered hostnames |
| `-e` | DNS server to use |

### 3.2 Sources (-b)

| Source | Data Type |
|--------|-----------|
| `google` | Emails, subdomains via Google search |
| `bing` | Emails, subdomains via Bing |
| `linkedin` | Employee names and titles |
| `hunter` | Emails (requires API key) |
| `shodan` | IPs, open ports (requires API key) |
| `virustotal` | Subdomains |
| `censys` | IPs and certificates (requires API key) |
| `certspotter` | Certificate transparency subdomains |
| `dnsdumpster` | DNS records, subdomains |
| `crtsh` | Certificate transparency (crt.sh) |
| `hackertarget` | Subdomains, hosts |
| `rapiddns` | Subdomains |
| `anubis` | Subdomains |
| `baidu` | Subdomains (Chinese searches) |
| `all` | All available sources |

**API Key configuration:** Edit `/etc/theHarvester/api-keys.yaml` or `~/.theHarvester/api-keys.yaml`
```yaml
apikeys:
  hunter:
    key: YOUR_HUNTER_API_KEY
  shodan:
    key: YOUR_SHODAN_API_KEY
  censys:
    id: YOUR_CENSYS_ID
    secret: YOUR_CENSYS_SECRET
```

### 3.3 Real-World Usage Examples

```bash
# 1. Comprehensive email and subdomain harvesting
theHarvester -d targetcorp.com -b google,bing,dnsdumpster,crtsh,certspotter -l 500 -f /tmp/harvest_targetcorp.html

# 2. LinkedIn employee enumeration (useful for spear phishing prep)
theHarvester -d targetcorp.com -b linkedin -l 200 -f employees.html

# 3. Shodan + DNS combined for IP/host mapping
theHarvester -d targetcorp.com -b shodan,hackertarget,virustotal -n -f shodan_harvest.xml

# 4. Quick recon with all sources (rate-limited, takes time)
theHarvester -d targetcorp.com -b all -l 300 -f full_harvest.html

# 5. Targeted email gathering with validation
theHarvester -d targetcorp.com -b hunter,google -l 500 -v -f emails_verified.html
```

### 3.4 Output Interpretation

- **Emails found:** Direct email addresses (often in formats like firstname.lastname@domain.com — reveals naming convention)
- **Hosts found:** Subdomains discovered (dev., staging., api., mail., vpn. are high-value)
- **IPs found:** IP addresses associated with the domain
- **Interesting URLs:** Paths found during crawling

---

## 4. recon-ng

A full-featured web reconnaissance framework modeled after Metasploit. Modules operate on a database, making it possible to chain results from one module into inputs for another.

**Installation:** Pre-installed on Kali. `pip3 install recon-ng` for latest.

**Launch:**
```bash
recon-ng
```

---

### 4.1 Framework Architecture

```
recon-ng
├── workspaces/          # Isolated engagement databases (SQLite)
├── modules/
│   ├── discovery/       # Active probing, service checking
│   ├── exploitation/    # Credential stuffing, exploitation
│   ├── import/          # Data import from files
│   ├── recon/           # Core recon modules (largest group)
│   │   ├── domains-contacts/
│   │   ├── domains-credentials/
│   │   ├── domains-hosts/
│   │   ├── hosts-hosts/
│   │   ├── hosts-ports/
│   │   └── ...
│   └── reporting/       # Export and report generation
└── keys/                # API key storage
```

### 4.2 Workspace Management

```
[recon-ng] > workspaces create targetcorp
[recon-ng] > workspaces load targetcorp
[recon-ng] > workspaces list
[recon-ng] > workspaces remove old_engagement
```

### 4.3 Database Operations

Recon-ng maintains a relational database with tables: `domains`, `hosts`, `ports`, `contacts`, `credentials`, `companies`, `locations`, `netblocks`, `vulnerabilities`, `pushpins`.

```
# View database tables
[recon-ng][targetcorp] > db schema

# Insert seed data
[recon-ng][targetcorp] > db insert domains
domain (TEXT): targetcorp.com
notes (TEXT): primary domain
[...]

# View stored results
[recon-ng][targetcorp] > db query SELECT * FROM hosts
[recon-ng][targetcorp] > db query SELECT email FROM contacts

# Show table contents
[recon-ng][targetcorp] > show hosts
[recon-ng][targetcorp] > show contacts
[recon-ng][targetcorp] > show domains
[recon-ng][targetcorp] > show ports
```

### 4.4 Module Usage

```
# Search and load modules
[recon-ng][targetcorp] > marketplace search dns
[recon-ng][targetcorp] > marketplace install recon/domains-hosts/hackertarget
[recon-ng][targetcorp] > modules load recon/domains-hosts/hackertarget

# Set options and run
[recon-ng][targetcorp][hackertarget] > options list
[recon-ng][targetcorp][hackertarget] > options set SOURCE targetcorp.com
[recon-ng][targetcorp][hackertarget] > run

# Use database result as input to next module
[recon-ng][targetcorp] > modules load recon/hosts-ports/shodan_ip
[recon-ng][targetcorp][shodan_ip] > options set SOURCE default   # "default" = pull from db
[recon-ng][targetcorp][shodan_ip] > run
```

### 4.5 Key Module Categories

#### recon/domains-hosts/ — Domain to Hostname
| Module | Source | Output |
|--------|--------|--------|
| `hackertarget` | HackerTarget API | Subdomains |
| `brute_hosts` | Built-in wordlist | Brute-force subdomains |
| `certificate_transparency` | crt.sh | Subdomains from certs |
| `bing_domain_web` | Bing search | Subdomains |
| `google_site_web` | Google search | Subdomains |
| `dnsdumpster` | DNSDumpster | Subdomains + DNS map |

#### recon/hosts-ports/ — Host to Port
| Module | Source | Output |
|--------|--------|--------|
| `shodan_ip` | Shodan | Open ports, banners |
| `censys_query` | Censys | Ports, services, certs |

#### recon/domains-contacts/ — Domain to Contacts
| Module | Source | Output |
|--------|--------|--------|
| `whois_pocs` | ARIN WHOIS | Contacts, emails |
| `hunter_io` | Hunter.io | Email addresses |
| `pgp_search` | PGP keyservers | Email addresses |

#### reporting/ — Export Results
```
[recon-ng][targetcorp] > modules load reporting/html
[recon-ng][targetcorp][html] > options set CREATOR "Adam Lynch"
[recon-ng][targetcorp][html] > options set CUSTOMER "Target Corp"
[recon-ng][targetcorp][html] > options set FILENAME /tmp/report.html
[recon-ng][targetcorp][html] > run
```

Other report formats: `reporting/csv`, `reporting/json`, `reporting/xml`, `reporting/markdown`

### 4.6 API Key Setup

```
[recon-ng] > keys list
[recon-ng] > keys add shodan_api YOUR_SHODAN_KEY
[recon-ng] > keys add hunter_io YOUR_HUNTER_KEY
[recon-ng] > keys add censys_id YOUR_CENSYS_ID
[recon-ng] > keys add censys_secret YOUR_CENSYS_SECRET
[recon-ng] > keys add github_api YOUR_GITHUB_TOKEN
[recon-ng] > keys add virustotal_api YOUR_VT_KEY
```

Keys are stored in `~/.recon-ng/keys.db` (encrypted at rest).

### 4.7 Real-World Usage Examples

```bash
# 1. Full domain recon workflow
recon-ng
> workspaces create client_corp
> db insert domains         # Enter: clientcorp.com
> marketplace install recon/domains-hosts/certificate_transparency
> modules load recon/domains-hosts/certificate_transparency
> run                       # Populates hosts table
> marketplace install recon/domains-hosts/hackertarget
> modules load recon/domains-hosts/hackertarget
> run                       # More hosts
> show hosts                # Review all discovered subdomains

# 2. Chain hosts into Shodan port data
> marketplace install recon/hosts-ports/shodan_ip
> modules load recon/hosts-ports/shodan_ip
> options set SOURCE default
> run
> show ports

# 3. Contact/email discovery
> marketplace install recon/domains-contacts/hunter_io
> modules load recon/domains-contacts/hunter_io
> options set SOURCE clientcorp.com
> run
> show contacts

# 4. Generate HTML report
> modules load reporting/html
> options set FILENAME /tmp/clientcorp_recon.html
> run
```

---

## 5. Maltego

A graphical link analysis tool for visualizing and discovering relationships between entities (people, organizations, domains, IPs, social media). Maltego uses "transforms" — small programs that query data sources and return related entities.

**Installation:** Pre-installed on Kali (Maltego CE). `sudo apt install maltego`

**Launch:** `maltego` — requires free account registration at maltego.com

---

### 5.1 Entity Types

| Entity | Description |
|--------|-------------|
| `Domain` | DNS domain (e.g., example.com) |
| `DNSName` | Subdomain or hostname |
| `IPAddress` | IPv4 or IPv6 address |
| `Netblock` | CIDR range |
| `MXRecord` | Mail exchanger record |
| `NSRecord` | Nameserver record |
| `Organization` | Company or entity |
| `Person` | Individual (name) |
| `EmailAddress` | Email address |
| `PhoneNumber` | Phone number |
| `WebSite` | URL |
| `TwitterAffiliate` | Twitter profile |
| `FacebookObject` | Facebook entity |
| `Phrase` | Free text string |
| `Document` | File or document |

---

### 5.2 Transforms

Transforms are the core of Maltego — each queries one or more data sources and returns related entities.

**Transform Hubs (data sources):**
- `Maltego Standard Transforms` (built-in, uses public data)
- `Shodan` (requires API key)
- `VirusTotal` (requires API key)
- `PassiveTotal / RiskIQ`
- `Have I Been Pwned`
- `BuiltWith`
- `ClearBit`
- `SpiderFoot HX`
- `ZoomEye`
- `Censys`

**Common transform chains:**
```
Domain → DNS Name (Subdomains)
Domain → IP Address (DNS resolution)
IP Address → Netblock (ARIN lookup)
Netblock → IP Address (expand range)
Email Address → Person (reverse lookup)
Person → Email Address (email hunt)
Domain → MX Record → Email Address
IP Address → Open Ports (Shodan)
```

**Running transforms:**
- Right-click entity → Run Transform → select transform
- Or select entity → press Ctrl+T to run all transforms

---

### 5.3 Machines

Maltego Machines are automated transform chains that run without manual intervention — like macros.

**Built-in machines:**
- `Company Stalker` — Full company OSINT from domain
- `Find Wikipedia Edits` — Find Wikipedia accounts by IP
- `Footprint L1` — Light DNS/IP footprint
- `Footprint L2` — Moderate footprint including email discovery
- `Footprint L3` — Deep footprint (many transforms, can be slow/noisy)
- `Person email address` — Find emails for a person entity
- `Twitter digger X` — Deep Twitter relationship mapping

**Running a machine:** Top menu → Machines → Run Machine → select machine → enter seed entity

---

### 5.4 Community (CE) vs. Commercial

| Feature | Community Edition (CE) | Commercial |
|---------|----------------------|------------|
| Price | Free | $999-$1999/yr |
| Transforms per run | 12 (hard limit) | Unlimited |
| Graph size | Limited | Unlimited |
| Data sources | Limited selection | Full hub access |
| Collaboration | Single user | Team features |
| API access | Limited | Full |

**CE limitations are significant for large engagements.** The 12-transform limit means graph exploration must be done methodically — expand one entity at a time.

---

### 5.5 Real-World Usage Examples

1. **Domain footprint:** Add `targetcorp.com` as Domain entity → Run Machine → Footprint L2
2. **Email to identity:** Add `john.smith@targetcorp.com` as EmailAddress → Run transforms for Person, Social profiles
3. **IP to ASN to netblock:** Add IP → `To AS Number [Routing]` → `To Netblocks [ARIN]` → expand all IPs in range
4. **Social graph mapping:** Add person → `Find on LinkedIn`, `Find on Twitter` → expand connections for org chart

---

## 6. Shodan

Shodan is a search engine that indexes internet-connected devices by scanning the entire IPv4 space and storing service banners. It provides a queryable database of open ports, service versions, SSL certificates, operating systems, and geographic/ownership data.

**Installation (CLI):**
```bash
pip3 install shodan
shodan init YOUR_API_KEY
```

---

### 6.1 CLI Commands

```bash
# Search for hosts matching a query
shodan search "apache 2.4 country:US"

# Get all information about a specific IP
shodan host 1.2.3.4

# Count results without displaying them
shodan count "product:nginx port:443"

# Get your API usage and credits
shodan info

# Download full search results to a file
shodan download --limit 1000 results.json.gz "org:\"Target Corp\""

# Parse downloaded results
shodan parse results.json.gz

# Get IP addresses from results
shodan search --fields ip_str,port "apache" > apache_hosts.txt

# Real-time stream of new Shodan scan data
shodan stream --ports 80,443,22 > stream.json
```

---

### 6.2 Search Dorks and Filters

#### Basic Filters

| Filter | Example | Description |
|--------|---------|-------------|
| `port:` | `port:3389` | Filter by port number |
| `os:` | `os:"Windows Server 2019"` | Operating system |
| `org:` | `org:"Amazon"` | Organization/ISP name |
| `hostname:` | `hostname:.targetcorp.com` | Reverse DNS hostname |
| `country:` | `country:US` | Two-letter country code |
| `city:` | `city:"Albuquerque"` | City name |
| `net:` | `net:192.168.1.0/24` | CIDR range |
| `product:` | `product:nginx` | Product name from banner |
| `version:` | `version:2.4.51` | Version number |
| `http.title:` | `http.title:"Login"` | HTTP page title |
| `http.html:` | `http.html:"phpMyAdmin"` | HTML content match |
| `ssl:` | `ssl:"targetcorp.com"` | SSL certificate content |
| `ssl.cert.subject.cn:` | `ssl.cert.subject.cn:*.targetcorp.com` | Certificate CN |
| `asn:` | `asn:AS15169` | Autonomous system number |
| `before:` | `before:01/01/2025` | Indexed before date |
| `after:` | `after:01/01/2024` | Indexed after date |
| `vuln:` | `vuln:CVE-2021-44228` | Vulnerable to CVE |
| `has_screenshot:` | `has_screenshot:true` | Has screenshot |
| `tag:` | `tag:ics` | Tagged as ICS/SCADA |

#### High-Value Dorks

```
# Default credentials pages
http.title:"Router Setup" country:US
http.title:"NETGEAR" port:80

# Exposed admin panels
http.title:"admin" http.html:"password" port:80

# Jenkins without auth
http.title:"Dashboard [Jenkins]"

# Exposed Elasticsearch
port:9200 http.title:"200 OK" all:"indices"
port:9200 json

# Exposed MongoDB
port:27017 -http.title:

# Redis no auth
port:6379 -http.title:

# SCADA/ICS systems
tag:scada
tag:ics country:US

# VNC servers
port:5900 has_screenshot:true

# Printers
http.title:"HP LaserJet" country:US

# RDP exposed to internet
port:3389 os:"Windows"

# Webcams
http.title:"Network Camera" product:"Hikvision"
has_screenshot:true port:8080 http.title:"webcam"

# Citrix gateways
http.title:"Citrix Gateway" country:US

# Pulse Secure VPN
http.title:"Pulse Connect Secure"

# Org-specific recon
org:"Target Corp" 
hostname:.targetcorp.com
ssl.cert.subject.cn:"targetcorp.com"
net:198.51.100.0/24
```

---

### 6.3 API Integration

```python
import shodan

api = shodan.Shodan('YOUR_API_KEY')

# Search
results = api.search('apache country:US port:443')
for result in results['matches']:
    print(f"{result['ip_str']}:{result['port']} - {result.get('org', 'N/A')}")

# Host lookup
host = api.host('8.8.8.8')
print(f"Organization: {host.get('org', 'N/A')}")
print(f"Ports: {host['ports']}")

# Count results
count = api.count('nginx')
print(f"Total nginx servers indexed: {count}")

# Exploit search (requires subscription)
results = api.exploits.search('heartbleed')
```

---

### 6.4 Real-World Usage Examples

```bash
# 1. Map an organization's external footprint
shodan search org:\"Target Corporation\" --fields ip_str,port,product,version -l 500

# 2. Find all subdomains indexed by Shodan
shodan search hostname:.targetcorp.com --fields ip_str,hostnames,port,product

# 3. Identify SSL certificate exposure
shodan search ssl.cert.subject.cn:\"*.targetcorp.com\" --fields ip_str,port,ssl.cert.subject.cn

# 4. Find exposed databases in target netblock
shodan search net:203.0.113.0/24 port:3306,5432,27017,6379,9200

# 5. Check specific IP for all known services and vulns
shodan host 203.0.113.42
```

---

## 7. enum4linux / enum4linux-ng

SMB enumeration tools for extracting information from Windows and Samba systems without full credentials. enum4linux wraps `smbclient`, `rpcclient`, `net`, and `nmblookup`.

**Installation:**
```bash
# enum4linux (legacy, Perl)
sudo apt install enum4linux

# enum4linux-ng (modern Python rewrite, recommended)
pip3 install enum4linux-ng
# OR
git clone https://github.com/cddmp/enum4linux-ng && cd enum4linux-ng && pip3 install -r requirements.txt
```

---

### 7.1 enum4linux Flags

| Flag | Description |
|------|-------------|
| `-a` | All simple enumeration (equivalent to -U -S -G -P -r -o -n -i) |
| `-U` | Enumerate users |
| `-S` | Enumerate shares |
| `-G` | Enumerate groups and members |
| `-P` | Get password policy |
| `-d` | Detailed information for shares and users |
| `-r` | Enumerate users via RID cycling |
| `-R 500-600` | RID range for cycling |
| `-u` | Username (for authenticated enumeration) |
| `-p` | Password (for authenticated enumeration) |
| `-s /path/shares.txt` | Brute force shares from wordlist |
| `-o` | Get OS information |
| `-n` | NetBIOS name lookup |
| `-i` | Get printer information |
| `-w` | Specify workgroup/domain |
| `-v` | Verbose output |

---

### 7.2 Basic Usage

```bash
# Full enumeration (unauthenticated)
enum4linux -a 10.10.10.5

# User enumeration via RID cycling
enum4linux -U -r 10.10.10.5

# Share enumeration only
enum4linux -S 10.10.10.5

# Password policy
enum4linux -P 10.10.10.5

# Authenticated enumeration
enum4linux -a -u administrator -p 'Password123' 10.10.10.5

# Enumerate with specific domain
enum4linux -a -w TARGETDOMAIN 10.10.10.5
```

---

### 7.3 enum4linux-ng Usage

enum4linux-ng provides JSON/YAML output, better error handling, and supports newer SMB dialects.

```bash
# Full enumeration
enum4linux-ng -A 10.10.10.5

# With credentials
enum4linux-ng -A -u administrator -p 'Password123' 10.10.10.5

# JSON output
enum4linux-ng -A -oJ /tmp/enum_results.json 10.10.10.5

# YAML output
enum4linux-ng -A -oY /tmp/enum_results.yaml 10.10.10.5

# Verbose with debug
enum4linux-ng -A -v 10.10.10.5

# Only specific checks
enum4linux-ng -U -S -G 10.10.10.5   # Users, shares, groups only
```

---

### 7.4 What to Look For

**Users (-U):** Look for usernames to use in password attacks. Note admin accounts.
```
[+] Enumerating users using SID S-1-5-21-...
  [*] Found user 'Administrator' (RID 500)
  [*] Found user 'Guest' (RID 501)
  [*] Found user 'john.smith' (RID 1001)
```

**Shares (-S):** Identify accessible shares, especially with READ or WRITE access.
```
[+] Enumerating shares
  [*] Share: IPC$    | Access: READ
  [*] Share: C$      | Access: NO ACCESS
  [*] Share: NETLOGON | Access: READ
  [*] Share: data    | Access: READ, WRITE   <-- HIGH VALUE
```

**Password Policy (-P):** Determine safe brute-force parameters.
```
[+] Retieved partial password policy
  Minimum password length: 8
  Password complexity: Enabled
  Lockout threshold: 5 attempts
  Lockout duration: 30 minutes
```

**Groups (-G):** Domain Admins, local admin group membership.

---

### 7.5 Real-World Usage Examples

```bash
# 1. Quick null session check and full dump
enum4linux -a 10.10.10.5 2>&1 | tee /tmp/enum_10.10.10.5.txt

# 2. RID brute force with wide range
enum4linux -r -R 500-2000 10.10.10.5

# 3. Authenticated full enum after getting creds
enum4linux -a -u 'john.smith' -p 'Summer2024!' -w CORP 10.10.10.5

# 4. enum4linux-ng with JSON for later parsing
enum4linux-ng -A -oJ /tmp/smb_results.json 192.168.1.10
python3 -c "import json; d=json.load(open('/tmp/smb_results.json')); [print(u) for u in d.get('users',{}).keys()]"

# 5. Share brute force
enum4linux -s /usr/share/wordlists/seclists/Discovery/smb-shares.txt 10.10.10.5
```

---

## 8. LDAP Enumeration

LDAP (Lightweight Directory Access Protocol) is used by Active Directory for directory lookups. Exposed or misconfigured LDAP can reveal the entire organizational directory.

---

### 8.1 ldapsearch

Command-line LDAP client.

**Syntax:**
```
ldapsearch -x -H ldap://<host> -b <base_dn> [filter] [attributes]
```

**Key Flags:**

| Flag | Description |
|------|-------------|
| `-x` | Simple authentication (no SASL) |
| `-H` | LDAP URI (ldap:// or ldaps://) |
| `-b` | Search base DN (e.g., `DC=corp,DC=com`) |
| `-D` | Bind DN (username) |
| `-w` | Bind password |
| `-W` | Prompt for password |
| `-s` | Scope: base, one, sub (default: sub) |
| `-L` | LDIF format (use -LLL to suppress comments) |
| `-o ldif-wrap=no` | Disable line wrapping in LDIF output |
| `(objectClass=*)` | Standard "return everything" filter |
| `-Z` | Start TLS |

**Common queries:**
```bash
# Anonymous bind, enumerate base
ldapsearch -x -H ldap://10.10.10.5 -b "" -s base "(objectClass=*)" namingContexts

# Enumerate all domain objects (anonymous)
ldapsearch -x -H ldap://10.10.10.5 -b "DC=corp,DC=com"

# Enumerate all users
ldapsearch -x -H ldap://10.10.10.5 -b "DC=corp,DC=com" "(objectClass=user)" cn sAMAccountName mail

# Enumerate all computers
ldapsearch -x -H ldap://10.10.10.5 -b "DC=corp,DC=com" "(objectClass=computer)" cn dNSHostName

# Find all domain admins
ldapsearch -x -H ldap://10.10.10.5 -b "DC=corp,DC=com" "(memberOf=CN=Domain Admins,CN=Users,DC=corp,DC=com)" sAMAccountName

# Authenticated enumeration
ldapsearch -x -H ldap://10.10.10.5 -b "DC=corp,DC=com" -D "CN=john.smith,CN=Users,DC=corp,DC=com" -w 'Password123' "(objectClass=user)"

# Find accounts with no Kerberos pre-auth (AS-REP Roasting candidates)
ldapsearch -x -H ldap://10.10.10.5 -b "DC=corp,DC=com" -D "user@corp.com" -w 'pass' "(userAccountControl:1.2.840.113556.1.4.803:=4194304)" sAMAccountName

# Find accounts with SPN set (Kerberoasting candidates)
ldapsearch -x -H ldap://10.10.10.5 -b "DC=corp,DC=com" -D "user@corp.com" -w 'pass' "(&(objectClass=user)(servicePrincipalName=*))" sAMAccountName servicePrincipalName
```

---

### 8.2 ldapdomaindump

Python tool that dumps all LDAP data and generates HTML/JSON/grep-able reports.

**Installation:**
```bash
pip3 install ldapdomaindump
```

**Usage:**
```bash
# Dump entire domain
ldapdomaindump -u 'CORP\john.smith' -p 'Password123' ldap://10.10.10.5

# With LDAPS
ldapdomaindump -u 'CORP\john.smith' -p 'Password123' ldaps://10.10.10.5

# Output to specific directory
ldapdomaindump -u 'CORP\john.smith' -p 'Password123' 10.10.10.5 -o /tmp/ldapdump/
```

**Output files:**
- `domain_computers.html` — All computers in domain
- `domain_groups.html` — All groups with membership
- `domain_policy.html` — Domain password/lockout policy
- `domain_trusts.html` — Domain trust relationships
- `domain_users.html` — All users with attributes
- `domain_users_by_group.html` — Users organized by group
- `*.json` — Machine-readable versions of above
- `*.grep` — grep-friendly text versions

---

### 8.3 windapsearch

Python tool specifically designed for AD enumeration via LDAP.

**Installation:**
```bash
pip3 install windapsearch
# OR
git clone https://github.com/ropnop/windapsearch
```

**Usage:**
```bash
# Enumerate domain users
python3 windapsearch.py -d corp.com -u john.smith -p Password123 --users

# Enumerate domain admins
python3 windapsearch.py -d corp.com -u john.smith -p Password123 --da

# Enumerate privileged users
python3 windapsearch.py -d corp.com -u john.smith -p Password123 --privileged-users

# Enumerate groups
python3 windapsearch.py -d corp.com -u john.smith -p Password123 --groups

# Enumerate computers
python3 windapsearch.py -d corp.com -u john.smith -p Password123 --computers

# Find unconstrained delegation systems (high-value targets)
python3 windapsearch.py -d corp.com -u john.smith -p Password123 --unconstrained-users

# Full enum with all modules
python3 windapsearch.py -d corp.com -u john.smith -p Password123 --full

# JSON output
python3 windapsearch.py -d corp.com -u john.smith -p Password123 --users --json
```

---

### 8.4 Real-World Usage Examples

```bash
# 1. Check for anonymous LDAP access (common AD misconfiguration)
ldapsearch -x -H ldap://10.10.10.5 -b "DC=corp,DC=com" "(objectClass=*)" | head -50

# 2. Full domain dump with ldapdomaindump for reporting
ldapdomaindump -u 'CORP\svc_account' -p 'ServicePass1' ldap://10.10.10.5 -o /tmp/domain_dump/
firefox /tmp/domain_dump/domain_users.html

# 3. Extract all user emails for phishing list
ldapsearch -x -H ldap://10.10.10.5 -b "DC=corp,DC=com" -D "john.smith@corp.com" -w 'Pass' "(objectClass=user)" mail | grep "^mail:" | awk '{print $2}' > emails.txt

# 4. Find Kerberoastable accounts
ldapsearch -x -H ldap://10.10.10.5 -b "DC=corp,DC=com" -D "user@corp.com" -w 'pass' "(&(objectClass=user)(servicePrincipalName=*)(!(cn=krbtgt)))" sAMAccountName servicePrincipalName description

# 5. Identify privileged group membership
ldapsearch -x -H ldap://10.10.10.5 -b "DC=corp,DC=com" -D "user@corp.com" -w 'pass' "(memberOf=CN=Domain Admins,CN=Users,DC=corp,DC=com)" sAMAccountName description
```

---

## 9. DNS Recon

DNS is often the most information-rich attack surface in an engagement. Subdomain enumeration, zone transfers, and reverse lookups can reveal the entire infrastructure.

---

### 9.1 dnsenum

Perl script for DNS enumeration — zone transfers, brute forcing, reverse lookups, Google scraping.

**Installation:** `sudo apt install dnsenum`

```bash
# Full enumeration
dnsenum targetcorp.com

# With brute force (built-in wordlist)
dnsenum --enum targetcorp.com

# Custom wordlist
dnsenum --dnsserver 8.8.8.8 -f /usr/share/wordlists/seclists/Discovery/DNS/subdomains-top1million-5000.txt targetcorp.com

# Reverse lookup on discovered IPs
dnsenum --noreverse targetcorp.com   # Disable reverse lookups (faster)

# Save output
dnsenum targetcorp.com -o /tmp/dnsenum_results.xml
```

---

### 9.2 dnsrecon

Python-based DNS reconnaissance with multiple scan modes. More reliable than dnsenum for modern use.

**Installation:** Pre-installed. `sudo apt install dnsrecon`

**Syntax:** `dnsrecon -d <domain> -t <type> [options]`

| Flag | Description |
|------|-------------|
| `-d` | Target domain |
| `-t` | Scan type (see below) |
| `-n` | DNS server to use |
| `-r` | Reverse lookup range (CIDR or start-stop) |
| `-w` | Bruteforce wordlist |
| `-D` | Subdomain dictionary file |
| `-f` | Output file (JSON/CSV/XML/SQLite) |
| `-c` | CSV output |
| `-j` | JSON output |
| `-x` | XML output |
| `-v` | Verbose |

**Scan types (-t):**

| Type | Description |
|------|-------------|
| `std` | Standard NS/SOA/MX/A/AAAA/SPF enumeration |
| `axfr` | Zone transfer attempt |
| `brute` | Subdomain brute force using wordlist |
| `brt` | Same as brute |
| `rvl` | Reverse lookup of IP range |
| `srv` | SRV record enumeration |
| `tld` | TLD expansion (.com → .net, .org, etc.) |
| `snoop` | DNS cache snooping |
| `zonewalk` | DNSSEC zone walking (NSEC records) |
| `goo` | Google scraping for subdomains |
| `bing` | Bing scraping for subdomains |
| `crt` | Certificate transparency logs |
| `noip` | IP addresses not reverse-resolving |

**Usage Examples:**

```bash
# Standard full enumeration
dnsrecon -d targetcorp.com -t std

# Zone transfer attempt
dnsrecon -d targetcorp.com -t axfr

# Subdomain brute force with large wordlist
dnsrecon -d targetcorp.com -t brute -D /usr/share/wordlists/seclists/Discovery/DNS/subdomains-top1million-20000.txt

# Reverse lookup on discovered range
dnsrecon -r 203.0.113.0-203.0.113.255 -t rvl

# SRV record discovery (reveals services)
dnsrecon -d targetcorp.com -t srv

# Certificate transparency scan
dnsrecon -d targetcorp.com -t crt

# JSON output for processing
dnsrecon -d targetcorp.com -t std -j /tmp/dnsrecon_results.json

# Use specific DNS server
dnsrecon -d targetcorp.com -t std -n 8.8.8.8
```

---

### 9.3 fierce

Performs DNS reconnaissance including zone transfers and subdomain discovery, with a focus on finding non-contiguous IP space.

**Installation:** `pip3 install fierce` or `sudo apt install fierce`

```bash
# Basic scan
fierce --domain targetcorp.com

# Custom wordlist
fierce --domain targetcorp.com --subdomain-file /usr/share/wordlists/seclists/Discovery/DNS/fierce-hostlist.txt

# Use specific DNS server
fierce --domain targetcorp.com --dns-servers 8.8.8.8

# Delay between queries (stealth)
fierce --domain targetcorp.com --delay 3

# Traverse discovered networks
fierce --domain targetcorp.com --traverse 10    # Check ±10 IPs around each discovered IP
```

---

### 9.4 subfinder

Fast passive subdomain discovery using multiple OSINT sources. No brute forcing — purely passive.

**Installation:**
```bash
go install -v github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
# OR
sudo apt install subfinder
```

**Usage:**
```bash
# Basic subdomain discovery
subfinder -d targetcorp.com

# Multiple domains
subfinder -dL domains.txt

# Show only resolved subdomains
subfinder -d targetcorp.com -resolve

# Output to file
subfinder -d targetcorp.com -o /tmp/subdomains.txt

# All sources (slower)
subfinder -d targetcorp.com -all

# JSON output
subfinder -d targetcorp.com -json -o subdomains.json

# Verbose (shows which source found each subdomain)
subfinder -d targetcorp.com -v

# Recursive discovery
subfinder -d targetcorp.com -recursive
```

**Source configuration** (API keys): Edit `~/.config/subfinder/provider-config.yaml` to add keys for Shodan, Censys, SecurityTrails, etc.

---

### 9.5 amass

The most comprehensive subdomain enumeration tool. Supports passive OSINT, active brute forcing, and certificate transparency.

**Installation:** `sudo apt install amass` or `go install -v github.com/owasp-amass/amass/v4/...@master`

**Two primary modes:**

#### amass intel — Passive OSINT
```bash
# Discover ASNs and netblocks for an organization
amass intel -org "Target Corporation"

# Discover domains from an ASN
amass intel -asn 15169

# Discover domains from a CIDR
amass intel -cidr 203.0.113.0/24

# Reverse WHOIS
amass intel -d targetcorp.com -whois

# Certificate transparency discovery
amass intel -d targetcorp.com
```

#### amass enum — Active Subdomain Enumeration
```bash
# Passive only (no DNS brute force)
amass enum -passive -d targetcorp.com

# Active (includes brute force with default wordlist)
amass enum -active -d targetcorp.com

# Custom brute force wordlist
amass enum -brute -d targetcorp.com -w /usr/share/wordlists/seclists/Discovery/DNS/subdomains-top1million-20000.txt

# Output to file
amass enum -d targetcorp.com -o /tmp/amass_subdomains.txt

# JSON output
amass enum -d targetcorp.com -json /tmp/amass_results.json

# With config file (API keys)
amass enum -config ~/.config/amass/config.ini -d targetcorp.com

# Multiple domains
amass enum -d targetcorp.com -d subsidiary.com

# Recursive brute force
amass enum -brute -d targetcorp.com -rf /usr/share/wordlists/resolvers.txt -w wordlist.txt

# Visualize results
amass viz -d3 -d targetcorp.com -o viz.html
```

**API key configuration** (`~/.config/amass/config.ini`):
```ini
[data_sources]
[data_sources.Shodan]
[data_sources.Shodan.Credentials]
apikey = YOUR_SHODAN_KEY

[data_sources.SecurityTrails]
[data_sources.SecurityTrails.Credentials]
apikey = YOUR_ST_KEY
```

---

### 9.6 dig — Manual DNS Querying

```bash
# Standard A record lookup
dig targetcorp.com A

# MX records
dig targetcorp.com MX

# NS records
dig targetcorp.com NS

# TXT records (SPF, DKIM, DMARC)
dig targetcorp.com TXT

# SOA record
dig targetcorp.com SOA

# ALL records
dig targetcorp.com ANY

# Zone transfer (AXFR)
dig axfr @ns1.targetcorp.com targetcorp.com

# Trace DNS resolution path
dig +trace targetcorp.com

# Short output only
dig +short targetcorp.com

# Reverse lookup
dig -x 203.0.113.42

# Query specific DNS server
dig @8.8.8.8 targetcorp.com

# DNSSEC lookup
dig +dnssec targetcorp.com
```

---

### 9.7 Real-World DNS Recon Workflow

```bash
# 1. Get nameservers and attempt zone transfer
dig NS targetcorp.com +short
dig axfr @ns1.targetcorp.com targetcorp.com

# 2. Passive subdomain enumeration
subfinder -d targetcorp.com -o /tmp/subs_passive.txt
cat /tmp/subs_passive.txt | sort -u > /tmp/all_subs.txt

# 3. Active brute force
dnsrecon -d targetcorp.com -t brute -D /usr/share/wordlists/seclists/Discovery/DNS/subdomains-top1million-5000.txt -j /tmp/dnsrecon_brute.json

# 4. Certificate transparency
amass enum -passive -d targetcorp.com -o /tmp/amass_subs.txt

# 5. Consolidate and resolve
cat /tmp/subs_passive.txt /tmp/amass_subs.txt | sort -u | dnsx -a -resp-only > /tmp/resolved_ips.txt
```

---

## 10. OSINT Tools

---

### 10.1 whois

Queries domain registration and IP ownership records.

```bash
# Domain registration
whois targetcorp.com

# IP ownership/ASN
whois 203.0.113.42

# Query specific WHOIS server
whois -h whois.arin.net 203.0.113.42

# Suppress legal boilerplate
whois targetcorp.com | grep -v "^#" | grep -v "^%"
```

**Look for:** Registrant name, email, phone, registrar, nameservers, creation/expiry dates, abuse contact.

---

### 10.2 spiderfoot

Automated OSINT collection framework with 200+ modules. Can correlate data across dozens of sources.

**Installation:**
```bash
sudo apt install spiderfoot
# OR
git clone https://github.com/smicallef/spiderfoot && cd spiderfoot && pip3 install -r requirements.txt
```

**Web interface:**
```bash
python3 ./sf.py -l 127.0.0.1:5001
# Navigate to http://127.0.0.1:5001
```

**CLI usage:**
```bash
# List all modules
python3 ./sf.py -M

# Scan by domain (passive)
python3 ./sf.py -s targetcorp.com -t INTERNET_NAME -m sfp_dnsresolve,sfp_ssl,sfp_whois

# Scan an IP
python3 ./sf.py -s 203.0.113.42 -t IP_ADDRESS -m sfp_shodan,sfp_whois,sfp_portscan_basic

# Full passive recon on domain
python3 ./sf.py -s targetcorp.com -t DOMAIN_NAME -q   # quiet mode
```

**Module categories:**
- `sfp_shodan` — Shodan lookups
- `sfp_dns*` — DNS modules
- `sfp_whois` — WHOIS records
- `sfp_ssl` — SSL certificate analysis
- `sfp_linkedin` — LinkedIn enumeration
- `sfp_github` — GitHub code search
- `sfp_pastebin` — Pastebin data leaks
- `sfp_hunter` — Email enumeration

---

### 10.3 sherlock

Searches 400+ social media platforms for a given username.

**Installation:**
```bash
sudo apt install sherlock
# OR
pip3 install sherlock-project
```

**Usage:**
```bash
# Search for a username
sherlock johndoe

# Multiple usernames
sherlock johndoe john_doe j.doe

# Output to file
sherlock johndoe --output results.txt

# CSV output
sherlock johndoe --csv

# Timeout per site
sherlock johndoe --timeout 10

# Tor routing
sherlock johndoe --tor

# Only show found results (suppress not-found)
sherlock johndoe --print-found
```

---

### 10.4 whatweb

Web scanner that identifies technologies, CMS, frameworks, and other web fingerprints.

**Installation:** Pre-installed on Kali.

**Usage:**
```bash
# Basic scan
whatweb https://targetcorp.com

# Aggressive mode (more requests, better coverage)
whatweb -a 3 https://targetcorp.com

# Scan a list of URLs
whatweb -i urls.txt

# Output formats
whatweb https://targetcorp.com --log-verbose=output.txt
whatweb https://targetcorp.com --log-json=output.json
whatweb https://targetcorp.com --log-xml=output.xml

# Follow redirects
whatweb --follow-redirect=always https://targetcorp.com

# Custom user agent
whatweb -U "Mozilla/5.0" https://targetcorp.com

# Scan entire CIDR
whatweb -a 1 192.168.1.0/24
```

**Output example:**
```
https://targetcorp.com [200 OK] Apache[2.4.51], Bootstrap[4.6], Cookies[PHPSESSID], 
Country[UNITED STATES][US], Email[admin@targetcorp.com], HTML5, 
HTTPServer[Debian Linux][Apache/2.4.51 (Debian)], IP[203.0.113.42], 
JQuery[3.6.0], PHP[7.4.28], WordPress[5.9.2], X-Powered-By[PHP/7.4.28]
```

**Aggression levels:**
- 1 (Stealthy): Single request per URL
- 3 (Aggressive): Multiple requests, follows links
- 4 (Heavy): Many requests, stress test level

---

### 10.5 wafw00f

Identifies Web Application Firewalls (WAFs) in front of web applications.

**Installation:** `sudo apt install wafw00f` or `pip3 install wafw00f`

```bash
# Detect WAF
wafw00f https://targetcorp.com

# Verbose output
wafw00f -v https://targetcorp.com

# Try all WAF fingerprints
wafw00f -a https://targetcorp.com

# Scan multiple targets
wafw00f -i targets.txt

# JSON output
wafw00f -o results.json https://targetcorp.com

# Format output
wafw00f -f json https://targetcorp.com
```

**Detects 180+ WAFs including:** Cloudflare, AWS WAF, Akamai, F5 BIG-IP ASM, Imperva SecureSphere, Barracuda, Sucuri, ModSecurity, Palo Alto, Fortinet, and many more.

**Use WAF detection to:**
- Adjust scanning strategy (slow down, use evasion)
- Determine if bypass techniques are needed
- Inform report on defense posture

---

### 10.6 wapiti

Web application vulnerability scanner with an OSINT-capable crawler mode.

**Installation:** `sudo apt install wapiti` or `pip3 install wapiti3`

```bash
# Basic scan
wapiti -u https://targetcorp.com

# Specify attack modules
wapiti -u https://targetcorp.com -m sql,xss,file,exec,redirect

# Passive crawl only (no attacks)
wapiti -u https://targetcorp.com --list-modules
wapiti -u https://targetcorp.com -m ""   # No attack modules, crawl only

# Output report
wapiti -u https://targetcorp.com -o /tmp/wapiti_report -f html

# Set max crawl depth
wapiti -u https://targetcorp.com --max-depth 5

# Follow links to other domains
wapiti -u https://targetcorp.com --external-domains

# Custom cookies for authenticated scanning
wapiti -u https://targetcorp.com --cookie "session=ABCD1234; auth=true"
```

---

### 10.7 Real-World OSINT Workflow

```bash
# 1. Initial passive fingerprinting
whois targetcorp.com > /tmp/osint/whois.txt
whatweb -a 3 https://targetcorp.com --log-json=/tmp/osint/whatweb.json
wafw00f -a https://targetcorp.com

# 2. Technology stack and exposure mapping
# (theHarvester + subfinder covered in sections 3 and 9)

# 3. Username OSINT
sherlock "john.smith" --csv --output /tmp/osint/sherlock_john.csv

# 4. SpiderFoot automated correlation
python3 /opt/spiderfoot/sf.py -s targetcorp.com -t DOMAIN_NAME -o /tmp/osint/sf_results.json
```

---

## 11. Network Discovery

---

### 11.1 netdiscover

ARP-based host discovery for local networks. Passively listens for ARP traffic or actively sends ARP requests.

**Installation:** `sudo apt install netdiscover`

```bash
# Active scan of subnet
sudo netdiscover -r 192.168.1.0/24

# Specific interface
sudo netdiscover -i eth0 -r 10.10.10.0/24

# Passive mode (just listen for ARP)
sudo netdiscover -p

# Fast scan (lower wait time)
sudo netdiscover -r 192.168.1.0/24 -f

# Manual ARP request to specific IP
sudo netdiscover -r 192.168.1.1/32

# Output to file
sudo netdiscover -r 192.168.1.0/24 -o /tmp/hosts.txt

# Use custom MAC list for vendor detection
sudo netdiscover -l /usr/share/netdiscover/ieee-oui.txt -r 192.168.1.0/24
```

**Output:**
```
  IP            At MAC Address     Count     Len  MAC Vendor / Hostname
 192.168.1.1   aa:bb:cc:11:22:33     1      60   Cisco Systems
 192.168.1.10  dd:ee:ff:44:55:66     1      60   Dell Inc.
 192.168.1.20  11:22:33:aa:bb:cc     1      60   Apple Inc.
```

---

### 11.2 arp-scan

Sends ARP packets and displays responses. Faster and more reliable than ping for local segment discovery.

**Installation:** `sudo apt install arp-scan`

```bash
# Scan local network (auto-detects interface and range)
sudo arp-scan --localnet

# Specify interface
sudo arp-scan -I eth0 --localnet

# Specific range
sudo arp-scan 192.168.1.0/24

# Scan specific hosts
sudo arp-scan 192.168.1.1 192.168.1.10 192.168.1.100

# From file
sudo arp-scan --file=targets.txt

# Include duplicate responses (detects spoofing)
sudo arp-scan --localnet --ignoredups=false

# Retry for better accuracy (default: 2)
sudo arp-scan --localnet --retry=5

# Custom source MAC
sudo arp-scan --localnet --srcaddr=00:11:22:33:44:55

# Output to file
sudo arp-scan --localnet | tee /tmp/arp_hosts.txt
```

**Why prefer arp-scan over ping for LAN discovery:**
- Works even if ICMP is firewalled
- Layer 2 — cannot be blocked by host-based firewalls
- Returns vendor information (OUI lookup)
- Much faster than nmap ping scan on local segments

---

### 11.3 masscan

The fastest Internet-scale TCP port scanner. Can scan the entire IPv4 internet in under 6 minutes at 10Gbps. Sends raw packets using its own TCP/IP stack.

**Installation:** `sudo apt install masscan`

**Basic syntax:**
```
masscan [targets] -p [ports] [options]
```

**Key Flags:**

| Flag | Description |
|------|-------------|
| `-p` | Port(s) to scan (same syntax as nmap) |
| `--rate` | Packets per second (default: 100) |
| `--banners` | Grab service banners (requires --source-port) |
| `-oL` | Output to list format |
| `-oJ` | Output to JSON |
| `-oX` | Output to XML (nmap-compatible) |
| `-oG` | Output to grepable format |
| `--adapter-ip` | Source IP address |
| `--adapter-port` | Source port range |
| `--router-mac` | Gateway MAC (for interface bypassing) |
| `--exclude` | Exclude specific IPs/ranges |
| `--excludefile` | Exclude IPs from file |
| `--retries` | Retry count (default: 0) |
| `--ttl` | TTL value |
| `--wait` | Wait seconds after scan before exiting (for late responses) |
| `--open` | Only show open ports |
| `-c` | Config file |
| `--resume` | Resume interrupted scan |

**Rate guidance:**
- LAN: `--rate 10000` (10k pps)
- Pentest WAN: `--rate 1000-5000` (balance speed vs. reliability)
- Internet scan: `--rate 100000+` (requires 1Gbps+)
- **Warning:** High rates can crash routers, overwhelm targets, trigger alarms

```bash
# Fast scan of common ports in a /16
sudo masscan 10.10.0.0/16 -p 80,443,22,21,3389,445,8080 --rate 5000

# Full port scan of single host (fast)
sudo masscan 10.10.10.5 -p1-65535 --rate 10000

# Grab banners from web servers
sudo masscan 192.168.1.0/24 -p 80,443 --banners --rate 1000

# Save to JSON, exclude localhost
sudo masscan 10.0.0.0/8 -p 22,80,443,3389 --rate 2000 --exclude 10.0.0.0/32 -oJ /tmp/masscan_results.json

# Resume an interrupted scan
sudo masscan --resume paused.conf

# Scan from config file
sudo masscan -c masscan.conf

# UDP (limited support, mostly for specific cases)
sudo masscan 192.168.1.0/24 -pU:53,161

# Convert masscan XML to nmap format for tool compatibility
masscan -iL targets.txt -p80,443 -oX masscan.xml
xsltproc masscan.xml -o masscan.html
```

**masscan.conf example:**
```
rate = 5000
output-format = json
output-filename = results.json
ports = 22,80,443,8080,8443,445,3389,5985,5986
range = 10.0.0.0/8
excludefile = /etc/masscan/exclude.conf
retries = 1
banners = true
```

---

### 11.4 zmap

Internet-scale scanning tool from the University of Michigan. Designed for single-port large-scale scans. Can scan all 3.7 billion IPv4 addresses in under 45 minutes at 1Gbps.

**Installation:** `sudo apt install zmap`

```bash
# Scan entire internet for port 80 (use ONLY on authorized ranges)
sudo zmap -p 80 -o results.txt

# Scan specific range
sudo zmap -p 443 -o https_hosts.txt 192.168.0.0/16

# Set bandwidth limit (not rate)
sudo zmap -p 22 -B 10M -o ssh_hosts.txt 10.0.0.0/8

# Use ZGrab for banner grabbing (companion tool)
sudo zmap -p 80 192.168.1.0/24 | zgrab --port 80 --http "/" > http_results.json

# Multiple target ranges
sudo zmap -p 443 -w targets.txt

# Randomize scan order (default behavior)
sudo zmap -p 80 --seed 12345 10.0.0.0/8    # Reproducible random order

# Custom source port
sudo zmap -p 80 --source-port 40000-50000 10.0.0.0/24

# Output format
sudo zmap -p 80 -o results.csv --output-fields saddr,daddr,sport,dport,seqnum,timestamp 10.0.0.0/24

# Rate per second
sudo zmap -p 80 -r 100000 10.0.0.0/8
```

**zmap vs masscan:**
- zmap: Designed for single-port internet-scale research
- masscan: Multi-port, more flexible, nmap-like interface
- Both use raw packets and their own network stacks
- masscan is generally preferred for penetration testing engagements

---

### 11.5 Real-World Network Discovery Workflows

```bash
# 1. LAN host discovery — reliable, fast
sudo arp-scan -I eth0 --localnet | grep -v "DUP" | awk '/^[0-9]/{print $1}' > /tmp/live_hosts.txt

# 2. Combined discovery — ARP + ICMP + TCP
sudo nmap -sn 192.168.1.0/24 --send-eth -oG /tmp/ping_sweep.gnmap
grep "Up" /tmp/ping_sweep.gnmap | awk '{print $2}' >> /tmp/live_hosts.txt

# 3. Rapid open port identification across a /16
sudo masscan 10.10.0.0/16 -p21,22,23,25,53,80,110,143,443,445,993,995,1433,1521,3306,3389,5432,5900,6379,8080,8443,27017 --rate 3000 -oL /tmp/masscan_open_ports.txt

# 4. Follow-up nmap on masscan findings
awk '/^open/{print $4}' /tmp/masscan_open_ports.txt | sort -u > /tmp/open_hosts.txt
sudo nmap -sV -sC -T4 -iL /tmp/open_hosts.txt --open -oA /tmp/nmap_followup

# 5. Internal network discovery from compromised host (minimal footprint)
sudo netdiscover -r 10.10.10.0/24 -f -P | tee /tmp/netdiscover_results.txt
```

---

## Appendix: Recommended Tool Combinations

### External Reconnaissance Workflow
```
1. Passive OSINT:
   whois → theHarvester (-b all) → subfinder → amass intel → crt.sh
   
2. DNS Enumeration:
   dnsrecon -t std,axfr,srv → amass enum --passive → fierce --traverse
   
3. Web Fingerprinting:
   whatweb → wafw00f → shodan (ssl.cert + hostname filters)
   
4. Exposure Mapping:
   Shodan (org: + net: filters) → Censys → recon-ng (certificate_transparency module)
```

### Internal Network Penetration Test Workflow
```
1. Host Discovery:
   arp-scan → netdiscover → nmap -sn
   
2. Port Discovery:
   masscan (all ports, high rate) → nmap (targeted follow-up with -sV -sC)
   
3. Service Enumeration:
   enum4linux-ng (SMB targets) → ldapdomaindump (AD targets) → nmap NSE scripts
   
4. Vulnerability Assessment:
   nmap --script vuln → Nessus/OpenVAS credentialed scan
```

### Stealth/Evasion Workflow
```
1. Initial: -T1, -f, --data-length 25, --source-port 53
2. Decoys: -D RND:10 (confirm IPs are reachable first)
3. MAC spoof on same L2: --spoof-mac 0
4. Source port: -g 443 (HTTPS-looking traffic)
5. Timing: --scan-delay 500ms between probes
6. Rate: masscan --rate 100 for slow, stealthy WAN scans
```

---

## Appendix: Wordlists Reference

| Path | Description |
|------|-------------|
| `/usr/share/wordlists/rockyou.txt.gz` | 14M passwords (gunzip first) |
| `/usr/share/wordlists/seclists/` | SecLists collection (install: apt install seclists) |
| `/usr/share/wordlists/seclists/Discovery/DNS/subdomains-top1million-20000.txt` | DNS brute force |
| `/usr/share/wordlists/seclists/Discovery/Web-Content/raft-large-directories.txt` | Web directory brute |
| `/usr/share/wordlists/seclists/Usernames/top-usernames-shortlist.txt` | Username list |
| `/usr/share/nmap/scripts/` | All NSE scripts |
| `/usr/share/nmap/nmap-services` | Port frequency database |

---

## Appendix: Quick Reference — Common Scan Commands

```bash
# Live host sweep
sudo nmap -sn 192.168.1.0/24

# Fast top-1000 port scan
sudo nmap -sS -T4 --top-ports 1000 --open 10.10.10.5

# Full version + script scan
sudo nmap -sS -sV -sC -p- -T4 --open -oA full_scan 10.10.10.5

# Aggressive all-in-one
sudo nmap -A -T4 -p- 10.10.10.5

# Vulnerability check
sudo nmap -sV --script=vuln 10.10.10.5

# SMB checks
sudo nmap -p 445 --script="smb-vuln-*,smb-enum-*" 10.10.10.5

# DNS zone transfer
dig axfr @ns1.target.com target.com

# Passive subdomain enum
subfinder -d target.com | tee subs.txt

# SMB null session
enum4linux-ng -A 10.10.10.5

# LDAP anonymous dump
ldapsearch -x -H ldap://10.10.10.5 -b "DC=corp,DC=com"

# Network segment discovery
sudo arp-scan --localnet
sudo masscan 10.10.10.0/24 -p22,80,443,445,3389 --rate 1000
```

---

*All techniques in this document are for use in authorized penetration testing engagements, CTF competitions, and security research in environments where explicit written permission has been obtained. Unauthorized use against systems you do not own or have written permission to test is illegal under the Computer Fraud and Abuse Act (CFAA), the UK Computer Misuse Act, and equivalent laws in most jurisdictions.*
