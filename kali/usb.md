# Kali Linux — USB / Live Boot

Source: https://www.kali.org/docs/usb/

---

## Available Guides

- Making a Kali bootable USB (Linux): https://www.kali.org/docs/usb/live-usb-install-with-linux/
- Making a Kali bootable USB (macOS/OS X): https://www.kali.org/docs/usb/live-usb-install-with-mac/
- Making a Kali bootable USB (Windows): https://www.kali.org/docs/usb/live-usb-install-with-windows/
- Standalone encrypted Kali on USB: https://www.kali.org/docs/usb/usb-standalone-encrypted/
- Updating Kali on USB: https://www.kali.org/docs/usb/updating-kali-usb/
- Verifying USB write: https://www.kali.org/docs/usb/verifying-usb/
- Adding persistence: https://www.kali.org/docs/usb/usb-persistence/
- Adding encrypted persistence: https://www.kali.org/docs/usb/usb-persistence-encryption/
- USB boot in VMware: https://www.kali.org/docs/usb/usb-with-vmware/
- USB boot in VirtualBox: https://www.kali.org/docs/usb/usb-with-virtualbox/

---

## Making a Bootable USB Drive (Linux)

Source: https://www.kali.org/docs/usb/live-usb-install-with-linux/

### Requirements

- Verified Kali Linux ISO image (latest from https://www.kali.org/get-kali/)
- `dd` command or Etcher software
- USB drive with minimum **4 GB** capacity

### Method 1: Using dd (Command Line)

#### Step 1: Identify Your USB Device (Before Inserting)

```bash
sudo fdisk -l
```

Note all currently listed devices.

#### Step 2: Insert USB and Identify Its Path

Insert the USB drive, then run again:

```bash
sudo fdisk -l
```

The new device is your USB drive — typically `/dev/sdb`, `/dev/sdc`, etc.

#### Step 3: Write the ISO Image

Replace `/dev/sdX` with your actual device path (e.g., `/dev/sdb`):

**For newer systems (2017 and later):**

```bash
sudo dd if=kali-linux-2025.4-live-amd64.iso of=/dev/sdX conv=fsync bs=4M status=progress
```

**For older systems:**

```bash
sudo dd if=kali-linux-2025.4-live-amd64.iso of=/dev/sdX conv=fsync bs=4M
```

**CRITICAL WARNING:** `dd` will overwrite anything at the target path without confirmation. Double-check `/dev/sdX` is your USB drive, NOT your main hard drive. Data loss is not recoverable.

Expect 10+ minutes for completion. The process finishes when the shell returns and shows byte counts.

### Method 2: Using Etcher (Graphical)

1. Download Etcher from https://www.balena.io/etcher/
2. Launch Etcher
3. Click **"Select image"** and choose your Kali ISO
4. Verify the correct USB drive is selected
5. Click **"Flash!"**
6. Remove USB once the process completes

---

## Adding Persistence to a Kali Live USB

Source: https://www.kali.org/docs/usb/usb-persistence/

Persistence allows data (files, configurations, tool results) to survive across reboots of a Kali Live USB session.

### Prerequisites

- Kali Linux Live USB already created
- Root privileges or sudo access
- USB drive with at least **8 GB** capacity
- Running from a Linux-based system

### Step 1: Verify USB Device

```bash
lsblk
```

Identify your USB device. This guide uses `/dev/sdX` — replace with your actual device (e.g., `/dev/sdb`). Existing partitions will be `/dev/sdX1` and `/dev/sdX2`.

### Step 2: Create a New Partition

```bash
usb=/dev/sdX
sudo fdisk $usb <<< $(printf "p\nn\np\n\n\n\np\nw")
```

Verify the new partition was created:

```bash
lsblk
```

You should now see `/dev/sdX3`.

### Step 3: Format the Persistence Partition

```bash
usb=/dev/sdX
sudo mkfs.ext4 -L persistence ${usb}3
```

The `-L persistence` label is required — Kali looks for this label at boot.

### Step 4: Configure Persistence

```bash
sudo mkdir -pv /mnt/my_usb
sudo mount -v ${usb}3 /mnt/my_usb
echo "/ union" | sudo tee /mnt/my_usb/persistence.conf
sudo umount -v ${usb}3
```

### Step 5: Boot with Persistence Enabled

Reboot and from the GRUB boot menu, select **"Live USB Persistence"** instead of the regular Live boot.

### Multiple Persistence Stores (Advanced)

You can create multiple labeled persistence partitions (e.g., `work`, `personal`) and select which to use at boot by pressing **Tab** during boot and modifying the `persistence-label` kernel parameter.

---

## Adding Encrypted Persistence

Source: https://www.kali.org/docs/usb/usb-persistence-encryption/

Similar to standard persistence but the partition is encrypted with LUKS.

### Create and Encrypt the Partition

```bash
usb=/dev/sdX

# Create partition (same as standard persistence)
sudo fdisk $usb <<< $(printf "n\np\n\n\n\nw")

# Encrypt it with LUKS
sudo cryptsetup --verbose --verify-passphrase luksFormat ${usb}3

# Open the encrypted container
sudo cryptsetup luksOpen ${usb}3 my_usb

# Format the opened container
sudo mkfs.ext4 -L persistence /dev/mapper/my_usb

# Mount and configure
sudo mkdir -pv /mnt/my_usb
sudo mount /dev/mapper/my_usb /mnt/my_usb
echo "/ union" | sudo tee /mnt/my_usb/persistence.conf
sudo umount /dev/mapper/my_usb
sudo cryptsetup luksClose /dev/mapper/my_usb
```

At boot, select **"Live USB Encrypted Persistence"** and enter your LUKS passphrase.

---

## Verifying a USB Write

Source: https://www.kali.org/docs/usb/verifying-usb/

After writing, verify the ISO was written correctly:

```bash
# Get the ISO size in bytes
isosize=$(wc -c < kali-linux-2025.4-live-amd64.iso)

# Hash the ISO file
sha256sum kali-linux-2025.4-live-amd64.iso

# Hash the same number of bytes from the USB device
sudo dd if=/dev/sdX bs=512 count=$((isosize/512)) | sha256sum
```

The hashes should match if the write was successful.
