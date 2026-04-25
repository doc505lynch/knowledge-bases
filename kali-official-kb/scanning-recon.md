# Scanning & Reconnaissance Tools

## nmap
**Category:** Scanning/Recon
**Description:** Network exploration tool and security/port scanner; the gold standard for host and service discovery.
**Common Usage:** `nmap [scan type] [options] {target}`
**Key Flags:**
- `-sS` — TCP SYN (stealth) scan
- `-sV` — Service/version detection
- `-sC` — Run default NSE scripts
- `-O` — OS detection
- `-p <ports>` — Specify port range (e.g., `-p 1-65535`, `-p 80,443`)
- `-Pn` — Skip host discovery (treat all hosts as online)
- `-A` — Aggressive scan (OS detect, version, scripts, traceroute)
- `-T<0-5>` — Timing template (0=paranoid, 5=insane)
- `-iL <file>` — Input targets from file
- `--script=<name>` — Run specific NSE script
- `-oN/-oX/-oG <file>` — Output in normal/XML/grepable format
**Help Output:**
```
Nmap 7.98 ( https://nmap.org )
Usage: nmap [Scan Type(s)] [Options] {target specification}
TARGET SPECIFICATION:
  Can pass hostnames, IP addresses, networks, etc.
  Ex: scanme.nmap.org, microsoft.com/24, 192.168.0.1; 10.0.0-255.1-254
  -iL <inputfilename>: Input from list of hosts/networks
  -iR <num hosts>: Choose random targets
  --exclude <host1[,host2][,host3],...>: Exclude hosts/networks
HOST DISCOVERY:
  -sL: List Scan - simply list targets to scan
  -sn: Ping Scan - disable port scan
  -Pn: Treat all hosts as online -- skip host discovery
  -PS/PA/PU/PY[portlist]: TCP SYN, TCP ACK, UDP or SCTP discovery to given ports
  -PE/PP/PM: ICMP echo, timestamp, and netmask request discovery probes
SCAN TECHNIQUES:
  -sS/sT/sA/sW/sM: TCP SYN/Connect()/ACK/Window/Maimon scans
  -sU: UDP Scan
  -sN/sF/sX: TCP Null, FIN, and Xmas scans
  -sI <zombie host[:probeport]>: Idle scan
PORT SPECIFICATION:
  -p <port ranges>: Only scan specified ports
  -F: Fast mode - Scan fewer ports than the default scan
  --top-ports <number>: Scan <number> most common ports
SERVICE/VERSION DETECTION:
  -sV: Probe open ports to determine service/version info
  --version-intensity <level>: Set from 0 (light) to 9 (try all probes)
SCRIPT SCAN:
  -sC: equivalent to --script=default
  --script=<Lua scripts>: comma separated list of directories, script-files or script-categories
OS DETECTION:
  -O: Enable OS detection
OUTPUT:
  -oN/-oX/-oS/-oG <file>: Output scan in normal, XML, s|<rIpt kIddi3, and Grepable format
  -v: Increase verbosity level
MISC:
  -A: Enable OS detection, version detection, script scanning, and traceroute
  -T<0-5>: Set timing template (higher is faster)
```
---

## masscan
**Category:** Scanning/Recon
**Description:** Extremely fast TCP port scanner; can scan the entire internet in under 6 minutes. Sends packets asynchronously.
**Common Usage:** `masscan <target> -p<ports> --rate=<pps>`
**Key Flags:**
- `-p <ports>` — Ports to scan (e.g., `-p80,443`, `-p1-65535`)
- `--rate=<n>` — Packets per second (default: 100)
- `--banner` — Attempt to grab banners
- `-oX/-oL/-oJ <file>` — Output in XML, list, or JSON format
- `--adapter-ip` — Source IP address
- `-c <file>` — Load config from file
- `--echo` — Print current config (useful for generating config files)
**Help Output:**
```
MASSCAN is a fast port scanner. The primary input parameters are the
IP addresses/ranges you want to scan, and the port numbers. An example
is the following, which scans the 10.x.x.x network for web servers:
 masscan 10.0.0.0/8 -p80
The program auto-detects network interface/adapter settings. If this
fails, you'll have to set these manually. The following is an example:
 --adapter-ip 192.168.10.123
 --adapter-mac 00-11-22-33-44-55
 --router-mac 66-55-44-33-22-11
Parameters can be set either via the command-line or config-file.
To use the config file, type:
 masscan -c <filename>
To generate a config-file from the current settings, use the --echo option.
```
---

