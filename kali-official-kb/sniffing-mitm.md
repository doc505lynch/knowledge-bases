# Sniffing & MITM Tools

## tcpdump
**Category:** Sniffing/MITM
**Description:** Command-line packet analyzer. Captures and displays network packets matching a BPF filter expression.
**Version:** 4.99.5 (libpcap 1.10.6)
**Common Usage:** `tcpdump -i <interface> [filter]` | `tcpdump -i eth0 -w capture.pcap`
**Key Flags:**
- `-i <interface>` — Capture on specified interface (`-i any` for all)
- `-w <file>` — Write packets to pcap file
- `-r <file>` — Read packets from pcap file
- `-n` — Don't resolve hostnames
- `-nn` — Don't resolve hostnames or port names
- `-v / -vv / -vvv` — Verbose output
- `-X` — Print packet data in hex and ASCII
- `-A` — Print packets in ASCII only
- `-c <count>` — Capture only N packets
- `-s <snaplen>` — Snapshot length (0 = full packet)
- `-G <secs>` — Rotate capture file every N seconds (use with -w)
- `host <ip>` — Filter by host
- `port <n>` — Filter by port
- `net <network>` — Filter by network
- `tcp/udp/icmp` — Filter by protocol
**Help Output:**
```
tcpdump version 4.99.5
libpcap version 1.10.6 (64-bit time_t, with TPACKET_V3)
OpenSSL 3.5.5 27 Jan 2026

Usage: tcpdump [-AbdDefhHIJKlLnNOpqStuUvxX#] [ -B size ] [ -c count ] [--count]
        [ -C file_size ] [ -E algo:secret ] [ -F file ] [ -G seconds ]
        [ -i interface ] [ --immediate-mode ] [ -j tstamptype ]
        [ -M secret ] [ --number ] [ --print ] [ -Q in|out|inout ]
        [ -r file ] [ -s snaplen ] [ -T type ] [ --version ]
        [ -V file ] [ -w file ] [ -W filecount ] [ -y datalinktype ]
        [ --time-stamp-precision precision ] [ --micro ] [ --nano ]
        [ -z postrotate-command ] [ -Z user ] [ expression ]
```

**Common filter examples:**
```bash
# Capture all traffic on eth0
tcpdump -i eth0 -v

# Capture and save to file
tcpdump -i eth0 -w capture.pcap

# Filter by host and port
tcpdump -i eth0 host 192.168.1.1 and port 80

# Capture HTTP traffic (GET/POST)
tcpdump -i eth0 -A -s 0 'tcp port 80 and (((ip[2:2] - ((ip[0]&0xf)<<2)) - ((tcp[12]&0xf0)>>2)) != 0)'

# Capture credentials (insecure protocols)
tcpdump -i eth0 port 21 or port 23 or port 110 or port 143 -A
```
---

## tshark
**Category:** Sniffing/MITM
**Description:** Terminal-based version of Wireshark. Provides deep packet inspection with display filters and dissection of hundreds of protocols.
**Version:** 4.6.4 (Wireshark)
**Common Usage:** `tshark -i <interface>` | `tshark -r <file> -Y <display_filter>`
**Key Flags:**
- `-i <interface>` — Capture interface
- `-r <file>` — Read from pcap file
- `-w <file>` — Write to pcap file
- `-Y <filter>` — Display filter (Wireshark syntax)
- `-f <filter>` — Capture filter (BPF syntax)
- `-T <format>` — Output format: fields, json, pdml, text
- `-e <field>` — Extract specific field (with `-T fields`)
- `-E <opt>` — Field options (separator, header, etc.)
- `-c <count>` — Stop after N packets
- `-D` — List available interfaces
- `-a duration:<n>` — Stop after N seconds
- `-b filesize:<n>` — Ring buffer file size in KB
**Help Output:**
```
TShark (Wireshark) 4.6.4
Dump and analyze network traffic.

Usage: tshark [options] ...

Capture interface:
  -i <interface>              name or idx of interface (def: first non-loopback)
  -f <capture filter>         packet filter in libpcap filter syntax
  -s <snaplen>                packet snapshot length
  -p, --no-promiscuous-mode   don't capture in promiscuous mode
  -D, --list-interfaces       print list of interfaces and exit
  -L, --list-data-link-types  print list of link-layer types of iface and exit

Capture stop conditions:
  -c <packet count>           stop after n packets (def: infinite)
  -a <autostop cond.> ...     duration:NUM, filesize:NUM, files:NUM, packets:NUM

Input file:
  -r <infile>, --read-file <infile>  set the filename to read from (or '-' for stdin)

Processing:
  -Y <display filter>, --display-filter <display filter>  apply display filter to packet data

Output:
  -T fields|json|pdml|text    format of text output (def: text)
  -e <field>                  field to print (requires -T fields)
  -w <outfile|->              write captured packets to outfile (or '-' for stdout)
```

**Common usage examples:**
```bash
# Live capture with display filter
tshark -i eth0 -Y 'http.request.method == "POST"'

# Extract credentials from pcap
tshark -r capture.pcap -Y 'ftp.request.command == "PASS"' -T fields -e ftp.request.arg

# Extract HTTP passwords
tshark -r capture.pcap -Y 'http.request.method==POST' -T fields -e http.file_data

# Follow TCP stream
tshark -r capture.pcap -z follow,tcp,ascii,0

# JSON output for a specific field
tshark -r capture.pcap -T fields -e ip.src -e ip.dst -e tcp.dstport -E separator=,
```
---

