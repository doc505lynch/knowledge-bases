# Kali Linux — Containers (Docker, Podman, LXD)

Source: https://www.kali.org/docs/containers/

---

## Available Guides

- Installing Docker on Kali: https://www.kali.org/docs/containers/installing-docker-on-kali/
- Official Kali Docker Images: https://www.kali.org/docs/containers/official-kalilinux-docker-images/
- Using Kali Docker Images: https://www.kali.org/docs/containers/using-kali-docker-images/
- Using Kali Podman Images: https://www.kali.org/docs/containers/using-kali-podman-images/
- Kali Linux LXC/LXD Images: https://www.kali.org/docs/containers/kalilinux-lxc-images/

---

## Installing Docker on Kali Linux

Source: https://www.kali.org/docs/containers/installing-docker-on-kali/

### Method 1: Quick Install via docker.io (Recommended for Most Users)

Kali already has a package named `docker`, so the container platform is available as `docker.io`:

```bash
sudo apt update
sudo apt install -y docker.io
sudo systemctl enable docker --now
```

Verify the install:

```bash
docker version
docker info
```

### Optional: Run Docker Without sudo

```bash
sudo usermod -aG docker $USER
```

**Important:** You must log out and back in for group membership to take effect. After re-login, run `docker` without `sudo`.

### Method 2: Install docker-ce from Docker's Official Repository

Kali Linux is based on Debian. Use the Debian repository. As of December 2025, the Debian stable release is **trixie**.

**Step 1: Import the Docker GPG key:**

```bash
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

**Step 2: Add Docker's repository:**

```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian trixie stable" | sudo tee /etc/apt/sources.list.d/docker.list
```

**Step 3: Install docker-ce:**

```bash
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io
```

---

## Official Kali Linux Docker Images

Source: https://www.kali.org/docs/containers/official-kalilinux-docker-images/

All images are available on Docker Hub at `docker.io/kalilinux/` and are updated weekly.

### Available Images

| Image | Branch | Description |
|-------|--------|-------------|
| `kalilinux/kali-rolling` | kali-rolling | **Recommended.** Continuously updated main image |
| `kalilinux/kali-last-release` | kali-last-snapshot | Updated only at new quarterly releases |
| `kalilinux/kali-bleeding-edge` | kali-bleeding-edge | Includes experimental/bleeding-edge repository |
| `kalilinux/kali-experimental` | kali-experimental | Not-yet-ready packages for testing |
| `kalilinux/kali-dev` | kali-dev | For rebuilding Kali packages |

### Important: No Default Metapackage

**None of the images include the default metapackage.** After starting a container, install tools:

```bash
apt update && apt -y install kali-linux-headless
```

### Source / CI

The images are built via GitLab CI. Source project: https://gitlab.com/kalilinux/build-scripts/kali-docker/

---

## Using Kali Linux Docker Images

Source: https://www.kali.org/docs/containers/using-kali-docker-images/

### Pull the Image

```bash
docker pull docker.io/kalilinux/kali-rolling
```

### Run an Interactive Container

```bash
docker run --tty --interactive kalilinux/kali-rolling
```

**Limitation:** Docker containers started this way do not support `systemd`, so `systemctl` commands will not work.

### Install Tools Inside the Container

```bash
apt update && apt -y install kali-linux-headless
```

### Resume an Exited Container

List all containers (including stopped ones):

```bash
docker container list --all
```

Restart a stopped container by ID:

```bash
docker start <CONTAINER_ID>
```

Reconnect to the running container:

```bash
docker attach <CONTAINER_ID>
```

Press **Enter** once after attaching to get a fully displayed prompt.

The container resumes in whatever state you left it after the initial `docker run` or the last `docker start` + `docker attach`.

### Remove a Container

```bash
docker rm <CONTAINER_ID>
```

### Common Docker Commands Reference

```bash
docker images                          # List downloaded images
docker ps                              # List running containers
docker ps -a                           # List all containers (including stopped)
docker stop <CONTAINER_ID>             # Stop a running container
docker rm <CONTAINER_ID>               # Remove a container
docker rmi kalilinux/kali-rolling      # Remove an image
docker logs <CONTAINER_ID>             # View container logs
```

### Running with Shared Volume (Persistent Files)

```bash
docker run --tty --interactive \
  --volume /path/on/host:/mnt/shared \
  kalilinux/kali-rolling
```

### Running with Network Host Mode (Full Network Access)

```bash
docker run --tty --interactive \
  --network host \
  kalilinux/kali-rolling
```

### Running with Privileged Mode (for tools needing raw sockets)

```bash
docker run --tty --interactive \
  --privileged \
  kalilinux/kali-rolling
```

---

## Kali Linux LXC/LXD Images

Source: https://www.kali.org/docs/containers/kalilinux-lxc-images/

LXC/LXD provides system containers (more like VMs than Docker containers) with full init system support including `systemd`.

### Install LXD

```bash
sudo apt install -y lxd
sudo lxd init
```

### Launch a Kali Container

```bash
lxc launch images:kali/current/amd64 kali-container
lxc exec kali-container -- /bin/bash
```

### List Containers

```bash
lxc list
```

---

## Using Kali Linux Podman Images

Source: https://www.kali.org/docs/containers/using-kali-podman-images/

Podman is a daemonless container engine compatible with Docker commands. It can run containers as a non-root user.

### Install Podman

```bash
sudo apt install -y podman
```

### Pull and Run Kali Image

```bash
podman pull docker.io/kalilinux/kali-rolling
podman run --tty --interactive kalilinux/kali-rolling
```

Podman commands are generally interchangeable with Docker commands.
