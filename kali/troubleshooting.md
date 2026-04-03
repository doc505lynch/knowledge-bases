# Kali Linux — Troubleshooting

Source: https://www.kali.org/docs/troubleshooting/

---

## Available Troubleshooting Guides

| Issue | URL |
|-------|-----|
| Download speed issues | https://www.kali.org/docs/troubleshooting/download-issues/ |
| APT problems | https://www.kali.org/docs/troubleshooting/apt-get-upgrade-issues/ |
| Basic troubleshooting | https://www.kali.org/docs/troubleshooting/basic-troubleshooting/ |
| Installation failures | https://www.kali.org/docs/troubleshooting/installation-failures/ |
| Wireless driver issues | https://www.kali.org/docs/troubleshooting/troubleshooting-wireless-driver-issues/ |
| Windows antivirus warnings | https://www.kali.org/docs/troubleshooting/windows-antivirus-warnings/ |
| Cloud setup issues | https://www.kali.org/docs/troubleshooting/cloud-setup/ |
| Minimum install setup | https://www.kali.org/docs/troubleshooting/common-minimum-setup/ |
| Dual boot fixes | https://www.kali.org/docs/troubleshooting/dual-boot-issues/ |
| Graphics issues (bare metal) | https://www.kali.org/docs/troubleshooting/graphics-issues/ |
| PostgreSQL collation errors | https://www.kali.org/docs/troubleshooting/postgresql-collation-errors/ |
| Audio problems | https://www.kali.org/docs/troubleshooting/audio-issues/ |

---

## Wireless Driver Troubleshooting

Source: https://www.kali.org/docs/troubleshooting/troubleshooting-wireless-driver-issues/

**Note:** 90% of wireless issues reported to the Kali team are due to users not reading the Aircrack-ng documentation first. Always check https://www.aircrack-ng.org/doku.php first.

### Diagnostic Framework

#### Scenario 1: No Interface Detected

```bash
# Check if device is recognized by the system
lsusb           # For USB wireless adapters
lspci           # For PCIe/internal wireless cards

# Check for driver loading errors
dmesg | grep -i wifi
dmesg | grep -i wlan
dmesg | grep -i firmware

# If using a VM, confirm the USB device is attached to the VM (not the host)
```

**Possible causes:**
- Device not physically connected
- Driver not installed
- Firmware not installed
- For VMs: device not passed through to VM

#### Scenario 2: Interface Present But Not Working

```bash
# View recent kernel messages
dmesg | tail -20

# Check rfkill (hardware/software radio kill switch)
rfkill list
rfkill unblock all

# Verify firmware is installed
apt list --installed | grep firmware
```

**Check BIOS settings:** Some laptops have a hardware Wi-Fi kill switch or BIOS setting that disables wireless.

#### Scenario 3: Monitor Mode Not Available

Common causes:
- **STA drivers** (Ralink, Broadcom) do not support monitor mode
- **ndiswrapper** does not support monitor mode
- Hardware switch or BIOS restriction blocking packet capture

Adapters that work reliably in monitor mode typically use Atheros, Ralink RT3070/RT5572, or Realtek RTL8812AU chipsets.

#### Scenario 4: Packet Injection Not Working

```bash
# Put interface in monitor mode
sudo airmon-ng start wlan0

# Kill interfering processes (NetworkManager, wpa_supplicant)
sudo airmon-ng check kill

# Test injection
aireplay-ng -9 wlan0mon

# Check rfkill again
rfkill list
```

---

## APT / Package Management Problems

Source: https://www.kali.org/docs/troubleshooting/apt-get-upgrade-issues/

### Fix Broken Package State

```bash
sudo dpkg --configure -a
sudo apt install -f
sudo apt update
sudo apt dist-upgrade
```

### Fix "Hash Sum Mismatch" Error

```bash
sudo apt clean
sudo rm -rf /var/lib/apt/lists/*
sudo apt update
```

### Fix "Repository Not Signed" / Expired Key Error

```bash
# Refresh the Kali archive keyring
sudo apt install -y kali-archive-keyring
sudo apt update
```

### Fix Held Packages

```bash
# See which packages are held
apt-mark showhold

# Unhold a specific package
sudo apt-mark unhold <package-name>
```

### Fix Dependency Conflicts

