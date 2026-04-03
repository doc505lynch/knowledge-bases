# Kali Linux — General Use (Post-Install)

Source: https://www.kali.org/docs/general-use/

---

## Topics Covered in General Use

- Updating Kali Linux
- Enabling root access
- Repository / sources.list configuration
- NVIDIA GPU driver installation
- Forensics mode
- SSH configuration
- Remote desktop (RDP/VNC/noVNC/Guacamole)
- YubiKey SSH authentication
- Forensics mode
- Installing Python apps via pipx
- Desktop environment switching
- Wayland display server
- Kali Bleeding Edge features
- Packages that behave differently with non-root users

---

## Updating Kali Linux

Source: https://www.kali.org/docs/general-use/updating-kali/

### Update Frequency

Users with default Kali installations should check for updates every few weeks. Verify all tools function correctly before engagements. Avoid updating during active engagements since rolling release updates can occasionally introduce breaking changes.

### Step 1: Verify Repository Configuration

Check `/etc/apt/sources.list` contains:

```
deb http://http.kali.org/kali kali-rolling main contrib non-free non-free-firmware
```

### Step 2: Update and Upgrade

```bash
sudo apt update
sudo apt dist-upgrade -y
```

### Alternative (Use Only When Necessary)

```bash
sudo apt update && sudo apt full-upgrade -y
```

**Warning:** `full-upgrade` may break your system. Only use it when standard `dist-upgrade` fails.

---

## Enabling Root Access

Source: https://www.kali.org/docs/general-use/enabling-root/

Kali uses a non-root user by default (since 2020). Two approaches are available: temporary elevation or permanent root enablement.

### Temporary Root Access

```bash
sudo su          # Uses your current user password
su -             # Uses root password (must be set first)
```

Exit root with `exit` or `Ctrl+D`.

### Permanent Root Enablement

#### Step 1: Set a Root Password

```bash
sudo passwd
```

Enter and confirm your new root password. Input will not display visually.

#### Step 2: Enable Root Login

**For SSH access:** Edit `/etc/ssh/sshd_config`:

```
# Change this line:
PermitRootLogin prohibit-password

# To allow password-based root SSH:
PermitRootLogin yes
```

Then restart SSH:

```bash
sudo systemctl restart ssh
```

**For Desktop Login (GNOME/KDE):** Install the root login package:

```bash
sudo apt -y install kali-root-login
```

Log out, then log back in using the root account.

---

## NVIDIA GPU Driver Installation

Source: https://www.kali.org/docs/general-use/install-nvidia-drivers-on-kali-linux/

### Prerequisites

- GPU with CUDA compute capability > 5.0 (recommended)
- `contrib` and `non-free` components enabled in sources.list
- System fully updated

### Prepare System

```bash
sudo apt update
sudo apt -y full-upgrade
sudo apt install linux-headers-$(uname -r) -y
[ -f /var/run/reboot-required ] && sudo reboot -f
```

### Identify Your GPU

**Dedicated desktop GPU:**

```bash
lspci | grep -i vga
lspci -s [YOUR_BUS_ID] -v
```

**Optimus laptop (dual GPU):**

```bash
sudo apt install -y nvidia-detect
nvidia-detect
lspci | grep -i vga
```

### Install Drivers

```bash
sudo apt install -y linux-headers-amd64
sudo apt install -y nvidia-driver nvidia-cuda-toolkit
```

Reboot to load the new kernel modules:

```bash
sudo reboot
```

### Verify Installation

```bash
nvidia-smi
lspci | grep -i vga
```

The kernel driver should now show `nvidia` instead of `nouveau`.

### Test with Hashcat (GPU benchmarking)

```bash
sudo apt install -y hashcat
hashcat -I        # Show OpenCL/CUDA device info
hashcat -b        # Run benchmark
```

### Troubleshoot OpenCL Issues

```bash
sudo apt install -y clinfo
clinfo

# List OpenCL ICD loaders
dpkg -l | grep -i icd

# Remove conflicting Mesa OpenCL
sudo apt remove mesa-opencl-icd
```

---

## Forensics Mode

Source: https://www.kali.org/docs/general-use/kali-linux-forensics-mode/

Kali Linux Live includes a dedicated forensics mode, originally introduced in BackTrack Linux. It is widely used because Kali is portable, easily deployable, and ships with popular open-source forensic tools.

### Key Protective Features

**Internal Hard Drive Protection:**
- Internal hard disks are **never** touched
- Swap partitions are **not** used
- No internal disk is auto-mounted

The Kali team validated this by hashing a drive before and after booting in forensics mode and confirmed the hashes matched (disk unchanged).

**Removable Media:**
- Auto-mounting of removable media is **disabled**
- USB drives, CDs, etc. will **not** be auto-mounted when inserted
- Nothing happens to any media without explicit user action

### How to Boot into Forensics Mode

Select **"Live (forensics mode)"** from the GRUB/boot menu when booting from a Kali Live USB or DVD.

### Important Disclaimer

Validate all forensic tools independently before relying on them in real investigations. The Kali team welcomes suggestions for additional open-source forensic tools.

---

## Packages That Behave Differently as Non-Root

Some Kali tools require root for certain functionality. Common examples:

- `nmap` — raw socket operations require root for SYN scans
- `aircrack-ng` suite — monitor mode and injection require root
- `wireshark` — packet capture requires root or membership in `wireshark` group

To add your user to the wireshark group:

```bash
sudo usermod -aG wireshark $USER
# Log out and back in for change to take effect
```

---

## Installing Python Applications via pipx

For Python tools that conflict with system packages, use `pipx`:

```bash
sudo apt install -y pipx
pipx install <tool-name>
pipx ensurepath
```

This installs each Python app in an isolated virtual environment.

---

## Remote Access Options

| Method | Description |
|--------|-------------|
| SSH | Standard terminal access |
| RDP + Xfce | Remote Desktop Protocol with Xfce desktop |
| noVNC | Browser-based VNC access |
| Guacamole | Full browser-based remote desktop gateway |
| Win-KeX | Kali desktop in Windows (WSL only) |