## nikto
**Category:** Scanning/Recon
**Description:** Web server scanner that performs comprehensive tests against web servers for dangerous files, outdated software, and misconfigurations.
**Common Usage:** `nikto -h <target> [options]`
**Key Flags:**
- `-h <host>` — Target host/URL
- `-p <port>` — Target port (default 80)
- `-ssl` — Force SSL
- `-o <file>` — Output file
- `-Format <fmt>` — Output format: csv, json, htm, txt, xml
- `-Tuning <x>` — Test tuning (0-9, a-c)
- `-evasion <x>` — Evasion technique (1-8, A, B)
- `-useproxy` — Use proxy defined in nikto.conf
- `-id <user:pass>` — HTTP authentication
**Help Output:**
```
Options:
    -ask+               Whether to ask about submitting updates
    -Cgidirs+           Scan these CGI dirs: "none", "all", or values like "/cgi/ /cgi-a/"
    -config+            Use this config file
    -Display+           Turn on/off display outputs:
                            1  Show redirects
                            2  Show cookies received
                            3  Show all 200/OK responses
                            V  Verbose output
    -evasion+           Encoding technique:
                            1  Random URI encoding (non-UTF8)
                            2  Directory self-reference (/./)
                            3  Premature URL ending
                            7  Change the case of the URL
    -Format+            Save file (-o) format: csv, json, htm, nbe, sql, txt, xml
    -host+              Target host/URL
    -id+                Host authentication to use, format is id:pass or id:pass:realm
    -list-plugins       List all available plugins, perform no testing
    -maxtime+           Maximum testing time per host (e.g., 1h, 60m, 3600s)
```
---

## gobuster
**Category:** Scanning/Recon
**Description:** Directory/file, DNS, and vhost brute-force tool written in Go. Faster than dirb/dirbuster.
**Common Usage:** `gobuster dir -u <url> -w <wordlist>` | `gobuster dns -d <domain> -w <wordlist>`
**Key Flags:**
- `dir` — Directory/file enumeration mode
- `dns` — DNS subdomain enumeration mode
- `vhost` — Virtual host enumeration mode
- `fuzz` — Fuzzing mode (FUZZ keyword in URL/headers/body)
- `-u <url>` — Target URL
- `-w <wordlist>` — Wordlist file
- `-x <exts>` — File extensions to search (e.g., `-x php,html`)
- `-t <n>` — Number of threads (default 10)
- `-o <file>` — Output file
- `-k` — Skip TLS verification
- `-b <codes>` — Blacklist status codes
**Help Output:**
```
NAME:
   gobuster - the tool you love

USAGE:
   gobuster command [command options]

VERSION:
   3.8.2

COMMANDS:
   dir      Uses directory/file enumeration mode
   vhost    Uses VHOST enumeration mode
   dns      Uses DNS subdomain enumeration mode
   fuzz     Uses fuzzing mode. Replaces the keyword FUZZ in the URL, Headers and the request body
   tftp     Uses TFTP enumeration mode
   s3       Uses aws bucket enumeration mode
   gcs      Uses gcs bucket enumeration mode

GLOBAL OPTIONS:
   --help, -h     show help
   --version, -v  print the version
```
---

## dirb
**Category:** Scanning/Recon
**Description:** Web content scanner that brute-forces directories and files on web servers using a wordlist.
**Common Usage:** `dirb <url> [wordlist] [options]`
**Key Flags:**
- `-a <agent>` — Custom User-Agent string
- `-c <cookie>` — Set cookie for HTTP requests
- `-H <header>` — Add custom HTTP header
- `-i` — Case-insensitive search
- `-o <file>` — Save output to file
- `-p <proxy[:port]>` — Use proxy
- `-r` — Do not search recursively
- `-X <extensions>` — Append extensions to each word
- `-z <ms>` — Add delay between requests (milliseconds)
- `-u <user:pass>` — HTTP authentication
**Help Output:**
```
dirb <url_base> [<wordlist_file(s)>] [options]

 <url_base>         : Base URL to scan.
 <wordlist_file(s)> : List of wordfiles.

OPTIONS:
 -a <agent_string>  : Specify your custom USER_AGENT.
 -c <cookie_string> : Set a cookie for the HTTP request.
 -f                 : Fine tuning of NOT_FOUND (404) detection.
 -H <header_string> : Add a custom header to the HTTP request.
 -i                 : Use case-insensitive search.
 -N <nf_code>       : Ignore responses with this HTTP code.
 -o <output_file>   : Save output to disk.
 -p <proxy[:port]>  : Use this proxy. (Default port is 1080)
 -r                 : Don't search recursively.
 -X <extensions>    : Append each word with this extensions.
 -z <millisecs>     : Add a milliseconds delay to not cause excessive Flood.
```
---

