# Wireless Attack Tools

## aircrack-ng
**Category:** Wireless
**Description:** 802.11 WEP and WPA/WPA2-PSK key cracking program. Part of the aircrack-ng suite. Works by performing statistical analysis on captured IVs or dictionary attacks against captured handshakes.
**Version:** 1.7
**Common Usage:** `aircrack-ng -w <wordlist> <capture.cap>` | `aircrack-ng -b <bssid> capture*.cap`
**Key Flags:**
- `-w <wordlist>` — Path to wordlist file(s)
- `-b <bssid>` — Target AP MAC address
- `-e <essid>` — Target network SSID
- `-a <1|2>` — Force attack mode (1=WEP, 2=WPA-PSK)
- `-p <n>` — Number of CPU cores to use
- `-l <file>` — Write key to file
- `-j <file>` — Create Hashcat HCCAPX file
- `-E <file>` — Create EWSA Project file
- `-I <str>` — PMKID string for hashcat -m 16800
- `-q` — Quiet mode
**Help Output:**
```
Aircrack-ng 1.7 - (C) 2006-2022 Thomas d'Otreppe
https://www.aircrack-ng.org

usage: aircrack-ng [options] <input file(s)>

Common options:
    -a <amode>  : force attack mode (1/WEP, 2/WPA-PSK)
    -e <essid>  : target selection: network identifier
    -b <bssid>  : target selection: access point's MAC
    -p <nbcpu>  : # of CPU to use (default: all CPUs)
    -q          : enable quiet mode (no status output)
    -l <file>   : write key to file

Static WEP cracking options:
    -n <nbits>  : WEP key length: 64/128/152/256/512
    -f <fudge>  : bruteforce fudge factor, default: 2
    -K          : use only old KoreK attacks (pre-PTW)

WEP and WPA-PSK cracking options:
    -w <words>  : path to wordlist(s) filename(s)

WPA-PSK options:
    -j <file>   : create Hashcat v3.6+ file (HCCAPX)
    -I <str>    : PMKID string (hashcat -m 16800)
```

**Typical WPA cracking workflow:**
```bash
# 1. Put interface in monitor mode
airmon-ng start wlan0

# 2. Capture traffic
airodump-ng wlan0mon

# 3. Focus on target AP and capture handshake
airodump-ng -c <channel> --bssid <AP_MAC> -w capture wlan0mon

# 4. Deauth a client to force handshake (in separate terminal)
aireplay-ng --deauth 10 -a <AP_MAC> -c <Client_MAC> wlan0mon

# 5. Crack the handshake
aircrack-ng -w /usr/share/wordlists/rockyou.txt capture-01.cap
```
---

## airodump-ng
**Category:** Wireless
**Description:** 802.11 packet capture program for collecting IVs and capturing WPA handshakes. Part of the aircrack-ng suite.
**Common Usage:** `airodump-ng <interface>` | `airodump-ng -c <ch> --bssid <mac> -w <prefix> <interface>`
**Key Flags:**
- `--write <prefix>` / `-w` — Dump file prefix
- `--bssid <mac>` — Filter by AP MAC address
- `--essid <ssid>` — Filter by ESSID
- `-c <channel>` — Lock to specific channel
- `--ivs` — Save only captured IVs (WEP only)
- `--beacons` — Record all beacons in dump file
- `--update <secs>` — Display update delay
- `--output-format <formats>` — Output format: pcap, ivs, csv, gps, kismet, netxml
- `-r <file>` — Read packets from capture file
- `--wps` — Display WPS information
**Help Output:**
```
Airodump-ng 1.7 - (C) 2006-2022 Thomas d'Otreppe
https://www.aircrack-ng.org

usage: airodump-ng <options> <interface>[,<interface>,...]

Options:
    --ivs                 : Save only captured IVs
    --gpsd                : Use GPSd
    --write      <prefix> : Dump file prefix
    --beacons             : Record all beacons in dump file
    --update       <secs> : Display update delay in seconds
    -h                    : Hides known stations for --showack
    -f            <msecs> : Time in ms between hopping channels
    -r             <file> : Read packets from that file
    --manufacturer        : Display manufacturer from IEEE OUI list
    --wps                 : Display WPS information (if any)
    --output-format <formats>  : pcap, ivs, csv, gps, kismet, netxml, logcsv
    --ignore-negative-one : Removes the message about fixed channel -1

Filter options:
    --encrypt   <suite>   : Filter APs by cipher suite
    --netmask <netmask>   : Filter APs by mask
    --bssid     <bssid>   : Filter APs by BSSID
    --essid     <essid>   : Filter APs by ESSID
    --min-packets   <int> : Minimum AP packets recv'd before displaying (default: 2)
```
---

## airmon-ng
**Category:** Wireless
**Description:** Script to enable/disable monitor mode on wireless interfaces. Part of the aircrack-ng suite.
**Common Usage:** `airmon-ng start <interface>` | `airmon-ng stop <interface>`
**Key Commands:**
- `airmon-ng` — List wireless interfaces
- `airmon-ng start <iface>` — Enable monitor mode (creates wlan0mon)
- `airmon-ng stop <iface>` — Disable monitor mode
- `airmon-ng check` — Check for processes that may interfere
- `airmon-ng check kill` — Kill interfering processes
**Note:** Requires physical wireless hardware or compatible USB adapter; limited functionality in Docker without host network access.
---

