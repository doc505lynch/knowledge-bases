# Kali Linux — Networking

Source: https://www.kali.org/docs/networking/

---

## Repository and Sources Configuration

Source: https://www.kali.org/docs/general-use/kali-linux-sources-list-repositories/

### Default Repository Entry

A standard Kali Linux installation uses this entry in `/etc/apt/sources.list`:

```
deb http://http.kali.org/kali kali-rolling main contrib non-free non-free-firmware
```

This is configured by default even if there was no network access during installation (since version 2020.3).

### Available Branches

| Branch | Description | Use Case |
|--------|-------------|----------|
| `kali-rolling` | Continuously updated, default | Most users |
| `kali-last-snapshot` | Point releases, more stable | Users wanting stability |
| `kali-experimental` | Testing packages, work-in-progress | Developers and testers |
| `kali-bleeding-edge` | Auto-synced from upstream git | Cutting-edge features |

### Switch to kali-rolling

```bash
sudo tee /etc/apt/sources.list <<< "deb http://http.kali.org/kali kali-rolling main contrib non-free non-free-firmware"
```

### Add kali-bleeding-edge (in separate file)

```bash
echo "deb http://http.kali.org/kali kali-bleeding-edge main contrib non-free non-free-firmware" | sudo tee /etc/apt/sources.list.d/kali-bleeding-edge.list
```

### Repository Format Explained

```
deb   http://http.kali.org/kali   kali-rolling   main contrib non-free non-free-firmware
 |           |                          |                |
 |           |                          |                +-- Components (package categories)
 |           |                          +-- Branch (which Kali version)
 |           +-- Mirror URL (load balancer to optimal mirrors)
 +-- Archive type: deb (binary) or deb-src (source)
```

**Components:**
- `main` — Core packages that meet Debian Free Software Guidelines
- `contrib` — Packages that meet DFSG but depend on non-free packages
- `non-free` — Packages that do not meet DFSG
- `non-free-firmware` — Firmware packages (added in Debian 12 / Bookworm era)

### Critical Warnings

> **Do NOT add Kali's repository to a non-Kali OS.** Adding Kali's repository to Ubuntu, Debian, or any other distribution will highly increase the chance of your system breaking.

> **Do NOT add other OS repositories to Kali.** This is the single most common reason why Kali Linux systems break. Third-party software should use separate files in `/etc/apt/sources.list.d/`.

---

## Networking Configuration Guides (from kali.org/docs/networking/)

The Networking section covers:

- Network interface configuration
- Configuring wireless networking
- Proxy settings
- Network services setup
- Samba configuration for Windows file sharing

### Configuring a Static IP Address

```bash
# Edit network interfaces
sudo nano /etc/network/interfaces

# Example static configuration
auto eth0
iface eth0 inet static
    address 192.168.1.100
    netmask 255.255.255.0
    gateway 192.168.1.1
    dns-nameservers 8.8.8.8 8.8.4.4
```

### Restart Networking

```bash
sudo systemctl restart networking
# Or for NetworkManager users:
sudo systemctl restart NetworkManager
```

### Check Network Interfaces

```bash
ip addr show
ip link show
iwconfig          # For wireless interfaces
```

### Wireless Interface Management

```bash
# Bring interface up/down
sudo ip link set wlan0 up
sudo ip link set wlan0 down

# Check rfkill status (hardware/software radio kill)
rfkill list
rfkill unblock all
```