## responder
**Category:** Sniffing/MITM
**Description:** LLMNR/NBT-NS/mDNS poisoner and rogue authentication server. Captures credentials by responding to broadcast name resolution requests on the local network.
**Version:** 3.2.2.0
**Common Usage:** `responder -I <interface> -rdw`
**Key Flags:**
- `-I <interface>` — Network interface to use (or 'ALL' for all)
- `-A` — Analyze mode: see requests without poisoning (passive)
- `-r` — Enable answers for NetBIOS wredir suffix queries
- `-d` — Enable answers for NetBIOS domain suffix queries
- `-w` — Start WPAD rogue proxy server
- `-F` — Force NTLM/Basic auth on wpad.dat file retrieval
- `-P` — Force proxy auth (use with -F)
- `-e <ip>` — Poison with a different IPv4 address
- `-6` — Poison with IPv6 (RDNSS)
- `--disable-ess` — Disable Extended Session Security
- `-v` — Verbose mode
**Help Output:**
```
Responder - LLMNR/NBT-NS/mDNS Poisoner and Rogue Authentication Servers
Captures credentials by responding to broadcast/multicast name resolution,
DHCP, DHCPv6 requests

Options:
  Required Options:
    -I eth0, --interface=eth0   Network interface to use. Use 'ALL' for all interfaces.

  Poisoning Options:
    -A, --analyze       Analyze mode. See requests without poisoning. (passive)
    -e IP, --externalip=IP  Poison with a different IPv4 address than Responder's.
    -6 IPv6, --externalip6=IPv6  Poison with a different IPv6 address.
    --rdnss             Poison via Router Advertisements with RDNSS.
    -t HEX, --ttl=HEX   Set TTL for poisoned answers.

  DHCP Options:
    -d, --DHCP          Enable DHCPv4 poisoning. Injects WPAD in DHCP responses.

Credentials are saved to /usr/share/responder/logs/
```

**Common usage examples:**
```bash
# Standard LLMNR/NBT-NS poisoning
responder -I eth0 -rdw

# Passive analysis mode (no poisoning)
responder -I eth0 -A

# Force WPAD authentication
responder -I eth0 -wFP
```
---

## ettercap
**Category:** Sniffing/MITM
**Description:** Comprehensive suite for man-in-the-middle attacks. Features ARP poisoning, packet filtering, sniffing, and protocol dissection.
**Version:** 0.8.4
**Common Usage:** `ettercap -T -q -i <iface> -M arp:remote /<gw_ip>// /<target_ip>//`
**Key Flags:**
- `-T` — Text-only GUI
- `-G` — GTK+ GUI
- `-C` — Curses GUI
- `-D` — Daemon mode (no GUI)
- `-M <method:args>` — MITM method (arp, arp:remote, icmp, port, dhcp)
- `-i <iface>` — Network interface
- `-r <file>` — Read from pcap file
- `-w <file>` — Write to pcap file
- `-f <filter>` — pcap capture filter
- `-F <file>` — Load filter from compiled ettercap filter file
- `-q` — Quiet mode (don't display packet contents)
- `-L <logfile>` — Log all traffic
- `-P <plugin>` — Load plugin
**Help Output:**
```
ettercap 0.8.4

Usage: ettercap [OPTIONS] [TARGET1] [TARGET2]

TARGET is in the format MAC/IP/IPv6/PORTs

Sniffing and Attack options:
  -M, --mitm <METHOD:ARGS>    perform a mitm attack
  -o, --only-mitm             don't sniff, only perform the mitm attack
  -b, --broadcast             sniff packets destined to broadcast
  -B, --bridge <IFACE>        use bridged sniff (needs 2 ifaces)
  -p, --nopromisc             do not put the iface in promisc mode
  -S, --nosslmitm             do not forge SSL certificates
  -r, --read <file>           read data from pcapfile
  -f, --pcapfilter <string>   set the pcap filter string
  -R, --reversed              use reversed TARGET matching

User Interface Type:
  -T, --text                  use text only GUI
  -C, --curses                use curses GUI
  -D, --daemon                daemonize ettercap (no GUI)
  -G, --gtk                   use GTK+ GUI

Logging options:
  -w, --write <file>          write sniffed data to pcapfile
  -L, --log <logfile>         log all the traffic
  -l, --log-info <logfile>    log only passive infos
```

**Common ARP poisoning examples:**
```bash
# ARP poison between gateway and target (intercept traffic)
ettercap -T -q -i eth0 -M arp:remote /192.168.1.1// /192.168.1.100//

# Poison entire subnet
ettercap -T -q -i eth0 -M arp:remote /192.168.1.1// //
```
---

## dsniff
**Category:** Sniffing/MITM
**Description:** Collection of tools for network auditing and penetration testing. Includes password sniffers for various protocols.
**Version:** 2.5a2
**Tools in the package:**
- `dsniff` — Password sniffer for multiple protocols (FTP, Telnet, SMTP, HTTP, etc.)
- `arpspoof` — ARP spoofing (for MITM setup)
- `dnsspoof` — DNS spoofing
- `macof` — MAC address flooding (for switch overloading)
- `tcpkill` — Kill TCP connections
- `tcpnice` — Slow down TCP connections
- `urlsnarf` — Sniff HTTP requests in CLF format
- `webspy` — Mirror web browsing sessions
**Common Usage:**
```bash
# Enable IP forwarding first
echo 1 > /proc/sys/net/ipv4/ip_forward

# ARP spoof (redirect target through attacker)
arpspoof -i eth0 -t <target_ip> <gateway_ip>

# Sniff passwords
dsniff -i eth0

# Sniff URLs
urlsnarf -i eth0
```
---
