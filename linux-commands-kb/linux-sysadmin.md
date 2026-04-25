# Linux System Administration Command Reference

A comprehensive reference for Linux sysadmin commands, flags, and patterns. Each section includes syntax, key flags, real-world examples, and expert tips.

---

## Table of Contents

1. [Process Management](#1-process-management)
2. [systemd and Services](#2-systemd-and-services)
3. [Users and Groups](#3-users-and-groups)
4. [Scheduling](#4-scheduling)
5. [Logging](#5-logging)
6. [Memory and Performance](#6-memory-and-performance)
7. [Boot and Init](#7-boot-and-init)
8. [Environment](#8-environment)
9. [Package Management](#9-package-management)

---

## 1. Process Management

### `ps` — Process Snapshot

**Syntax:** `ps [options]`

`ps` reads the `/proc` filesystem to snapshot process state at the moment of invocation. Two flag styles exist: BSD (no dash) and POSIX (with dash) — they are **not** interchangeable.

**Key flags:**

| Flag | Meaning |
|------|---------|
| `aux` | All processes, user-oriented format (BSD) |
| `-ef` | All processes, full format (POSIX) |
| `--forest` | ASCII art process tree |
| `-o` | Custom output columns |
| `-p <pid>` | Show only this PID |
| `-u <user>` | Filter by user |
| `--sort` | Sort output (prefix `-` for descending) |

**Examples:**

```bash
# Standard wide listing — user, PID, %CPU, %MEM, command
ps aux

# Full POSIX format — includes PPID, nice value, start time
ps -ef

# Show process tree — visualize parent-child relationships
ps auxf
ps -ef --forest

# Custom output: PID, user, nice value, %mem, elapsed time, command
ps -eo pid,user,ni,%mem,etime,cmd --sort=-%mem | head -20

# Show all threads for a specific process
ps -Lp 1234 -o pid,tid,pcpu,comm

# Find processes owned by www-data consuming CPU
ps -u www-data --sort=-%cpu -o pid,%cpu,%mem,cmd
```

**Expert tips:**
- `ps aux` vs `ps -ef`: `aux` adds `%CPU`, `%MEM`, `VSZ`, `RSS`; `-ef` adds `PPID` and `STIME`. Combine as `ps axo pid,ppid,user,%cpu,%mem,vsz,rss,stat,start,cmd` for the best of both.
- `VSZ` is virtual memory (includes shared libs, mmap). `RSS` is resident set size (actual RAM in use). High VSZ with low RSS is normal for JVM/Node processes.
- `STAT` column codes: `R`=running, `S`=sleeping, `D`=uninterruptible sleep (usually I/O), `Z`=zombie, `T`=stopped, `+`=foreground, `<`=high priority, `N`=low priority.

---

### `top` — Live Process Monitor

**Syntax:** `top [options]`

**Key flags:**

| Flag | Meaning |
|------|---------|
| `-d <sec>` | Refresh interval (default 3s) |
| `-p <pid>` | Monitor specific PID(s) |
| `-u <user>` | Filter by user |
| `-b -n <N>` | Batch mode, N iterations (for scripting) |
| `-H` | Show threads instead of processes |

**Interactive keys:**

| Key | Action |
|-----|--------|
| `k` | Kill a process (prompts for PID then signal) |
| `r` | Renice a process |
| `M` | Sort by memory |
| `P` | Sort by CPU |
| `T` | Sort by time |
| `u` | Filter by username |
| `f` | Field management — add/remove columns |
| `d` | Change delay interval |
| `1` | Toggle per-CPU display |
| `H` | Toggle threads/tasks view |
| `W` | Write config to `~/.toprc` |
| `q` | Quit |
| `c` | Toggle full command path |
| `i` | Hide idle processes |

**Examples:**

```bash
# Monitor two PIDs with 1 second refresh
top -d 1 -p 1234,5678

# Capture 5 snapshots in batch mode for logging
top -b -n 5 -d 2 > /tmp/top-snapshot.txt

# Show threads for a specific process
top -H -p $(pgrep nginx | head -1)

# One-shot top output filtered to a user
top -b -n 1 -u postgres
```

**Expert tips:**
- Press `W` in interactive mode to persist your column layout to `~/.toprc` so it survives reboots.
- The `load average` line shows 1/5/15-minute averages. On a 4-core machine, a sustained load above 4.0 means the CPU is saturated.
- `us` = user space, `sy` = kernel, `wa` = I/O wait. High `wa` means your bottleneck is disk or network, not CPU.

---

### `htop` — Interactive Process Viewer

**Syntax:** `htop [options]`

`htop` is a full-screen ncurses process monitor with color, mouse support, and easier sorting than `top`.

**Key flags:**

| Flag | Meaning |
|------|---------|
| `-u <user>` | Filter by user |
| `-p <pid>[,pid]` | Monitor specific PIDs |
| `-d <tenths>` | Delay in tenths of a second |
| `--tree` | Start in tree view |

**Interactive keys:**

| Key | Action |
|-----|--------|
| `F2` | Setup/configure columns and meters |
| `F3` or `/` | Search |
| `F4` | Filter processes |
| `F5` | Toggle tree view |
| `F6` | Sort column selector |
| `F9` | Kill menu (choose signal) |
| `F10` | Quit |
| `Space` | Tag/untag a process |
| `u` | Filter by user |
| `H` | Toggle user/kernel threads |
| `I` | Invert sort order |

**Examples:**

```bash
# Start in tree mode filtering to root processes
htop --tree -u root

# Monitor a specific application by PID
htop -p $(pgrep -d',' postgres)
```

**Expert tips:**
- `htop` shows CPU meters per core at the top — immediately reveals if load is pinned on one core (single-threaded bottleneck) vs spread across all cores.
- Press `F2` → Columns to add `PPID`, `NLWP` (thread count), `IO_RATE` for deeper insight.
- On systems without `htop`, `top` + `1` + `P` gives comparable info.

---

### `kill`, `killall`, `pkill` — Sending Signals

**Syntax:**
```
kill [-signal] <pid>
killall [-signal] <name>
pkill [-signal] [-u user] <pattern>
```

**Common signals:**

| Signal | Number | Meaning |
|--------|--------|---------|
| `SIGTERM` | 15 | Graceful termination (default) |
| `SIGKILL` | 9 | Unconditional kill (cannot be caught) |
| `SIGHUP` | 1 | Hangup / reload config |
| `SIGINT` | 2 | Interrupt (Ctrl+C) |
| `SIGSTOP` | 19 | Pause process |
| `SIGCONT` | 18 | Resume stopped process |
| `SIGUSR1` | 10 | User-defined signal 1 |

**Examples:**

```bash
# Graceful stop, then force kill if needed
kill 4321
sleep 5
kill -9 4321

# Reload nginx config without restart
kill -HUP $(cat /var/run/nginx.pid)

# Kill all processes named "python3"
killall python3

# Kill all processes owned by a specific user
killall -u baduser

# Kill by pattern, case-insensitive
pkill -i -f "gunicorn.*myapp"

# Send SIGUSR1 to logrotate a running process
pkill -USR1 apache2
```

**Expert tips:**
- Never reach for `-9` first. `SIGTERM` allows the process to flush buffers, close DB connections, and clean up temp files. Use `-9` only after `SIGTERM` fails.
- `kill -0 <pid>` tests whether a PID exists and you have permission to signal it — useful in scripts without actually sending a signal.
- `killall -w` waits for all matching processes to die before returning — useful in shutdown scripts.

---

### `pgrep` — Find Process by Name

**Syntax:** `pgrep [options] <pattern>`

**Key flags:**

| Flag | Meaning |
|------|---------|
| `-l` | List PID and process name |
| `-a` | List PID and full command line |
| `-u <user>` | Match only this user's processes |
| `-x` | Exact match (full name, not substring) |
| `-f` | Match against full command line |
| `-d <delim>` | Output delimiter (default newline) |
| `-n` | Newest matching process |
| `-o` | Oldest matching process |

**Examples:**

```bash
# Find all nginx worker PIDs
pgrep -a nginx

# Get comma-separated PIDs for htop
htop -p $(pgrep -d',' gunicorn)

# Reload all apache workers
kill -USR1 $(pgrep -x apache2)

# Check if a service is running in a script
if pgrep -x "mysqld" > /dev/null; then
    echo "MySQL is running"
fi
```

---

### `nice` and `renice` — Process Priority

**Syntax:**
```
nice -n <value> <command>
renice -n <value> [-p pid] [-u user] [-g group]
```

Nice values range from **-20** (highest priority) to **+19** (lowest priority). Default is 0. Only root can set negative (higher priority) values.

**Examples:**

```bash
# Run a backup at lowest priority
nice -n 19 tar czf /backup/home.tar.gz /home

# Run a database import with slightly elevated priority
sudo nice -n -5 pg_restore -d mydb dump.sql

# Lower priority of a running process
renice -n 15 -p 8765

# Lower priority of all processes owned by a user
renice -n 10 -u reportuser

# Raise priority of critical process (root only)
sudo renice -n -10 -p $(pgrep -x "critical-app")
```

**Expert tips:**
- `ionice` is the I/O equivalent of `nice`. `ionice -c 3 -p <pid>` sets idle I/O class — the process only gets disk access when nothing else needs it.
- Check current nice value: `ps -o pid,ni,cmd -p <pid>` or look at the `NI` column in `top`.

---

### `nohup`, `disown`, `jobs`, `fg`, `bg` — Job Control

**`nohup`** — Run a command immune to SIGHUP (survives terminal close):

```bash
# Output goes to nohup.out by default
nohup python3 server.py &

# Redirect output explicitly
nohup python3 server.py > /var/log/server.log 2>&1 &

# Capture the PID
nohup ./long-script.sh > /tmp/out.log 2>&1 &
echo $!
```

**`&`** — Run in background:

```bash
# Start job in background, get PID
./compile.sh &
PID=$!

# Run multiple in parallel and wait for all
./task1.sh & ./task2.sh & ./task3.sh &
wait
echo "All tasks done"
```

**`jobs`, `fg`, `bg`** — Manage shell jobs:

```bash
# List all background jobs in current shell
jobs -l          # -l includes PID

# Suspend running process: Ctrl+Z, then background it
# (Ctrl+Z suspends with SIGSTOP)
bg %1            # resume job 1 in background

# Bring job 2 back to foreground
fg %2

# Send a specific job to background
sleep 100 &      # starts in background
jobs             # shows [1]+ Running sleep 100
```

**`disown`** — Detach a job from the shell (won't receive SIGHUP):

```bash
# Disown the most recent background job
./long-running.sh &
disown

# Disown a specific job number
disown %2

# Disown all jobs
disown -a
```

**`wait`** — Wait for background jobs:

```bash
# Wait for all background jobs
./part1.sh &
./part2.sh &
wait
echo "Both done, exit codes accumulated"

# Wait for specific PID
./job.sh &
JOB_PID=$!
wait $JOB_PID
echo "Exit code: $?"
```

**Expert tips:**
- `nohup` + `&` vs `disown`: `nohup` redirects SIGHUP and stdout/stderr; `disown` just removes the job from the shell's job table. Use `nohup` when starting from scratch; use `disown` when you forgot to use `nohup`.
- `screen` or `tmux` are superior for interactive long-running sessions — they provide full terminal multiplexing.

---

### `pstree` — Visual Process Tree

**Syntax:** `pstree [options] [pid|user]`

**Key flags:**

| Flag | Meaning |
|------|---------|
| `-p` | Show PIDs |
| `-u` | Show username transitions |
| `-a` | Show command arguments |
| `-h` | Highlight current process and ancestors |
| `-n` | Sort numerically by PID |

**Examples:**

```bash
# Show full tree with PIDs
pstree -p

# Show tree for a specific process
pstree -p 1234

# Show only processes owned by postgres
pstree postgres

# Display with arguments
pstree -ap | head -40
```

---

### `lsof` — List Open Files

**Syntax:** `lsof [options]`

`lsof` lists all open file descriptors — files, sockets, pipes, devices.

**Key flags:**

| Flag | Meaning |
|------|---------|
| `-p <pid>` | Open files for this PID |
| `-u <user>` | Open files for this user |
| `-i [addr]` | Network connections (all or filtered) |
| `-i :<port>` | What is using this port |
| `+D <dir>` | All open files under this directory |
| `-t` | Terse output (PIDs only) — good for scripting |
| `-c <name>` | Files opened by processes matching name |
| `-n` | No hostname resolution (faster) |
| `-P` | No port name resolution |

**Examples:**

```bash
# What process is using port 80?
lsof -i :80
lsof -i :80 -n -P        # faster, no DNS/port lookups

# All network connections for a process
lsof -p 4321 -i

# What files does nginx have open?
lsof -c nginx

# Find what is holding a file open (can't unmount?)
lsof /mnt/usb

# List all open files under /var/log
lsof +D /var/log

# Kill all processes with files open in a directory
kill $(lsof -t +D /path/to/dir)

# Show all listening TCP sockets
lsof -i TCP -s TCP:LISTEN -n -P
```

**Expert tips:**
- `lsof -i :PORT` is the quickest way to find what is occupying a port, faster to type than `ss -tlnp | grep PORT`.
- `FD` column values: `cwd`=current working dir, `txt`=executable, `mem`=memory-mapped, numbers like `3u`=file descriptor 3 opened read/write.
- On a system with `inotify` watch limits, `lsof | grep inotify | wc -l` counts active watchers.

---

## 2. systemd and Services

### `systemctl` — Service and Unit Management

**Syntax:** `systemctl [options] <command> [unit]`

**Service lifecycle:**

```bash
# Start, stop, restart a service
systemctl start nginx
systemctl stop nginx
systemctl restart nginx

# Reload config without full restart (if supported)
systemctl reload nginx

# Restart only if already running
systemctl try-restart nginx

# Enable at boot, disable at boot
systemctl enable nginx
systemctl disable nginx

# Enable AND start immediately (one step)
systemctl enable --now nginx

# Mask (completely prevent start, even manually)
systemctl mask bluetooth
systemctl unmask bluetooth

# Check status
systemctl status nginx
systemctl is-active nginx     # returns exit 0 if active
systemctl is-enabled nginx    # returns exit 0 if enabled
systemctl is-failed nginx
```

**Unit inspection:**

```bash
# List all active units
systemctl list-units

# List only failed units
systemctl list-units --state=failed

# List all service unit files and their enable state
systemctl list-unit-files --type=service

# Show all properties of a unit
systemctl show nginx

# Show specific property
systemctl show nginx --property=MainPID

# Cat the unit file
systemctl cat nginx

# Show unit file location
systemctl status nginx | grep Loaded
```

**System control:**

```bash
# Reload systemd after editing a unit file
systemctl daemon-reload

# Power off, reboot, halt
systemctl poweroff
systemctl reboot
systemctl halt

# Switch targets (runlevels)
systemctl isolate multi-user.target
systemctl isolate graphical.target

# Set default boot target
systemctl set-default multi-user.target
systemctl get-default
```

**Expert tips:**
- After editing a unit file in `/etc/systemd/system/`, always run `systemctl daemon-reload` before `restart`. Without it, systemd uses the old in-memory unit definition.
- `systemctl edit nginx` opens a drop-in override editor — changes go to `/etc/systemd/system/nginx.service.d/override.conf` and survive package upgrades. Use instead of editing `/lib/systemd/system/` directly.
- `systemctl mask` writes a symlink to `/dev/null` — it cannot be started by anything, including dependencies. Use for services you never want to run (e.g., `avahi-daemon`).

---

### `journalctl` — Query the systemd Journal

**Syntax:** `journalctl [options]`

**Key flags:**

| Flag | Meaning |
|------|---------|
| `-u <unit>` | Logs for a specific unit |
| `-f` | Follow (tail -f equivalent) |
| `-n <N>` | Last N lines |
| `-r` | Reverse chronological |
| `-p <level>` | Filter by priority (0=emerg to 7=debug) |
| `--since "str"` | Start time (e.g., "2024-01-15 10:00") |
| `--until "str"` | End time |
| `--no-pager` | Print directly, no pager |
| `-xe` | Jump to end, show context for errors |
| `-b` | This boot only |
| `-b -1` | Previous boot |
| `-k` | Kernel messages only (like dmesg) |
| `--disk-usage` | Show journal disk usage |
| `--vacuum-size=500M` | Remove old logs until under 500M |

**Examples:**

```bash
# Follow nginx logs live
journalctl -u nginx -f

# Last 50 lines for a service, no pager
journalctl -u postgresql -n 50 --no-pager

# Errors and above for a service
journalctl -u myapp -p err

# All logs since midnight today
journalctl --since "today"

# Time range for debugging an incident
journalctl --since "2024-03-15 14:00" --until "2024-03-15 15:30"

# Follow multiple units simultaneously
journalctl -f -u nginx -u php-fpm

# Investigate a failed service (shows recent context + error)
systemctl status myapp   # check status first
journalctl -xe -u myapp  # detailed error context

# See logs from last boot
journalctl -b

# Compare current boot to previous
journalctl -b 0   # current
journalctl -b -1  # previous boot

# Kernel ring buffer via journal
journalctl -k -f

# Output as JSON for log shipping
journalctl -u nginx -n 100 -o json-pretty

# Free up disk space
journalctl --vacuum-time=30d
journalctl --vacuum-size=1G
```

**Expert tips:**
- `journalctl -xe` is the first command to run when `systemctl start myapp` fails — `-x` adds catalog explanations, `-e` jumps to the end.
- Set persistent storage: `mkdir -p /var/log/journal && systemctl restart systemd-journald` — without this, logs are lost on reboot.
- `journalctl -p warning -b` is an excellent general health check after a reboot — shows all warnings and above from this boot.

---

### `service` vs `systemctl`

`service` is a compatibility shim that calls the appropriate init system (SysVinit scripts in `/etc/init.d/` or systemctl for systemd):

```bash
# These are equivalent on systemd systems
service nginx start
systemctl start nginx

# service can call SysVinit scripts that lack systemd units
service --status-all   # list all SysV services

# Use systemctl for full systemd features
# service cannot enable at boot, mask, show logs, etc.
```

**Rule:** Use `systemctl` on modern systems. `service` exists for backward compatibility only.

---

## 3. Users and Groups

### `useradd` / `usermod` / `userdel`

**`useradd`** — Create a new user:

```bash
# Basic user with home directory
useradd -m -s /bin/bash alice

# Full creation: home dir, shell, comment, groups
useradd -m -s /bin/bash -c "Alice Smith" -G sudo,docker alice

# System account (no home, no login shell, low UID)
useradd -r -s /usr/sbin/nologin appuser

# Set password immediately
useradd -m alice && echo "alice:SecurePass1!" | chpasswd

# Specify UID and GID
useradd -m -u 1500 -g 1500 alice
```

**Key `useradd` flags:**

| Flag | Meaning |
|------|---------|
| `-m` | Create home directory |
| `-s <shell>` | Login shell |
| `-c "comment"` | GECOS field (full name) |
| `-G <groups>` | Supplementary groups (comma-separated) |
| `-g <group>` | Primary group |
| `-u <uid>` | Specific UID |
| `-r` | System account |
| `-e <date>` | Account expiry (YYYY-MM-DD) |
| `-d <dir>` | Home directory path |

**`usermod`** — Modify existing user:

```bash
# Add to a supplementary group (APPEND — don't overwrite)
usermod -aG docker alice
usermod -aG sudo,docker alice

# Change login shell
usermod -s /bin/zsh alice

# Lock / unlock account
usermod -L alice    # lock (prepends ! to password hash)
usermod -U alice    # unlock

# Rename user (also update home dir and group)
usermod -l newname -d /home/newname -m oldname

# Set account expiry
usermod -e 2025-12-31 contractor
```

**`userdel`** — Delete user:

```bash
# Delete user but keep home directory
userdel alice

# Delete user AND home directory and mail spool
userdel -r alice

# Force delete even if user is logged in (dangerous)
userdel -f alice
```

---

### `groupadd` / `groupmod` / `groupdel`

```bash
# Create a group
groupadd developers
groupadd -g 2000 appgroup    # specific GID

# Rename a group
groupmod -n newname oldname

# Change GID
groupmod -g 2001 appgroup

# Delete a group
groupdel developers

# List members of a group
getent group docker
grep "^docker:" /etc/group
```

---

### `passwd` and `chpasswd`

```bash
# Change your own password
passwd

# Root changes another user's password
passwd alice

# Set password non-interactively (scripts)
echo "alice:NewPassword123" | chpasswd

# Bulk password change from file
chpasswd < passwords.txt   # file format: username:password

# Force password change on next login
passwd -e alice
chage -d 0 alice

# Lock/unlock password
passwd -l alice    # lock
passwd -u alice    # unlock

# Show password aging info
chage -l alice
```

---

### `su` and `sudo`

**`su`** — Switch user:

```bash
# Switch to root (full login environment)
su -

# Switch to another user
su - alice

# Run single command as another user
su -c "whoami" alice

# Switch without loading new environment (rare)
su alice    # without dash
```

**`sudo`** — Execute as another user (default: root):

```bash
# Run command as root
sudo apt update

# Run as specific user
sudo -u postgres psql

# Open root shell
sudo -i       # login shell (sets HOME, PATH)
sudo -s       # shell without login

# List what sudo allows you to do
sudo -l

# Preserve current environment
sudo -E env_sensitive_command

# Run command in background with sudo
sudo sh -c 'nohup myservice &'
```

**`visudo`** — Edit sudoers safely:

```bash
# Always use visudo — validates syntax before saving
sudo visudo

# Edit a drop-in file (preferred — survives OS upgrades)
sudo visudo -f /etc/sudoers.d/myapp
```

**Common sudoers patterns:**

```
# Full sudo without password
alice ALL=(ALL:ALL) NOPASSWD: ALL

# Specific commands only
deploy ALL=(ALL) NOPASSWD: /bin/systemctl restart myapp, /usr/bin/docker

# Group-based (% prefix)
%developers ALL=(ALL) /usr/bin/git, /usr/bin/docker

# Run as specific user only
dbadmin ALL=(postgres) /usr/bin/psql
```

---

### `id`, `whoami`, `who`, `w`, `last`, `lastlog`

```bash
# Current user's UID, GID, all groups
id
id alice    # another user's info

# Just the username
whoami

# Who is currently logged in (terminals)
who
who -b    # last system boot time
who am i  # your own session

# Detailed who: user, terminal, login time, CPU usage, current command
w

# Login history from /var/log/wtmp
last
last alice          # specific user
last -n 20          # last 20 entries
last reboot         # system reboots
last -F             # full dates

# Last login time for all users
lastlog
lastlog -u alice    # specific user
lastlog -t 7        # users who logged in last 7 days
```

---

### `/etc/passwd`, `/etc/shadow`, `/etc/group` Format

**`/etc/passwd`** (world-readable, no passwords):
```
username:x:UID:GID:GECOS:home_dir:shell
root:x:0:0:root:/root:/bin/bash
alice:x:1001:1001:Alice Smith:/home/alice:/bin/bash
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
```

Fields: `x` in password field means password is in `/etc/shadow`.

**`/etc/shadow`** (root-readable only):
```
username:hashed_pw:last_changed:min_days:max_days:warn_days:inactive_days:expire_date:reserved
alice:$6$salt$hash...:19500:0:99999:7:::
```
- `$6$` = SHA-512 hash. `$1$`=MD5, `$5$`=SHA-256.
- `last_changed` = days since Jan 1 1970.
- `!` or `*` in hash field = locked account.

**`/etc/group`**:
```
groupname:x:GID:member1,member2,member3
sudo:x:27:alice,bob
docker:x:998:alice
```

**Expert tips:**
- `getent passwd alice` queries NSS (works for LDAP/NIS users too, not just local `/etc/passwd`).
- Always use `usermod -aG` (capital A for append). Without `-a`, it **replaces** all supplementary groups — a common way to accidentally remove someone from `sudo`.
- System accounts typically have UID < 1000 (Debian/Ubuntu) or < 500 (RHEL). Check `/etc/login.defs` for `UID_MIN`.

---

## 4. Scheduling

### `cron` — Recurring Jobs

**Crontab syntax:**

```
┌─────────── minute (0-59)
│ ┌───────── hour (0-23)
│ │ ┌─────── day of month (1-31)
│ │ │ ┌───── month (1-12 or jan-dec)
│ │ │ │ ┌─── day of week (0-7, 0 and 7 = Sunday, or sun-sat)
│ │ │ │ │
* * * * * command
```

**Special strings:**

| String | Equivalent |
|--------|------------|
| `@reboot` | Once at startup |
| `@hourly` | `0 * * * *` |
| `@daily` | `0 0 * * *` |
| `@weekly` | `0 0 * * 0` |
| `@monthly` | `0 0 1 * *` |
| `@yearly` | `0 0 1 1 *` |

**`crontab` commands:**

```bash
# Edit your own crontab (uses $EDITOR)
crontab -e

# List your crontab
crontab -l

# Remove your crontab (with confirmation)
crontab -r

# Edit another user's crontab (root)
crontab -u alice -e
crontab -u alice -l
```

**Example entries:**

```bash
# Backup every day at 2:30 AM
30 2 * * * /usr/local/bin/backup.sh >> /var/log/backup.log 2>&1

# Run every 5 minutes
*/5 * * * * /usr/local/bin/healthcheck.sh

# Run at 8 AM Monday through Friday
0 8 * * 1-5 /usr/local/bin/morning-report.sh

# Run on the 1st and 15th of every month
0 0 1,15 * * /usr/local/bin/billing.sh

# Clear temp files every Sunday at midnight
0 0 * * 0 find /tmp -mtime +7 -delete

# Set PATH and env vars in crontab header
SHELL=/bin/bash
PATH=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin
MAILTO=admin@example.com
```

**System cron directories:**

```
/etc/crontab          — system crontab (has extra username field)
/etc/cron.d/          — drop-in files, same format as /etc/crontab
/etc/cron.daily/      — scripts run once daily (via run-parts)
/etc/cron.hourly/     — scripts run hourly
/etc/cron.weekly/     — scripts run weekly
/etc/cron.monthly/    — scripts run monthly
```

Format for `/etc/cron.d/` files (extra username field):
```
30 2 * * * root /usr/local/bin/system-backup.sh
```

**Expert tips:**
- Cron jobs run with a minimal environment. Always use absolute paths for commands AND in your scripts. Set `PATH=` at the top of the crontab.
- Redirect stdout AND stderr: `command >> /log 2>&1`. Without `2>&1`, errors disappear silently (or go to the mail spool).
- Set `MAILTO=""` in crontab to suppress all email output. Set `MAILTO=admin@host` to get error reports.
- To test a cron environment: `env -i HOME=/root SHELL=/bin/bash /bin/bash -l -c 'your command'`

---

### `at` — One-Time Scheduled Jobs

**Syntax:** `at <timespec>`

```bash
# Schedule a job interactively (Ctrl+D to end)
at 3:00 PM
at> /usr/local/bin/maintenance.sh
at> <Ctrl+D>

# Here-document style
at 02:30 tomorrow << 'EOF'
/usr/local/bin/backup.sh
EOF

# Various time formats
at now + 2 hours
at midnight
at noon tomorrow
at 3pm Friday
at 09:00 2024-12-25
at 10:00 AM Jul 25

# List pending jobs
atq

# Remove a pending job
atrm 3      # remove job #3

# Show what job 5 will run
at -c 5
```

**Expert tips:**
- `at` jobs inherit the current environment at submission time — less surprising than cron.
- Output is mailed to the user unless redirected: `at now + 1 hour << 'EOF'\n /script.sh > /log 2>&1\nEOF`
- `/etc/at.allow` and `/etc/at.deny` control who can use `at`.

---

### `anacron` — Runs Missed Cron Jobs

`anacron` handles jobs that should run daily/weekly/monthly even if the machine was off when cron would have triggered them. Configured in `/etc/anacrontab`:

```
# period  delay  job-identifier  command
1         5      cron.daily      run-parts --report /etc/cron.daily
7         10     cron.weekly     run-parts --report /etc/cron.weekly
@monthly  15     cron.monthly    run-parts --report /etc/cron.monthly
```

Fields: period in days, delay in minutes after boot, job ID (for `/var/spool/anacron/` timestamps), command.

```bash
# Test anacron (run jobs that are due now)
anacron -n

# Force run all jobs regardless of timestamps
anacron -f

# Check what's scheduled
cat /etc/anacrontab
ls /var/spool/anacron/
```

---

## 5. Logging

### `/var/log` Structure

| Path | Contents |
|------|---------|
| `/var/log/syslog` | General system messages (Debian/Ubuntu) |
| `/var/log/messages` | General system messages (RHEL/CentOS) |
| `/var/log/auth.log` | Authentication events (Debian) |
| `/var/log/secure` | Authentication events (RHEL) |
| `/var/log/kern.log` | Kernel messages |
| `/var/log/dmesg` | Kernel ring buffer at boot |
| `/var/log/apt/` | APT package manager logs |
| `/var/log/nginx/` | Nginx access and error logs |
| `/var/log/mysql/` | MySQL/MariaDB logs |
| `/var/log/mail.log` | Mail service logs |
| `/var/log/wtmp` | Login records (binary, read with `last`) |
| `/var/log/btmp` | Failed login attempts (binary, read with `lastb`) |
| `/var/log/lastlog` | Last login per user (binary, read with `lastlog`) |

---

### `rsyslog` — System Logging Daemon

Config file: `/etc/rsyslog.conf` and `/etc/rsyslog.d/*.conf`

**Facility.Severity pairs:**

Facilities: `kern`, `user`, `mail`, `daemon`, `auth`, `syslog`, `lpr`, `news`, `uucp`, `cron`, `local0`–`local7`

Severities (priority): `emerg(0)`, `alert(1)`, `crit(2)`, `err(3)`, `warning(4)`, `notice(5)`, `info(6)`, `debug(7)`

**Example rsyslog rules** (`/etc/rsyslog.d/50-custom.conf`):

```
# Log all auth messages to auth.log
auth,authpriv.*                 /var/log/auth.log

# Log all cron activity
cron.*                          /var/log/cron.log

# Errors from all facilities to a central error log
*.err                           /var/log/errors.log

# Forward everything to a remote syslog server
*.* @192.168.1.100:514          # UDP
*.* @@192.168.1.100:514         # TCP

# Drop noisy messages
:msg, contains, "spam pattern"  stop
```

```bash
# Restart rsyslog after config changes
systemctl restart rsyslog

# Validate config
rsyslogd -N1
```

---

### `logrotate` — Log Rotation

Config: `/etc/logrotate.conf` and `/etc/logrotate.d/`

**Example config** (`/etc/logrotate.d/myapp`):

```
/var/log/myapp/*.log {
    daily               # rotate daily
    rotate 14           # keep 14 rotated files
    compress            # gzip old logs
    delaycompress       # compress starting at rotation 2 (keeps latest uncompressed)
    missingok           # don't error if log file missing
    notifempty          # skip if log is empty
    create 0640 appuser adm   # permissions for new log file
    sharedscripts       # run postrotate once even if multiple files match
    postrotate
        /usr/bin/kill -HUP $(cat /var/run/myapp.pid 2>/dev/null) 2>/dev/null || true
    endscript
}
```

```bash
# Test rotation without actually rotating
logrotate -d /etc/logrotate.d/nginx

# Force rotation now (ignores time constraints)
logrotate -f /etc/logrotate.d/myapp

# Run all configured rotations
logrotate /etc/logrotate.conf

# Verbose output for debugging
logrotate -v /etc/logrotate.conf
```

---

### `dmesg` — Kernel Ring Buffer

```bash
# Show all kernel messages
dmesg

# Human-readable timestamps (requires kernel 3.5+)
dmesg -T

# Follow kernel messages live
dmesg -w

# Filter by level
dmesg --level err,warn
dmesg -l err,crit,alert,emerg

# Last 20 lines
dmesg | tail -20

# Filter for hardware errors
dmesg | grep -i "error\|fail\|warn"

# Clear the kernel ring buffer (root)
dmesg -C
```

---

### `logger` — Write to Syslog from Scripts

```bash
# Log a message to syslog
logger "Backup completed successfully"

# Specify facility and severity
logger -p local0.info "Application started"
logger -p user.err "Critical failure in payment module"

# Tag messages for filtering
logger -t myapp "User login: alice from 10.0.0.1"

# Log from a script with tag and PID
logger -t "$(basename $0)[$$]" "Starting maintenance task"

# Log stderr of a command to syslog
mycommand 2>&1 | logger -t mycommand
```

---

## 6. Memory and Performance

### `free` — Memory Overview

**Syntax:** `free [options]`

```bash
# Human-readable with units
free -h

# Show in megabytes / gigabytes
free -m
free -g

# Update every 2 seconds
free -h -s 2

# Show totals line
free -ht
```

**Output fields:**
- `total` — physical RAM installed
- `used` — RAM in use (total - free - buffers - cache)
- `free` — completely unused RAM
- `buff/cache` — kernel buffers + page cache (can be reclaimed)
- `available` — estimated RAM available for new processes without swapping

**Expert tip:** `available` is the number that matters, not `free`. Linux aggressively uses RAM for caching — `free` near 0 with high `available` is healthy, not a problem.

---

### `vmstat` — Virtual Memory Statistics

**Syntax:** `vmstat [options] [delay [count]]`

```bash
# Snapshot
vmstat

# Update every 2 seconds, 10 times
vmstat 2 10

# Show memory stats in megabytes
vmstat -S m

# Show disk I/O statistics
vmstat -d

# Show slab cache info
vmstat -m | head -20

# Show active/inactive memory
vmstat -a
```

**Key columns:**
- `r` — processes waiting for CPU (run queue length)
- `b` — processes in uninterruptible sleep (I/O blocked)
- `swpd` — virtual memory used (KB)
- `si/so` — swap in/out per second (non-zero = memory pressure)
- `bi/bo` — blocks in/out per second (disk reads/writes)
- `wa` — % CPU waiting for I/O
- `us/sy/id` — user/system/idle CPU %

**Expert tip:** If `b` > 0 persistently or `wa` > 20%, you have an I/O bottleneck. If `si`/`so` are non-zero, the system is swapping — add RAM or reduce memory consumption.

---

### `iostat` — I/O Statistics

**Syntax:** `iostat [options] [device] [interval [count]]`

From the `sysstat` package (`apt install sysstat`).

```bash
# Basic I/O stats
iostat

# Extended stats, human readable, every 2 seconds
iostat -xh 2

# Specific device, 5 times at 1-second intervals
iostat -x /dev/sda 1 5

# Show CPU utilization alongside I/O
iostat -c 2
```

**Key `-x` columns:**
- `%util` — % of time device was busy (near 100% = saturated)
- `await` — average I/O wait time in ms
- `r/s, w/s` — reads/writes per second
- `rkB/s, wkB/s` — KB read/written per second
- `avgqu-sz` — average queue length (> 1 = queueing)

---

### `sar` — System Activity Reporter

**Syntax:** `sar [options] [interval [count]]`

Collects historical data via the `sysstat` service. Data stored in `/var/log/sysstat/`.

```bash
# CPU usage every 2 seconds, 5 times
sar 2 5

# Historical CPU data for today
sar -f /var/log/sysstat/sa$(date +%d)

# Memory stats
sar -r 2 5

# Network I/O
sar -n DEV 2 5

# Disk I/O
sar -b 2 5

# Load averages
sar -q 2 5

# Everything from yesterday's 2 PM to 3 PM
sar -s 14:00:00 -e 15:00:00 -f /var/log/sysstat/sa$(date -d yesterday +%d)
```

**Enable sysstat collection:**
```bash
# Enable sysstat service
systemctl enable --now sysstat

# Or edit /etc/default/sysstat
# Set ENABLED="true"
```

---

### `mpstat` — Per-CPU Statistics

```bash
# All CPUs, every 2 seconds
mpstat -P ALL 2

# Single CPU core
mpstat -P 0 2 5

# Show interrupts per CPU
mpstat -I ALL 2
```

---

### `uptime`

```bash
uptime
# Output: 14:22:33 up 42 days, 3:17, 2 users, load average: 0.52, 0.48, 0.45

# Just the load average
cat /proc/loadavg
```

---

### `/proc/meminfo` and `/proc/cpuinfo`

```bash
# Memory details
cat /proc/meminfo
grep -E "MemTotal|MemFree|MemAvailable|SwapTotal|SwapFree|Cached|Buffers" /proc/meminfo

# CPU details
cat /proc/cpuinfo
# Count physical cores
grep "cpu cores" /proc/cpuinfo | sort -u
# Count logical CPUs (including hyperthreading)
nproc
grep -c "^processor" /proc/cpuinfo

# Huge pages
grep Huge /proc/meminfo
```

---

### `swapoff` / `swapon`

```bash
# Show swap usage
swapon --show
free -h

# Disable all swap
swapoff -a

# Enable all swap defined in /etc/fstab
swapon -a

# Add a swap file
fallocate -l 2G /swapfile
chmod 600 /swapfile
mkswap /swapfile
swapon /swapfile

# Make persistent in /etc/fstab
echo '/swapfile none swap sw 0 0' >> /etc/fstab

# Adjust swappiness (0-100, lower = prefer RAM)
sysctl vm.swappiness=10
echo 'vm.swappiness=10' >> /etc/sysctl.d/99-swappiness.conf
```

---

## 7. Boot and Init

### GRUB — Bootloader

**Config files:**
- `/etc/default/grub` — user-facing settings
- `/etc/grub.d/` — script fragments that build the final config
- `/boot/grub/grub.cfg` — generated config (DO NOT edit directly)

**`/etc/default/grub` key settings:**

```bash
GRUB_DEFAULT=0                        # default boot entry (0-indexed or "saved")
GRUB_TIMEOUT=5                        # seconds to show menu
GRUB_TIMEOUT_STYLE=menu               # menu|countdown|hidden
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"    # appended for normal boots
GRUB_CMDLINE_LINUX="net.ifnames=0"    # appended for ALL boots (incl. recovery)
GRUB_DISABLE_RECOVERY=true            # hide recovery entries
GRUB_SAVEDEFAULT=true                 # remember last choice
```

**Update GRUB after config changes:**

```bash
# Debian/Ubuntu
update-grub
# or equivalently
grub-mkconfig -o /boot/grub/grub.cfg

# RHEL/CentOS
grub2-mkconfig -o /boot/grub2/grub.cfg
# or for UEFI
grub2-mkconfig -o /boot/efi/EFI/redhat/grub.cfg

# Install GRUB to MBR (disaster recovery)
grub-install /dev/sda
```

**Useful GRUB kernel parameters** (added to `GRUB_CMDLINE_LINUX`):

| Parameter | Effect |
|-----------|--------|
| `quiet` | Suppress boot messages |
| `splash` | Show splash screen |
| `nomodeset` | Disable KMS (fix black screen issues) |
| `single` / `1` | Boot to single-user mode |
| `ro` / `rw` | Root filesystem mount mode |
| `systemd.unit=rescue.target` | Boot to rescue |
| `init=/bin/bash` | Bypass init completely (recovery) |

---

### `systemd-analyze` — Boot Performance

```bash
# Total boot time
systemd-analyze

# Time breakdown by unit
systemd-analyze blame

# Critical chain (longest path)
systemd-analyze critical-chain

# SVG plot of boot sequence
systemd-analyze plot > /tmp/boot.svg

# Verify unit file syntax
systemd-analyze verify /etc/systemd/system/myapp.service

# Check for security issues in a unit
systemd-analyze security nginx
```

---

### Boot Targets (systemd Runlevels)

| Target | SysVinit equivalent | Description |
|--------|---------------------|-------------|
| `poweroff.target` | 0 | Power off |
| `rescue.target` | 1 | Single-user / rescue |
| `multi-user.target` | 2, 3, 4 | Multi-user, no GUI |
| `graphical.target` | 5 | Multi-user with GUI |
| `reboot.target` | 6 | Reboot |
| `emergency.target` | — | Emergency shell |

```bash
# View current target
systemctl get-default

# Set default target
systemctl set-default multi-user.target

# Switch immediately (like telinit N)
systemctl isolate multi-user.target

# Drop to rescue (root only, unmounts most filesystems)
systemctl rescue

# Emergency mode (even more minimal)
systemctl emergency
```

---

## 8. Environment

### `env`, `export`, `printenv`, `set`, `unset`

```bash
# Show all environment variables
env
printenv

# Show specific variable
printenv HOME
printenv PATH
echo $VARIABLE_NAME

# Show all shell variables (includes functions, not just env)
set

# Export a variable to child processes
export MY_VAR="hello"
export DB_HOST=localhost DB_PORT=5432   # multiple at once

# Set and export in one step (equivalent)
MY_VAR="hello"; export MY_VAR
export MY_VAR="hello"

# Unset a variable
unset MY_VAR

# Run a command with a temporary env var (no permanent effect)
MY_VAR=debug ./myapp

# Run a command with completely clean environment
env -i HOME=/tmp PATH=/usr/bin:/bin ./myapp

# Override specific variables for one command
DB_HOST=testdb pytest tests/
```

---

### `.bashrc` vs `.bash_profile` vs `.profile`

| File | When Loaded | Use For |
|------|------------|---------|
| `~/.bash_profile` | Interactive **login** shell | PATH, env vars, call `.bashrc` |
| `~/.bashrc` | Interactive **non-login** shell | Aliases, functions, prompt |
| `~/.profile` | Any POSIX login shell | Portable env vars (no bash-isms) |
| `/etc/profile` | System-wide login shell | Global PATH, env vars |
| `/etc/bash.bashrc` | System-wide non-login | Global aliases |
| `/etc/profile.d/*.sh` | Sourced by `/etc/profile` | App-specific env vars |

**When each file runs:**
- SSH login → `~/.bash_profile` (which typically sources `~/.bashrc`)
- `sudo -i` or `su -` → `~/.bash_profile`
- New terminal in GUI → `~/.bashrc`
- `bash` (plain) → `~/.bashrc`
- `sh` login → `~/.profile` (not `.bash_profile`)

**Canonical `.bash_profile` pattern:**
```bash
# ~/.bash_profile — load .bashrc for interactive settings
if [ -f ~/.bashrc ]; then
    source ~/.bashrc
fi
# Login-only settings (PATH additions, env vars for GUI apps)
export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
```

---

### PATH Manipulation

```bash
# View current PATH
echo $PATH
echo $PATH | tr ':' '\n'   # one per line

# Prepend to PATH (higher priority)
export PATH="/usr/local/bin:$PATH"
export PATH="$HOME/.local/bin:$PATH"

# Append to PATH (lower priority)
export PATH="$PATH:/opt/myapp/bin"

# Add to PATH only if not already there (idempotent)
add_to_path() {
    case ":$PATH:" in
        *":$1:"*) ;;    # already present
        *) export PATH="$1:$PATH" ;;
    esac
}
add_to_path "$HOME/.local/bin"

# Temporarily remove a directory from PATH
PATH=$(echo $PATH | tr ':' '\n' | grep -v '/bad/dir' | tr '\n' ':' | sed 's/:$//')
```

---

### `source`

```bash
# Reload .bashrc without opening a new shell
source ~/.bashrc
. ~/.bashrc       # POSIX equivalent (dot command)

# Source a script to load its variables into current shell
source /etc/profile.d/java.sh
source .env       # load .env file into current shell

# Difference: source vs execute
# source: runs in current shell, variables persist
# ./script.sh: runs in subshell, variables lost on exit
```

---

## 9. Package Management

### `apt` — Debian/Ubuntu Package Manager

**Repository and index management:**

```bash
# Update package index (always do before install)
apt update

# Upgrade all installed packages
apt upgrade

# Upgrade + handle dependency changes (add/remove packages)
apt full-upgrade

# Upgrade a single package
apt upgrade nginx

# Install packages
apt install nginx
apt install nginx php-fpm postgresql   # multiple
apt install -y nginx                   # non-interactive (yes to all)
apt install --no-install-recommends nginx   # minimal, no extras

# Remove (keeps config files)
apt remove nginx

# Purge (removes config files too)
apt purge nginx

# Remove unused dependencies
apt autoremove
apt autoremove --purge   # also purge configs

# Clean download cache
apt clean        # remove all cached .deb files
apt autoclean    # remove cached .debs that are no longer available
```

**Querying:**

```bash
# Search by name/description
apt search nginx

# Show package details
apt show nginx

# List all installed packages
apt list --installed

# List installed packages matching pattern
apt list --installed | grep python

# Check if a package is installed
dpkg -l nginx
apt list --installed 2>/dev/null | grep "^nginx"

# Show available versions
apt policy nginx

# Show what files a package provides (before installing)
apt-file search nginx    # requires apt-file package + update
```

**Expert tips:**
- Always run `apt update` before `apt install` in scripts — stale indexes cause "package not found" errors in automation.
- Use `DEBIAN_FRONTEND=noninteractive apt install -y` in Dockerfiles and automation to suppress prompts.
- Pin a package to prevent upgrades: `apt-mark hold nginx` / `apt-mark unhold nginx`. List held packages: `apt-mark showhold`.

---

### `dpkg` — Low-Level Debian Package Tool

```bash
# Install a local .deb file
dpkg -i package.deb

# Install and fix dependencies
dpkg -i package.deb || apt-get install -f -y

# Remove package (keep config)
dpkg -r packagename

# Purge package (remove config too)
dpkg -P packagename

# List all installed packages
dpkg -l
dpkg -l 'python*'   # glob filter

# List files installed by a package
dpkg -L nginx

# Which package owns a file?
dpkg -S /etc/nginx/nginx.conf
dpkg -S /usr/bin/python3

# Get package status/details
dpkg -s nginx

# Unpack without installing (advanced)
dpkg --unpack package.deb

# Reconfigure an installed package
dpkg-reconfigure tzdata
dpkg-reconfigure locales
```

---

### `snap` — Snap Package Manager

```bash
# Search for a package
snap find vlc

# Install a snap
snap install vlc
snap install --classic code    # classic confinement (more access)

# List installed snaps
snap list

# Update all snaps
snap refresh

# Update specific snap
snap refresh vlc

# Remove a snap
snap remove vlc

# Show snap info
snap info vlc

# List available channels
snap info vlc | grep channels

# Install from specific channel
snap install vlc --channel=candidate

# Disable/enable without removing
snap disable vlc
snap enable vlc

# Revert to previous version
snap revert vlc
```

---

### RPM/YUM/DNF — Red Hat Package Management

**`rpm`** — Low-level RPM tool (equivalent to `dpkg`):

```bash
# Install local RPM
rpm -ivh package.rpm      # i=install, v=verbose, h=hash progress

# Upgrade
rpm -Uvh package.rpm

# Remove
rpm -e packagename

# List all installed packages
rpm -qa
rpm -qa | grep nginx

# List files in a package
rpm -ql nginx

# Which package owns a file?
rpm -qf /etc/nginx/nginx.conf

# Package info
rpm -qi nginx

# Check package signature
rpm -K package.rpm
```

**`yum`** — Legacy RHEL/CentOS package manager (replaced by DNF):

```bash
yum update
yum install nginx
yum remove nginx
yum search nginx
yum info nginx
yum list installed
yum provides /usr/bin/nginx
yum history            # transaction history
yum history undo last  # undo last transaction
```

**`dnf`** — Modern replacement for yum (RHEL 8+, Fedora):

```bash
# Update indexes and upgrade all
dnf check-update
dnf upgrade

# Install packages
dnf install nginx
dnf install -y nginx      # non-interactive

# Remove
dnf remove nginx

# Autoremove orphan dependencies
dnf autoremove

# Search
dnf search nginx

# Show package details
dnf info nginx

# Which package provides a file?
dnf provides /usr/bin/nginx
dnf provides '*/nginx.conf'

# List installed
dnf list installed
dnf list installed | grep python

# Group operations
dnf group list
dnf group install "Development Tools"

# Transaction history
dnf history
dnf history info 5
dnf history undo 5    # rollback a transaction

# Clean caches
dnf clean all
dnf makecache

# Enable/disable repos
dnf config-manager --enable epel
dnf config-manager --disable epel

# Module streams (RHEL 8+ AppStream)
dnf module list
dnf module enable nodejs:18
dnf module install nodejs:18/default
```

**Expert tips:**
- DNF supports rollback: `dnf history undo <id>` can revert a bad upgrade — no equivalent in apt.
- On RHEL-based systems, add EPEL for community packages: `dnf install epel-release`.
- `dnf provides` is the DNF equivalent of `dpkg -S` and `apt-file search` — finds which package contains a file or binary.
- `yum` on RHEL 8+ is actually a compatibility symlink to `dnf` — they are identical.

---

*Reference compiled for Zia Venture Group | Adam Lynch | 2026*
