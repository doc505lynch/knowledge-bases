# Kali Linux — Windows Subsystem for Linux (WSL)

Source: https://www.kali.org/docs/wsl/

---

## Available Guides

- Kali WSL setup: https://www.kali.org/docs/wsl/wsl-preparations/
- Win-KeX (main GUI): https://www.kali.org/docs/wsl/win-kex/
- Win-KeX Enhanced Session Mode: https://www.kali.org/docs/wsl/win-kex-esm/
- Win-KeX Seamless Mode: https://www.kali.org/docs/wsl/win-kex-sl/
- Win-KeX Window Mode: https://www.kali.org/docs/wsl/win-kex-win/

---

## Overview

**WSL 2 is the preferred and default option** when installing WSL. WSL 2 uses an actual Linux kernel within Hyper-V, whereas WSL 1 relies on a system call translation layer. WSL 2 offers much better compatibility with Linux software.

---

## System Requirements

| Version | OS | Minimum Build |
|---------|----|--------------|
| WSL 1 | Windows 10 | Build 16215 |
| WSL 2 (x64) | Windows 10 | Build 18362.1049 |
| WSL 2 (ARM64) | Windows 10 | Build 19041 |
| WSL 2 | Windows 11 | Any build (recommended) |

Check your Windows build: Press `Win+R`, type `winver`.

---

## Installation on Windows 11 (Simplest Method)

Open PowerShell or Command Prompt as Administrator:

```powershell
wsl --install --distribution kali-linux
```

This single command installs WSL 2 with Kali Linux. Restart when prompted.

---

## Installation on Windows 10

### Step 1: Enable Required Windows Features

Open an Administrator Command Prompt:

```cmd
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all
```

### Step 2: Restart Windows

### Step 3: Install WSL 2 Linux Kernel Update

Download and install from: https://aka.ms/wsl2kernel

### Step 4: Restart Again

### Step 5: Set WSL 2 as Default

```powershell
wsl --set-default-version 2
```

### Step 6: Install Kali Linux

**Option A — Microsoft Store:**
Search for "Kali Linux" in the Microsoft Store and click Install.

**Option B — PowerShell:**

```powershell
Invoke-WebRequest -Uri https://aka.ms/wsl-kali-linux-new -OutFile .\kali-linux.AppxBundle -UseBasicParsing
Add-AppxPackage .\kali-linux.AppxBundle
```

**Option C — Manual Rootfs Import:**

```powershell
wsl --import kali-wsl wsl-test .\kali-linux-rolling-wsl-rootfs-amd64.tar.gz
```

---

## First Run

Launch Kali WSL from:
- Start Menu shortcut
- Command: `kali`
- Command: `wsl --distribution kali-linux`

On first launch, you will be prompted to create a Unix user account (username and password).

---

## Installing Tools

The WSL installation is minimal. Install the tools you need:

```bash
# Update package lists
sudo apt update

# Install headless toolset (no GUI tools)
sudo apt install -y kali-linux-headless

# Or install the full default metapackage (large download)
sudo apt install -y kali-linux-default
```

---

## Win-KeX — Kali Desktop on Windows

Win-KeX provides a full Kali Linux desktop experience within Windows.

### Install Win-KeX

Inside the Kali WSL terminal:

```bash
sudo apt update
sudo apt install -y kali-win-kex
```

### Start Win-KeX (Window Mode)

```bash
kex --win -s
```

### Start Win-KeX (Seamless Mode — Kali apps appear alongside Windows apps)

```bash
kex --sl -s
```

### Start Win-KeX (Enhanced Session Mode — Full desktop in RDP window)

```bash
kex --esm --ip -s
```

### Stop Win-KeX

```bash
kex stop
```

---

## Troubleshooting WSL

Before seeking support, document:
- System architecture (x64 or ARM64)
- Windows edition and OS build number (`winver`)
- Current and desired WSL version
- Whether virtualization is enabled in BIOS/UEFI
- Whether the `VirtualMachinePlatform` feature is installed
- Any error messages encountered

### Check WSL Version

```powershell
wsl --list --verbose
```

### Convert WSL 1 to WSL 2

```powershell
wsl --set-version kali-linux 2
```

### Update WSL

```powershell
wsl --update
```

### Reset/Unregister a Distribution

```powershell
wsl --unregister kali-linux
```