## reaver
**Category:** Wireless
**Description:** WPS (Wi-Fi Protected Setup) PIN brute-force attack tool. Exploits the WPS protocol to recover WPA/WPA2 passphrases.
**Version:** 1.6.6
**Common Usage:** `reaver -i <monitor_interface> -b <bssid> -vv`
**Key Flags:**
- `-i <iface>` — Monitor-mode interface
- `-b <bssid>` — BSSID of target AP
- `-e <essid>` — ESSID of target AP
- `-c <channel>` — Set 802.11 channel
- `-K` / `-Z` — Run Pixie Dust attack
- `-p <pin>` — Use specified WPS PIN
- `-d <secs>` — Delay between PIN attempts (default: 1)
- `-l <secs>` — Lock delay if AP locks WPS (default: 60)
- `-S` — Use small DH keys (improve speed)
- `-L` — Ignore AP lock state
- `-v / -vv` — Verbose / very verbose
- `-N` — Do not send NACKs
**Help Output:**
```
Reaver v1.6.6 WiFi Protected Setup Attack Tool

Required Arguments:
    -i, --interface=<wlan>    Name of the monitor-mode interface to use
    -b, --bssid=<mac>         BSSID of the target AP

Optional Arguments:
    -e, --essid=<ssid>        ESSID of the target AP
    -c, --channel=<channel>   Set the 802.11 channel for the interface
    -s, --session=<file>      Restore a previous session file
    -f, --fixed               Disable channel hopping
    -5, --5ghz                Use 5GHz 802.11 channels
    -v, --verbose             Display non-critical warnings
    -q, --quiet               Only display critical messages

Advanced Options:
    -p, --pin=<wps pin>       Use the specified pin
    -d, --delay=<seconds>     Set the delay between pin attempts [1]
    -l, --lock-delay=<seconds> Set the time to wait if AP locks WPS [60]
    -g, --max-attempts=<num>  Quit after num pin attempts
    -S, --dh-small            Use small DH keys to improve crack speed
    -L, --ignore-locks        Ignore locked state reported by target AP
    -K, --pixie-dust          Run pixiedust attack
```
---

## wifite
**Category:** Wireless
**Description:** Automated wireless attack tool that attacks WEP, WPA, and WPS networks automatically by running aircrack-ng suite tools in sequence.
**Version:** 2.8.2
**Common Usage:** `wifite` (interactive scan) | `wifite --wpa --dict <wordlist>`
**Key Flags:**
- `--interface <iface>` / `-i` — Wireless interface
- `--channel <ch>` / `-c` — Channels to scan
- `--wpa` — Attack only WPA networks
- `--wep` — Attack only WEP networks
- `--wps` — Attack only WPS-enabled networks
- `--wpa3` — Attack WPA3 networks
- `--dict <file>` — Wordlist for WPA cracking
- `--pmkid` — Only use PMKID capture attack
- `--no-pmkid` — Disable PMKID capture
- `-p <secs>` — Pillage: attack all targets after scan_time seconds
- `--kill` — Kill processes that conflict with Airmon
- `--pow <n>` — Minimum signal strength
- `--nodeauths` — Never send deauth packets (passive)
**Help Output:**
```
wifite2 2.8.1 - a wireless auditor by derv82

options:
  -i [interface]                Wireless interface to use
  -c [channel]                  Wireless channel to scan
  -inf, --infinite              Enable infinite attack mode
  -mac, --random-mac            Randomize wireless card MAC address
  -p [scan_time]                Pillage: Attack all targets after scan_time seconds
  --kill                        Kill processes that conflict with Airmon/Airodump
  --skip-crack                  Skip cracking captured handshakes/pmkid
  --nodeauths                   Passive mode: Never deauthenticates clients

WEP:
  --wep                         Show only WEP-encrypted networks
  --keep-ivs                    Retain .IVS files and reuse when cracking

WPA:
  --wpa                         Show only WPA/WPA2-encrypted networks
  --dict [file]                 File containing passwords for cracking

WPS:
  --wps                         Show only WPS-enabled networks
  --bully                       Use bully program for WPS attacks
  --reaver                      Use reaver program for WPS attacks
  --ignore-locks                Do not stop WPS PIN attack if AP becomes locked

PMKID:
  --pmkid                       Only use PMKID capture
  --no-pmkid                    Don't use PMKID capture
```
---

## bully
**Category:** Wireless
**Description:** Alternative WPS brute-force tool. Uses a different approach from reaver and may succeed where reaver fails.
**Version:** 1.4.00
**Common Usage:** `bully <interface> -b <bssid> -e <essid> -c <channel>`
**Key Flags:**
- `-b <bssid>` — BSSID of target AP
- `-e <essid>` — ESSID of target AP
- `-c <channel>` — 802.11 channel
- `-d` — Enable Pixie Dust attack
- `-v <n>` — Verbosity (1-3)
---

## kismet
**Category:** Wireless
**Description:** Wireless network and device detector, sniffer, and intrusion detection system for 802.11 and Bluetooth.
**Version:** 2025.09.R1
**Common Usage:** `kismet -c <interface>`
**Key Flags:**
- `-c <source>` — Capture source (e.g., wlan0, wlan0:type=linuxwifi)
- `--no-ncurses` — Disable ncurses UI (use REST API instead)
- `--daemonize` — Run as daemon
- Access web UI at http://localhost:2501 after starting
---