## wfuzz
**Category:** Scanning/Recon / Web
**Description:** Web application fuzzer that replaces FUZZ keyword in URLs, headers, or POST data with wordlist values.
**Common Usage:** `wfuzz -w <wordlist> -u http://target/FUZZ`
**Key Flags:**
- `-w <wordlist>` — Wordlist file
- `-z <type,value>` — Payload type and value
- `-u <url>` — Target URL (use FUZZ as placeholder)
- `-H <header>` — Custom header
- `-d <data>` — POST data
- `-c` — Colorize output
- `--hc <codes>` — Hide responses with these HTTP codes
- `--hl <lines>` — Hide responses with this many lines
- `--hw <words>` — Hide responses with this many words
- `-t <n>` — Concurrent connections (default: 10)
- `-p <proxy>` — Proxy (ip:port:type)
**Help Output:**
```
Wfuzz 3.1.0 - The Web Fuzzer

Usage: wfuzz [options] -z payload,params <url>

    FUZZ, ..., FUZnZ wherever you put these keywords wfuzz will replace them with the values of the specified payload.

Options:
    -h/--help                 : This help
    -e <type>                 : List of available encoders/payloads/iterators/printers/scripts
    --recipe <filename>       : Reads options from a recipe.
    -c                        : Output with colors
    -v                        : Verbose information.
    -f filename,printer       : Store results in the output file using the specified printer
    -p addr                   : Use Proxy in format ip:port:type (SOCKS4,SOCKS5,HTTP)
    -t N                      : Specify the number of concurrent connections (10 default)
    -s N                      : Specify time delay between requests (0 default)
    -R depth                  : Recursive path discovery
    -L,--follow               : Follow HTTP redirections
    --hc/hl/hw/hh N[,N]+      : Hide responses with the specified code/lines/words/chars
    --sc/sl/sw/sh N[,N]+      : Show responses with the specified code/lines/words/chars
```
---

## dnsrecon
**Category:** Scanning/Recon
**Description:** DNS enumeration tool that performs zone transfers, brute-force subdomain lookups, reverse lookups, and various DNS record queries.
**Common Usage:** `dnsrecon -d <domain> -t <type>`
**Key Flags:**
- `-d <domain>` — Target domain
- `-t <type>` — Enumeration type: std, rvl, brt, srv, axfr, bing, yandex, crt
- `-D <dict>` — Dictionary file for brute-force
- `-r <range>` — IP range for reverse lookup
- `-n <nameserver>` — Custom name server
- `-a` — Perform AXFR with standard enumeration
- `--threads <n>` — Number of threads
- `-j <file>` — Save output to JSON
**Help Output:**
```
usage: dnsrecon [-h] [-d DOMAIN] [-n NS_SERVER] [-r RANGE] [-D DICTIONARY]
                [-f] [-a] [-s] [-b] [-y] [-k] [-w] [-z]
                [--threads THREADS] [--lifetime LIFETIME] [--tcp]
                [-x XML] [-c CSV] [-j JSON] [-v] [-t TYPE]

options:
  -d, --domain DOMAIN   Target domain.
  -n, --name_server NS_SERVER  Domain server to use.
  -r, --range RANGE     IP range for reverse lookup brute force.
  -D, --dictionary DICTIONARY  Dictionary file of subdomain and hostnames.
  -f                    Filter out wildcard IPs from brute force results.
  -a                    Perform AXFR with standard enumeration.
  -w                    Perform deep whois record analysis.
  --threads THREADS     Number of threads to use.
  -j, --json JSON       Save output to a JSON file.
  -v, --verbose         Enable verbosity
  -t, --type TYPE       Type of enumeration:
                          std: SOA, NS, A, AAAA, MX and SRV.
                          rvl: Reverse lookup of a given CIDR.
                          brt: Brute force domains and hosts.
                          srv: SRV records.
                          axfr: Zone transfer attempt.
```
---

