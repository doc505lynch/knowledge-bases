# Kali Linux — Cloud Deployments

Source: https://www.kali.org/docs/cloud/

---

## Supported Cloud Platforms

| Platform | Documentation URL |
|----------|------------------|
| AWS (Amazon Web Services) | https://www.kali.org/docs/cloud/aws/ |
| Azure (Microsoft) | https://www.kali.org/docs/cloud/azure/ |
| Digital Ocean | https://www.kali.org/docs/cloud/digitalocean/ |
| Linode | https://www.kali.org/docs/cloud/linode/ |

---

## AWS (Amazon Web Services)

Source: https://www.kali.org/docs/cloud/aws/
Last updated: February 2023

### Step-by-Step Deployment

1. **Create an AWS Account** at https://aws.amazon.com/

2. **Navigate to EC2:**
   - Services > Compute > EC2

3. **Access the AMI Catalog:**
   - In the EC2 left sidebar, click "AMI Catalog"

4. **Find the Official Kali Image:**
   - Click "AWS Marketplace AMIs"
   - Search for `kali`
   - Select the **official Kali Linux image**

5. **Configure Instance Settings:**
   - Review usage details — SSH access uses the `kali` user account
   - Select your preferred instance type (t2.micro eligible for free tier)

6. **Create a Key Pair:**
   - Generate a new `.pem` key pair for secure SSH access
   - Save the key file — you cannot retrieve it again

7. **Configure Storage:**
   - Change storage type to "standard" to minimize costs

8. **Launch the Instance**

### Connect via SSH

```bash
ssh -i "keys.pem" kali@<INSTANCE_IP>
```

Replace `<INSTANCE_IP>` with your EC2 instance's public IP or DNS.

### Post-Connection Setup

**Change the default password:**

```bash
sudo passwd kali
```

**Install default tools:**

```bash
sudo apt update && sudo apt install -y kali-linux-headless
```

**Install full GUI toolset (larger download):**

```bash
sudo apt install -y kali-linux-default
```

### Set Up GUI with RDP

For a graphical interface via RDP with Xfce:

```bash
# Install Xfce and RDP server
sudo apt install -y kali-desktop-xfce xrdp

# Start xrdp
sudo systemctl enable xrdp --now

# Create SSH tunnel for RDP (from local machine)
ssh -i "keys.pem" -L 3390:localhost:3389 kali@<INSTANCE_IP>
```

Then connect from Windows Remote Desktop to `localhost:3390`.

### NVIDIA GPU Support on AWS (GPU Instances)

```bash
sudo apt update && sudo apt -y full-upgrade
sudo apt install -y linux-headers-$(uname -r)
sudo apt install -y nvidia-driver nvidia-cuda-toolkit
sudo reboot
```

---

## Azure (Microsoft Azure)

Source: https://www.kali.org/docs/cloud/azure/

Kali's Azure availability was restored with version 2022.3.

### Step-by-Step Deployment

1. **Create an Azure Account** at https://portal.azure.com/

2. **Navigate to Virtual Machines:**
   - Portal > Create a resource > Virtual Machine

3. **Create the VM:**
   - Click "Create" > "Azure virtual machine"

4. **Configure the Resource:**
   - Create or select a Resource Group
   - Search for and select the Kali Linux image from the marketplace
   - Set a custom username and generate or import a key pair

5. **Set Up Storage:**
   - Create and attach a new disk (no pre-existing disk is needed)
   - Default disk values are acceptable

6. **Review and Deploy:**
   - Review all configuration settings
   - Click "Create" to initiate deployment

7. **Access Your Instance:**
   - Once deployed, click "Go to resource"
   - Click "Connect" > "SSH" for connection instructions

8. **Connect via SSH:**

```bash
# Fix key permissions first
chmod 400 your-key.pem

ssh -i "your-key.pem" <username>@<PUBLIC_IP>
```

### Post-Connection Setup (Azure)

```bash
sudo apt update && sudo apt install -y kali-linux-headless
```

---

## Digital Ocean

Source: https://www.kali.org/docs/cloud/digitalocean/

Kali Linux is available as a 1-Click App / Marketplace image on Digital Ocean.

### Deploy from Marketplace

1. Log into your Digital Ocean account
2. Click "Create" > "Droplets"
3. Choose "Marketplace" tab
4. Search for "Kali"
5. Select your Droplet size (minimum 2 GB RAM recommended)
6. Choose a datacenter region
7. Add your SSH key
8. Click "Create Droplet"

### Connect

```bash
ssh root@<DROPLET_IP>
```

---

## Linode (Akamai Cloud)

Source: https://www.kali.org/docs/cloud/linode/

### Deploy Kali on Linode

1. Log into https://cloud.linode.com/
2. Click "Create" > "Linode"
3. Choose "Marketplace" and search for Kali Linux
4. Select Linode plan (minimum Nanode 1GB for headless, 2GB+ for desktop)
5. Choose a region
6. Set root password or add SSH key
7. Click "Create Linode"

### Connect

```bash
ssh root@<LINODE_IP>
```

---

## General Cloud Notes

- Cloud Kali instances are minimal by default — install the tools you need
- Use `kali-linux-headless` for command-line tools only
- Use `kali-linux-default` for the full desktop environment
- Always update immediately after first boot: `sudo apt update && sudo apt dist-upgrade -y`
- Consider security groups / firewall rules to restrict SSH access by IP