```bash
sudo apt --fix-broken install
sudo apt install -f
```

### Clear and Rebuild Package Cache

```bash
sudo apt clean
sudo apt autoclean
sudo apt update
```

### Never Do This (Breaks Systems)

- Do NOT add Ubuntu, Debian, or other non-Kali repositories to Kali's sources.list
- Do NOT mix Kali repositories with other distributions

---

## Common Minimum Setup Issues

After a minimal or cloud install, many tools are missing. Fix this by installing a metapackage:

```bash
sudo apt update

# Headless tools (no GUI)
sudo apt install -y kali-linux-headless

# Default Kali toolset
sudo apt install -y kali-linux-default

# Just the desktop environment (Xfce)
sudo apt install -y kali-desktop-xfce
```

### WSL Minimum Setup

For WSL users who want a GUI:

```bash
sudo apt install -y kali-win-kex
kex --win -s
```

### Docker Minimum Setup

Inside a Kali Docker container:

```bash
apt update && apt -y install kali-linux-headless
```

Note: `systemctl` does not work inside Docker containers.

---

## Installation Failures

### Common Causes

1. **Corrupt ISO** — Always verify the SHA256 hash of the downloaded ISO before writing to USB
2. **Bad USB write** — Re-flash the USB drive
3. **Secure Boot enabled** — Disable in BIOS/UEFI
4. **Insufficient disk space** — Need at least 20 GB for standard install
5. **BIOS/UEFI not set to boot from USB** — Configure boot order

### Verify ISO Integrity

```bash
# Download the SHA256 checksums file from kali.org alongside the ISO
sha256sum -c SHA256SUMS
```

---

## Dual Boot Issues

### GRUB Not Showing / Windows Not Listed

```bash
# Update GRUB to detect all OSes
sudo update-grub
sudo grub-mkconfig -o /boot/grub/grub.cfg
```

### Can't Boot Windows After Kali Install

```bash
# Install os-prober if not present
sudo apt install -y os-prober

# Run os-prober then update GRUB
sudo os-prober
sudo update-grub
```

### Clock Sync Issues Between Windows and Kali

```bash
# Make Linux use local time (matches Windows behavior)
timedatectl set-local-rtc 1 --adjust-system-clock
```

---

## Graphics Issues (Bare Metal Install)

### Black Screen After Boot

Try booting with `nomodeset` kernel parameter:
1. At the GRUB menu, press `E` to edit the boot entry
2. Find the line starting with `linux`
3. Add `nomodeset` before `quiet splash`
4. Press `Ctrl+X` to boot

Then install proper drivers after booting:

```bash
# For NVIDIA
sudo apt install -y nvidia-driver

# For AMD (usually works with open-source amdgpu driver by default)
sudo apt install -y firmware-amd-graphics
```

---

## PostgreSQL Collation Errors

This affects tools like Metasploit that use PostgreSQL.

```bash
# Check PostgreSQL status
sudo systemctl status postgresql

# Fix collation errors (may require database rebuild)
sudo pg_dropcluster --stop 15 main
sudo pg_createcluster --start 15 main

# Start and enable PostgreSQL
sudo systemctl enable postgresql --now
```

---

## Windows Antivirus Warnings

Kali's penetration testing tools (Metasploit payloads, password crackers, network scanners) will trigger antivirus alerts on Windows. This is **expected behavior** — these are real security testing tools.

When downloading Kali's tools on a Windows machine or sharing files between Kali and Windows:
- Add exceptions in Windows Defender for the tools directory
- Or use Kali in a VM or WSL with filesystem isolation
- This is not a false positive in the traditional sense — the tools are genuinely capable of what AV flags them for

---

## Audio Problems (Kali 2023.2+)

If you have no sound after upgrading to Kali 2023.2 or later (PipeWire migration):

```bash
# Install PipeWire audio stack
sudo apt install -y pipewire pipewire-pulse wireplumber

# Reload audio services
systemctl --user daemon-reload
systemctl --user restart pipewire pipewire-pulse wireplumber
```

---

## Getting Help

- **Forums:** https://forums.kali.org/
- **Discord:** https://discord.kali.org/
- **Bug Tracker:** https://bugs.kali.org/
- **Documentation contributions:** https://gitlab.com/kalilinux/documentation/