## fierce
**Category:** Scanning/Recon
**Description:** DNS reconnaissance tool for locating non-contiguous IP space and subdomain discovery.
**Common Usage:** `fierce --domain <domain>`
**Key Flags:**
- `--domain <domain>` — Target domain
- `--subdomain-file <file>` — File with subdomains to try
- `--dns-servers <servers>` — Custom DNS servers
- `--range <cidr>` — Scan an internal IP range
- `--traverse <n>` — Scan IPs near discovered records
- `--wide` — Scan entire class C of discovered records
- `--delay <secs>` — Time to wait between lookups
- `--tcp` — Use TCP instead of UDP
**Help Output:**
```
usage: fierce [-h] [--domain DOMAIN] [--connect] [--wide]
              [--traverse TRAVERSE] [--search SEARCH [SEARCH ...]]
              [--range RANGE] [--delay DELAY]
              [--subdomains SUBDOMAINS [SUBDOMAINS ...] |
              --subdomain-file SUBDOMAIN_FILE]
              [--dns-servers DNS_SERVERS | --dns-file DNS_FILE] [--tcp]

        A DNS reconnaissance tool for locating non-contiguous IP space.

options:
  --domain DOMAIN       domain name to test
  --connect             attempt HTTP connection to non-RFC 1918 hosts
  --wide                scan entire class c of discovered records
  --traverse TRAVERSE   scan IPs near discovered records
  --range RANGE         scan an internal IP range, use cidr notation
  --delay DELAY         time to wait between lookups
  --subdomain-file SUBDOMAIN_FILE  use subdomains specified in this file
  --dns-servers DNS_SERVERS [DNS_SERVERS ...]  use these dns servers
  --tcp                 use TCP instead of UDP
```
---

## whois
**Category:** Scanning/Recon
**Description:** Queries WHOIS databases for domain registration and IP address block information.
**Common Usage:** `whois <domain|ip>`
**Key Flags:**
- `-h <host>` — Connect to specific WHOIS server
- `-p <port>` — Connect to specific port
- `-H` — Hide legal disclaimers
- `-I` — Query whois.iana.org and follow referrals
- `--no-recursion` — Disable recursion from registry to registrar
- `-B` — Show email addresses (turn off object filtering)
**Help Output:**
```
Usage: whois [OPTION]... OBJECT...

-h HOST, --host HOST   connect to server HOST
-p PORT, --port PORT   connect to PORT
-I                     query whois.iana.org and follow its referral
-H                     hide legal disclaimers
      --no-recursion   disable recursion from registry to registrar servers
-l                     find the one level less specific match
-L                     find all levels less specific matches
-x                     exact match
-b                     return brief IP address ranges with abuse contact
-B                     turn off object filtering (show email addresses)
-r                     turn off recursive look-ups for contact information
```
---

## whatweb
**Category:** Scanning/Recon
**Description:** Next-generation web scanner that identifies web technologies including CMS, blogging platforms, analytics packages, JavaScript libraries, and server details.
**Common Usage:** `whatweb [options] <URLs>`
**Key Flags:**
- `-a <level>` — Aggression level 1-4 (1=stealthy, 3=aggressive, 4=heavy)
- `-i <file>` — Read targets from file
- `-U <agent>` — Custom User-Agent
- `-H <header>` — Add HTTP header
- `--proxy <host:port>` — Use proxy
- `-v` — Verbose output
- `-q` — Quiet mode
- `--log-json=<file>` — Log results as JSON
- `--log-xml=<file>` — Log results as XML
**Help Output:**
```
WhatWeb - Next generation web scanner version 0.6.3.

Usage: whatweb [options] <URLs>

TARGET SELECTION:
  <TARGETs>   Enter URLs, hostnames, IP addresses, or IP ranges in CIDR format.
  -i          Read targets from a file.

AGGRESSION:
  -a=LEVEL    Set the aggression level. Default: 1.
  1. Stealthy - Makes one HTTP request per target.
  3. Aggressive - If a level 1 plugin matches, additional requests are made.
  4. Heavy - Makes a lot of HTTP requests per target.

HTTP OPTIONS:
  -U=AGENT    Identify as AGENT instead of WhatWeb/0.6.3.
  -H          Add an HTTP header.
  --follow-redirect=WHEN  Control when to follow redirects (never/always/etc).
  --max-redirects=NUM     Maximum number of redirects. Default: 10.
```
---

