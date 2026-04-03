# Kali Linux — Installation

Source: https://www.kali.org/docs/installation/

---

## Available Installation Guides

- Hard disk install (standard): https://www.kali.org/docs/installation/hard-disk-install/
- Dual boot with Windows: https://www.kali.org/docs/installation/dual-boot-kali-with-windows/
- Dual boot with Linux: https://www.kali.org/docs/installation/dual-boot-kali-with-linux/
- Dual boot with macOS/OS X: https://www.kali.org/docs/installation/dual-boot-kali-with-mac/
- PXE network install: https://www.kali.org/docs/installation/network-pxe/
- BTRFS install (Kali Unkaputtbar): https://www.kali.org/docs/installation/btrfs/
- Installing on Mac hardware: https://www.kali.org/docs/installation/mac-installer/
- Bare-bones Kali: https://www.kali.org/docs/installation/barebone-kali/
- Kali installation sizes: https://www.kali.org/docs/installation/installation-sizes/
- Installing old i386 images: https://www.kali.org/docs/installation/kali-linux-i386-eol/

---

## Standard Hard Disk Installation

Source: https://www.kali.org/docs/installation/hard-disk-install/

### System Requirements

| Configuration | RAM | Disk |
|--------------|-----|------|
| Minimal (SSH server, no desktop) | 128 MB minimum (512 MB recommended) | 2 GB |
| Standard (Xfce desktop, default metapackage) | 2 GB | 20 GB |
| Resource-intensive (Burp Suite, etc.) | 8 GB+ | 20 GB+ |

### Prerequisites

- amd64 installer image downloaded from kali.org
- CD/DVD or USB boot capability
- Single disk for installation
- Network connection with DHCP, DNS, and internet access

### Pre-Installation Steps

1. Download the official Kali Linux installer image from https://www.kali.org/get-kali/
2. Burn ISO to DVD or create bootable USB drive
3. Back up all existing data on the target device
4. Configure BIOS/UEFI to boot from the installation media
5. **Disable Secure Boot** — Kali's kernel is unsigned and will not boot with Secure Boot enabled

### Installation Process

#### 1. Boot Selection
Choose between:
- **Graphical install** (recommended for most users)
- **Install** (text-mode, for systems without graphical support)

#### 2. Language and Locale Configuration
Select:
- Preferred language
- Geographic location
- Keyboard layout

#### 3. Network Setup
- System probes network interfaces and attempts DHCP
- Enter a system hostname (e.g., `kali`)
- Optionally provide a domain name
- Configure manually if DHCP is unavailable

#### 4. User Account Creation
Create a standard user account with:
- Full name
- Username
- Strong password

#### 5. Time Zone Selection
Set your local time zone.

#### 6. Disk Partitioning

**Guided options:**
- **Entire disk** — Recommended for single-boot installations
- **Entire disk with encrypted LVM** — For Full Disk Encryption (FDE)
- **Manual** — For advanced users with custom partition needs

**Common partition layouts:**
- Single partition (simplest, default)
- Separate partitions for `/home`, `/var`, `/tmp`

**If using FDE:** The system performs a secure disk wipe before requesting an LVM encryption passphrase. This can take time depending on disk size.

#### 7. Proxy Configuration
Enter proxy information if required for repository access. Leave blank if connecting directly.

#### 8. Metapackage Selection
Choose desktop environments and tool groups. Default selections provide the standard Kali installation with the Xfce desktop.

#### 9. GRUB Bootloader
Install GRUB to the target drive (typically `/dev/sda`).

#### 10. Reboot
Remove installation media and boot into the new system.

---

## Dual Boot with Windows

Source: https://www.kali.org/docs/installation/dual-boot-kali-with-windows/

### Prerequisites

- Reviewed the standard installation guide above
- Use the **Live** image (not the installer image)
- Single disk with existing Windows installation

### Step 1: Disable Windows Fast Startup

Navigate: **Control Panel > Hardware and Sound > Power Options**
Disable: "Turn on fast startup"

This prevents partition resizing errors that can cause data corruption.

### Step 2: Resize the Windows Partition

1. Boot from the Kali Live USB/DVD
2. Launch **GParted** from the desktop
3. Select the Windows main partition (typically `/dev/sda2`)
4. Resize it, leaving a minimum of **20 GB** of unallocated free space for Kali
5. Click "Apply All Operations"
6. Reboot

**Warning:** Only modify unused space. Do not edit any partition regions shown as "in use" in GParted.

### Step 3: Install Kali into Free Space

During the Kali installer's partitioning step:
- Select **"Guided - use the largest continuous free space"**
- Do NOT select "use entire disk" (this will overwrite Windows)

Complete the installation normally.

### Step 4: Post-Installation

After reboot, the **GRUB boot menu** will present both Kali Linux and Windows as options.

#### Fix Clock Discrepancies (Windows/Linux Time Conflict)

If the system clock shows different times when switching between OSes:

```bash
# Set hardware clock to local time (fixes Windows compatibility)
timedatectl set-local-rtc 1 --adjust-system-clock

# Revert to UTC (standard Linux behavior)
timedatectl set-local-rtc 0 --adjust-system-clock
```

---

## PXE Network Installation

Source: https://www.kali.org/docs/installation/network-pxe/

Useful for systems without CD/USB ports or for enterprise mass deployments.

### Install and Configure dnsmasq (DHCP + TFTP)

```bash
sudo apt install -y dnsmasq
```

Configure `/etc/dnsmasq.conf`:

```bash
cat <<EOF | sudo tee /etc/dnsmasq.conf
interface=eth0
dhcp-range=192.168.101.100,192.168.101.200,12h
dhcp-boot=pxelinux.0
enable-tftp
tftp-root=/tftpboot/
dhcp-option=3,192.168.101.1
dhcp-option=6,8.8.8.8,8.8.4.4
EOF
```

### Set Up TFTP Root Directory

```bash
sudo mkdir -pv /tftpboot/
sudo systemctl restart dnsmasq
sudo systemctl enable dnsmasq
```

### Download Kali Netboot Images

```bash
sudo wget https://http.kali.org/kali/dists/kali-rolling/main/installer-amd64/current/images/netboot/netboot.tar.gz -P /tftpboot/
sudo tar -zxpvf /tftpboot/netboot.tar.gz -C /tftpboot
sudo rm -v /tftpboot/netboot.tar.gz
```

### Boot Target Systems

On target machines, access the boot menu (ESC, F2, F8, or F12 depending on BIOS) and select **Network Boot / PXE**.

### Keep Netboot Images Updated

Create a cron job or script to pull updated netboot images regularly to keep up with kernel updates.

### Unattended / Pre-seeded Installation

Integrate preseed configurations into the initrd at `/tftpboot/debian-installer/amd64/initrd` for fully automated installations.

### Alternative: netbootxyz

Follow the netbootxyz official documentation to integrate with an existing DHCP server and manage boot options via a web interface.