## wafw00f
**Category:** Scanning/Recon
**Description:** Web Application Firewall (WAF) fingerprinting and detection tool.
**Common Usage:** `wafw00f <url>`
**Key Flags:**
- `-a` — Find all WAFs, don't stop at first match
- `-r` — Do not follow 3xx redirects
- `-t <waf>` — Test for one specific WAF
- `-l` — List all detectable WAFs
- `-o <file>` — Write output to csv/json/text file
- `-p <proxy>` — Use HTTP proxy
- `-v` — Verbose output
**Help Output:**
```
Usage: wafw00f url1 [url2 [url3 ... ]]
example: wafw00f http://www.victim.org/

Options:
  -v, --verbose         Enable verbosity
  -a, --findall         Find all WAFs, do not stop on first match
  -r, --noredirect      Do not follow redirections given by 3xx responses
  -t TEST, --test=TEST  Test for one specific WAF
  -o OUTPUT, --output=OUTPUT  Write output to csv, json or text file
  -l, --list            List all WAFs that WAFW00F is able to detect
  -p PROXY, --proxy=PROXY  Use an HTTP proxy
  -V, --version         Print version and exit.
```
---

## netdiscover
**Category:** Scanning/Recon
**Description:** Active/passive ARP reconnaissance tool for discovering hosts on a local network.
**Common Usage:** `netdiscover -i <interface> -r <range>`
**Key Flags:**
- `-i <device>` — Network interface to use
- `-r <range>` — Scan a given CIDR range
- `-l <file>` — Scan ranges from a file
- `-p` — Passive mode (only sniff, don't send)
- `-s <ms>` — Sleep time between ARP requests (milliseconds)
- `-c <n>` — Number of times to send each ARP request
- `-f` — Enable fast scan mode
- `-P` — Print results in parseable format and stop after active scan
**Help Output:**
```
Netdiscover 0.21 [Active/passive ARP reconnaissance tool]

Usage: netdiscover [-i device] [-r range | -l file | -p] [-s time] [-c count] [-n node] [-dfPLNS]
  -i device: your network device
  -r range:  scan a given range, e.g. 192.168.6.0/24,/16,/8
  -l file:   scan the list of ranges in the given file
  -p         passive mode: do not send anything, only sniff
  -s time:   time to sleep between each ARP request (milliseconds)
  -c count:  number of times to send each ARP request
  -n node:   last source IP octet used for scanning (from 2 to 253)
  -f         enable fastmode scan, saves a lot of time
  -P         print results in a format suitable for parsing by another program
  -N         Do not print header (only valid when -P or -L is enabled)
  -S         enable sleep time suppression between each request (hardcore mode)
```
---

## arp-scan
**Category:** Scanning/Recon
**Description:** Sends ARP packets to discover hosts on a local network; more reliable than ICMP ping for local network host discovery.
**Common Usage:** `arp-scan --localnet` | `arp-scan <target>`
**Key Flags:**
- `--localnet` / `-l` — Scan all hosts on the local network
- `--interface=<iface>` / `-I` — Use specific network interface
- `--file=<file>` / `-f` — Read targets from file
- `--verbose` / `-v` — Verbose output
- `--retry=<n>` / `-r` — Send n ARP packets per host (default 2)
- `--timeout=<ms>` / `-t` — Timeout in milliseconds
- `--bandwidth=<bps>` / `-B` — Set bandwidth for outgoing packets
**Help Output:**
```
Usage: arp-scan [options] [hosts...]

Target hosts must be specified on the command line unless the --file or
--localnet option is used.

General Options:
--help or -h        Display this usage message and exit.
--verbose or -v     Display verbose progress messages.
--version or -V     Display program version details and exit.
--interface=<s>     Use network interface <s>.

Targets can be IPv4 addresses or hostnames. You can also use CIDR notation
(10.0.0.0/24), ranges (10.0.0.1-10.0.0.10), or network:mask notation.
```
---

## amass
**Category:** Scanning/Recon
**Description:** In-depth attack surface mapping and asset discovery tool for DNS enumeration and subdomain collection from multiple sources.
**Common Usage:** `amass enum -d <domain>` | `amass intel -org <org>`
**Key Flags (enum subcommand):**
- `-d <domain>` — Target domain
- `-o <file>` — Output file
- `-passive` — Passive mode only
- `-active` — Active recon (zone transfers, cert grabbing)
- `-brute` — Brute force subdomains
- `-w <wordlist>` — Wordlist for brute force
- `-r <resolvers>` — Custom DNS resolvers
- `-src` — Print data source for each result
**Version:** 5.0.1
---
