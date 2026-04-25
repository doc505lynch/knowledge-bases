# Linux Filesystem Commands — Exhaustive Reference

> Expert-level reference for filesystem navigation, file operations, permissions, links, archiving, disk management, and file content inspection. All examples use realistic paths and scenarios.

---

## Table of Contents

1. [Navigation](#1-navigation)
2. [File Operations](#2-file-operations)
3. [Finding Files](#3-finding-files)
4. [Permissions](#4-permissions)
5. [Archives & Compression](#5-archives--compression)
6. [Disk & Filesystems](#6-disk--filesystems)
7. [File Content](#7-file-content)

---

## 1. Navigation

### `pwd` — Print Working Directory

**Syntax:** `pwd [OPTION]`

| Flag | Meaning |
|------|---------|
| `-L` | Print logical path (follows symlinks, default) |
| `-P` | Print physical path (resolves all symlinks) |

**Examples:**
```bash
# Basic usage
pwd
# /home/alice/projects

# Inside a symlinked directory — logical vs physical
cd /var/www   # symlink → /srv/nginx/html
pwd -L        # /var/www
pwd -P        # /srv/nginx/html

# Use in scripts to store the script's own directory
SCRIPT_DIR="$(cd "$(dirname "${BASH_SOURCE[0]}")" && pwd -P)"
```

**Gotcha:** `$PWD` is a shell variable that mirrors `pwd -L`. If you cd into a symlink, `$PWD` shows the symlink path, not the real path. Use `pwd -P` when you need the canonical path for operations that will be executed outside the current shell context.

---

### `cd` — Change Directory

**Syntax:** `cd [OPTION] [DIR]`

| Form | Meaning |
|------|---------|
| `cd` | Go to `$HOME` |
| `cd ~` | Go to `$HOME` (explicit tilde expansion) |
| `cd ~username` | Go to another user's home directory |
| `cd -` | Go to the previous directory (`$OLDPWD`) |
| `cd ..` | Go up one level |
| `cd ../..` | Go up two levels |
| `cd /absolute/path` | Go to absolute path |
| `cd relative/path` | Go to relative path from `$PWD` |

**Examples:**
```bash
# Toggle between two directories
cd /etc/nginx
cd /var/log/nginx
cd -              # back to /etc/nginx
cd -              # back to /var/log/nginx

# Navigate relative to home
cd ~/projects/myapp/src

# Go to another user's home (requires permission or root)
cd ~deploy

# Go up two levels and into sibling directory
cd ../../other-project

# Use CDPATH to search multiple base directories
export CDPATH=".:/home/alice/projects:/opt"
cd myapp          # searches . then ~/projects then /opt for 'myapp'
```

**Gotcha:** `cd -` prints the directory it switched to. In scripts, suppress with `cd - >/dev/null`. Also, `cd` with no argument is equivalent to `cd $HOME`, not `cd /` — a common beginner confusion.

---

### `ls` — List Directory Contents

**Syntax:** `ls [OPTION]... [FILE]...`

| Flag | Meaning |
|------|---------|
| `-l` | Long format (permissions, owner, size, mtime) |
| `-a` | Show all including hidden (`.` prefix) files |
| `-A` | Show hidden files but exclude `.` and `..` |
| `-h` | Human-readable sizes (KB, MB, GB) — requires `-l` |
| `-R` | Recursive listing of all subdirectories |
| `-t` | Sort by modification time, newest first |
| `-S` | Sort by file size, largest first |
| `-r` | Reverse sort order |
| `-1` | One file per line (useful for scripting) |
| `-d` | List directory itself, not its contents |
| `-i` | Show inode number |
| `-n` | Like `-l` but show numeric UID/GID |
| `-F` | Append type indicators (`/` dir, `*` exec, `@` symlink, `|` FIFO, `=` socket) |
| `-p` | Append `/` to directory names only |
| `-X` | Sort alphabetically by extension |
| `-G` | Colorize output (BSD/macOS) |
| `--color=auto` | Colorize output (GNU) |
| `--color=never` | Disable color (useful in pipes) |
| `--time-style=FORMAT` | Control timestamp display format |
| `-Z` | Show SELinux security context |
| `--group-directories-first` | List directories before files |

**Examples:**
```bash
# Full long listing with hidden files and human sizes
ls -lAh /var/log

# Sort by time, newest last (reverse time sort)
ls -ltr /var/log/nginx/

# Sort by size, largest first
ls -lSh ~/Downloads/

# Recursive with file-type indicators
ls -RF /etc/nginx/

# List only the directory entry itself (not contents)
ls -ld /etc/nginx/

# Show inode numbers (useful when filenames are identical-looking)
ls -li /proc/1/fd/

# One filename per line for safe scripting (avoids word-splitting)
ls -1 /etc/cron.d/

# Long listing with full ISO timestamps
ls -l --time-style='+%Y-%m-%d %H:%M:%S' /var/log/

# List only directories
ls -d /etc/*/

# Show numeric UIDs to avoid LDAP/NIS lookup delays
ls -ln /home/
```

**Gotcha:** Never parse `ls` output in scripts — filenames can contain spaces, newlines, and special characters that break word-splitting. Use `find`, `glob`, or `printf '%s\n' *` instead. The `--color` flag embeds ANSI escape sequences that corrupt downstream `grep`/`awk` — always pipe with `--color=never` or `| cat`.

---

### `tree` — Directory Tree Visualization

**Syntax:** `tree [OPTION]... [DIRECTORY]...`

| Flag | Meaning |
|------|---------|
| `-a` | Show hidden files |
| `-d` | Show directories only |
| `-L LEVEL` | Limit depth to LEVEL |
| `-f` | Print full path prefix |
| `-i` | No indentation (useful with `-f` for scripting) |
| `-s` | Show file sizes |
| `-h` | Human-readable sizes |
| `-p` | Show permissions |
| `-u` | Show owner |
| `-g` | Show group |
| `-D` | Show last modification date |
| `-t` | Sort by modification time |
| `-r` | Reverse sort |
| `-I PATTERN` | Exclude files matching pattern |
| `--prune` | Omit empty directories |
| `-J` | Output as JSON |
| `-X` | Output as XML |
| `-H BASEURL` | Output as HTML |
| `--charset=UTF-8` | Use UTF-8 drawing characters |

**Examples:**
```bash
# Two-level tree of current directory with sizes
tree -L 2 -h .

# Show only directories, three levels deep
tree -d -L 3 /etc

# Show permissions and owner, excluding .git
tree -pu -I '.git|node_modules' ~/projects/myapp

# Full paths, no indentation — grep-friendly
tree -fi --prune /var/www | grep '\.php$'

# JSON output for programmatic consumption
tree -J -L 2 /opt/app > structure.json

# Show modification times
tree -D -L 2 /etc/nginx
```

**Gotcha:** `tree` is not installed by default on all distributions. On Debian/Ubuntu: `apt install tree`. On RHEL/CentOS: `yum install tree`. JSON output (`-J`) requires tree 1.7+.

---

## 2. File Operations

### `cp` — Copy Files and Directories

**Syntax:** `cp [OPTION]... SOURCE... DEST`

| Flag | Meaning |
|------|---------|
| `-r`, `-R` | Recursive (copy directories) |
| `-a` | Archive mode: `-dR --preserve=all` (preserves permissions, timestamps, symlinks, owner) |
| `-p` | Preserve mode, ownership, timestamps |
| `-v` | Verbose output |
| `-i` | Interactive: prompt before overwrite |
| `-n` | No-clobber: never overwrite existing files |
| `-u` | Update: copy only if source is newer |
| `-l` | Hard-link instead of copy |
| `-s` | Symbolic-link instead of copy |
| `-f` | Force: remove destination if needed |
| `--backup[=CONTROL]` | Make backup of existing destinations |
| `--suffix=SUFFIX` | Backup suffix (default `~`) |
| `-T` | Treat DEST as a normal file, not directory |
| `--reflink=auto` | Use copy-on-write if filesystem supports it (btrfs/XFS) |
| `-d` | Same as `--no-dereference --preserve=links` |
| `--sparse=WHEN` | Control sparse file handling (`auto`, `always`, `never`) |

**Examples:**
```bash
# Copy a file with permission and timestamp preservation
cp -p /etc/nginx/nginx.conf /etc/nginx/nginx.conf.bak

# Recursive archive copy — mirrors directory perfectly
cp -a /var/www/html/ /backup/html-$(date +%Y%m%d)/

# Copy only files newer than destination (incremental copy)
cp -uv /mnt/source/* /mnt/dest/

# Copy multiple files into a directory
cp file1.txt file2.txt file3.txt /tmp/

# No-clobber copy — safe for one-time migrations
cp -rn /mnt/old-data/ /mnt/new-data/

# Backup existing file before overwriting
cp --backup=numbered /etc/fstab /etc/fstab
# Creates /etc/fstab.~1~, then .~2~, etc.

# Copy-on-write (instant, no disk I/O) on btrfs
cp --reflink=always bigfile.img bigfile-copy.img

# Copy preserving SELinux context
cp --preserve=context /etc/passwd /tmp/passwd.test
```

**Gotcha:** `cp -r src/ dest/` behaves differently depending on whether `dest/` exists. If it exists, `src` is copied *inside* `dest` → `dest/src/`. If it does not exist, it becomes `dest`. This trailing-slash asymmetry burns everyone at least once. Use `rsync` for more predictable behavior.

---

### `mv` — Move / Rename Files

**Syntax:** `mv [OPTION]... SOURCE... DEST`

| Flag | Meaning |
|------|---------|
| `-i` | Interactive: prompt before overwrite |
| `-n` | No-clobber: never overwrite |
| `-f` | Force: no prompts |
| `-v` | Verbose |
| `-u` | Move only if source is newer or destination absent |
| `--backup[=CONTROL]` | Backup existing destination |
| `-t DIR` | Move all sources into DIR |

**Examples:**
```bash
# Simple rename
mv oldname.txt newname.txt

# Move multiple files into a directory
mv *.log /var/log/archive/

# Rename with backup of existing file
mv --backup=numbered report.pdf report.pdf

# Atomic rename (same filesystem) — used for safe config deploys
cp nginx.conf.new nginx.conf.tmp && mv nginx.conf.tmp nginx.conf

# Move newer files only
mv -u /tmp/download/* ~/Downloads/

# Move everything from source into target directory (explicit)
mv -t /opt/app/ config.yml app.py requirements.txt
```

**Gotcha:** `mv` across filesystems falls back to a copy+delete, which is not atomic. For atomic cross-filesystem deploys, you need an intermediate temp file on the same device as the destination. Also, `mv -n` silently does nothing if the destination exists — verify with `-v`.

---

### `rm` — Remove Files and Directories

**Syntax:** `rm [OPTION]... FILE...`

| Flag | Meaning |
|------|---------|
| `-r`, `-R` | Recursive (delete directories and contents) |
| `-f` | Force: ignore nonexistent files, no prompts |
| `-i` | Interactive: prompt before each deletion |
| `-I` | Prompt once before deleting more than 3 files |
| `-v` | Verbose |
| `-d` | Remove empty directories (same as `rmdir`) |
| `--one-file-system` | Do not cross filesystem boundaries during recursive delete |
| `--no-preserve-root` | Allow removing `/` (extremely dangerous) |

**Examples:**
```bash
# Delete a single file
rm /tmp/tempfile.txt

# Delete directory and all contents
rm -rf /tmp/old-build/

# Interactive delete with confirmation
rm -ri ~/Downloads/old-project/

# Delete all .tmp files in current directory (verbose)
rm -v *.tmp

# Safe recursive delete that won't cross mount points
rm -rf --one-file-system /mnt/container-root/

# Delete files with spaces or special chars (use -- to stop option parsing)
rm -- "-weirdfilename.txt"
rm -- "file with spaces.txt"
```

**Gotcha:** There is no undo. `rm -rf /` or `rm -rf $VAR/` where `$VAR` is empty (`/`) can destroy a system. Always quote variables. Consider `trash-cli` (`trash` command) for a recoverable delete. The `--one-file-system` flag is critical when running `rm -rf` on container roots that might have bind mounts.

---

### `mkdir` — Make Directories

**Syntax:** `mkdir [OPTION]... DIRECTORY...`

| Flag | Meaning |
|------|---------|
| `-p` | Create parent directories as needed; no error if exists |
| `-v` | Verbose: print each created directory |
| `-m MODE` | Set permissions on creation (octal or symbolic) |
| `--parents` | Synonym for `-p` |

**Examples:**
```bash
# Create nested path in one command
mkdir -p /opt/app/config/ssl/certs

# Create with specific permissions (group-writable)
mkdir -m 775 /var/www/shared

# Create multiple directories at once
mkdir -p project/{src,tests,docs,data/{raw,processed}}

# Verbose creation
mkdir -pv /etc/myapp/conf.d

# Create temp directory with mktemp (safer than fixed names)
TMPDIR=$(mktemp -d /tmp/build.XXXXXX)
echo "Working in: $TMPDIR"
```

**Gotcha:** `mkdir -p dir` with a specific `-m` mode only sets the mode on the final directory, not the parent directories created along the way. Parent directories get the default umask-filtered mode. If you need a full owned tree, use a loop or `install -d -m MODE path`.

---

### `rmdir` — Remove Empty Directories

**Syntax:** `rmdir [OPTION]... DIRECTORY...`

| Flag | Meaning |
|------|---------|
| `-p` | Remove directory and its empty parents |
| `-v` | Verbose |
| `--ignore-fail-on-non-empty` | Suppress errors for non-empty directories |

**Examples:**
```bash
# Remove a single empty directory
rmdir /tmp/empty-dir

# Remove empty directory and empty parents up the chain
rmdir -p /tmp/a/b/c/

# Remove multiple empty directories
rmdir /tmp/dir1 /tmp/dir2 /tmp/dir3
```

**Gotcha:** `rmdir` only works on empty directories. For non-empty directories, use `rm -r`. When you want to clean up a deep empty tree, `rmdir -p` is cleaner than `rm -r` since it will fail safely if any directory is non-empty.

---

### `touch` — Update Timestamps / Create Empty Files

**Syntax:** `touch [OPTION]... FILE...`

| Flag | Meaning |
|------|---------|
| `-a` | Change only access time |
| `-m` | Change only modification time |
| `-t STAMP` | Use `[[CC]YY]MMDDhhmm[.ss]` format |
| `-d STRING` | Use date string (e.g., `"2024-01-15 10:30"`) |
| `-r FILE` | Use reference file's timestamps |
| `-c` | Do not create file if it does not exist |

**Examples:**
```bash
# Create empty files
touch file1.txt file2.txt file3.txt

# Update timestamps to a specific time
touch -t 202401150830 report.txt

# Set timestamps to match another file
touch -r /etc/passwd /tmp/same-time-file

# Update only modification time to now
touch -m bigfile.tar.gz

# Use human-readable date string
touch -d "last monday" access.log

# Create if not exists, but don't create — just update if present
touch -c maybe-exists.lock
```

**Gotcha:** `touch` on a symlink changes the target's timestamps, not the symlink's own timestamps. Use `touch -h` (if available) or `utimensat` via Python to change symlink timestamps. `touch` creates zero-byte files, which is useful as lock files and flag markers in scripts.

---

### `ln` — Create Links

**Syntax:** `ln [OPTION]... TARGET [LINKNAME]`  
**Syntax:** `ln [OPTION]... TARGET... DIRECTORY`

| Flag | Meaning |
|------|---------|
| `-s` | Create symbolic (soft) link |
| `-f` | Force: remove existing destination |
| `-i` | Interactive: prompt before removing |
| `-n` | Treat LINKNAME as a normal file if it is a symlink to a directory |
| `-r` | Create symbolic links relative to link location |
| `-v` | Verbose |
| `-t DIR` | Specify link directory |
| `-b` | Make backup of each existing destination |

#### Hard Links vs Symbolic Links

| Property | Hard Link | Symbolic Link |
|----------|-----------|---------------|
| Points to | Inode (data directly) | Pathname (another file) |
| Cross-filesystem | No | Yes |
| Can link directories | No (root only, dangerous) | Yes |
| Survives target deletion | Yes (data remains) | No (becomes dangling) |
| Shows in `ls -l` | Same as file (`-`) | `l` type with `->` |
| `stat` inode number | Same as original | Different |
| `readlink` works | No | Yes |

**Examples:**
```bash
# Hard link — two directory entries to same inode
ln /var/log/app.log /var/log/app-hardlink.log
ls -li /var/log/app*.log   # same inode number

# Symbolic link — absolute path
ln -s /etc/nginx/sites-available/myapp /etc/nginx/sites-enabled/myapp

# Symbolic link — relative path (portable if directory moves)
ln -sr ../sites-available/myapp ./sites-enabled/myapp

# Overwrite existing symlink
ln -sf /opt/python3.12/bin/python3 /usr/local/bin/python3

# Link all files from a directory into another
ln -s /opt/myapp/bin/* /usr/local/bin/

# Verify symlink
readlink -f /usr/local/bin/python3
# Shows resolved absolute path

# Find dangling (broken) symlinks
find /etc -maxdepth 3 -type l ! -exec test -e {} \; -print
```

**Gotcha:** Relative symlinks are resolved relative to the symlink's location, not where you ran `ln`. `ln -s ../foo bar/baz` means `baz` → `../foo` evaluated from inside `bar/`. Creating symlinks from the wrong directory is a common mistake. Use `ln -sr` (GNU) to automatically compute the correct relative path, or use absolute paths when in doubt.

---

### `file` — Determine File Type

**Syntax:** `file [OPTION]... FILE...`

| Flag | Meaning |
|------|---------|
| `-b` | Brief: omit filename prefix |
| `-i`, `--mime-type` | Output MIME type |
| `-s` | Read block/character special files (devices) |
| `-z` | Look inside compressed files |
| `-L` | Follow symlinks |
| `-f FILE` | Read filenames from a list file |
| `--extension` | Print valid file extensions for detected type |

**Examples:**
```bash
# Basic type detection
file /bin/bash
# /bin/bash: ELF 64-bit LSB pie executable, x86-64, ...

# MIME type for web/scripting use
file -b --mime-type image.jpg
# image/jpeg

# Detect type of file with misleading extension
file suspicious.txt
# suspicious.txt: PE32+ executable (GUI) Intel 80386, for MS Windows

# Read inside gzipped files
file -z archive.tar.gz
# archive.tar.gz: POSIX tar archive (GNU) (gzip compressed data, ...)

# Check a block device
file -s /dev/sda1
# /dev/sda1: Linux rev 1.0 ext4 filesystem data, ...

# Batch check a list of files
find . -name '*.log' | file -f -
```

**Gotcha:** `file` uses magic number detection, not extensions. It reads the first few hundred bytes. For very short files or certain formats, it may report `ASCII text` when the content is actually structured data (JSON, YAML, etc.).

---

### `stat` — Display File Status

**Syntax:** `stat [OPTION]... FILE...`

| Flag | Meaning |
|------|---------|
| `-f` | Display filesystem status instead of file status |
| `-L` | Follow symlinks |
| `-t` | Terse output (one line per file) |
| `--printf=FORMAT` | Custom output format |
| `-c FORMAT` | Same as `--printf` but adds newline |

**Format specifiers for `--printf`:**
| Spec | Meaning |
|------|---------|
| `%n` | File name |
| `%s` | Total size in bytes |
| `%b` | Blocks allocated |
| `%f` | Raw hex mode |
| `%a` | Access rights in octal |
| `%A` | Access rights in human-readable |
| `%u` | User ID |
| `%U` | Username |
| `%g` | Group ID |
| `%G` | Group name |
| `%i` | Inode number |
| `%h` | Hard link count |
| `%x` | Time of last access |
| `%y` | Time of last modification |
| `%z` | Time of last status change |
| `%w` | Time of file birth (if available) |
| `%F` | File type |
| `%d` | Device number |

**Examples:**
```bash
# Full stat of a file
stat /etc/passwd

# Extract just the octal permissions
stat -c '%a %n' /etc/shadow
# 640 /etc/shadow

# Get modification time as Unix timestamp
stat -c '%Y' /var/log/syslog

# Check inode number (confirms hard links share an inode)
stat -c '%i %n' /bin/sh /bin/bash

# Filesystem info
stat -f /home
# Shows block size, total/free/available blocks, etc.

# Portable one-liner: file size in bytes
stat --printf="%s\n" largefile.bin
```

**Gotcha:** `stat` on a symlink shows the symlink's own metadata (tiny size, `l` file type). Use `-L` to stat the target. Also, birth time (`%w`) is only available on filesystems that record it (ext4 with `--iversion`, btrfs, XFS) and requires a recent kernel.

---

### `basename` and `dirname`

**Syntax:** `basename NAME [SUFFIX]`  
**Syntax:** `dirname NAME`

**Examples:**
```bash
# Extract filename from path
basename /var/log/nginx/access.log
# access.log

# Strip extension too
basename /var/log/nginx/access.log .log
# access

# Extract directory portion
dirname /var/log/nginx/access.log
# /var/log/nginx

# Common script pattern to get script's own directory
SCRIPT_DIR="$(dirname "$(realpath "$0")")"

# Process files in a loop, output alongside source
for f in /var/log/*.log; do
    echo "Processing: $(basename "$f")"
    gzip -k "$f" -c > "/backup/$(basename "$f").gz"
done
```

**Gotcha:** `basename` and `dirname` are string operations — they don't check whether the path exists. For canonical path resolution (following symlinks), use `realpath` or `readlink -f` instead.

---

## 3. Finding Files

### `find` — Search for Files

**Syntax:** `find [STARTING-POINT...] [EXPRESSION]`

#### Primary Tests

| Expression | Meaning |
|-----------|---------|
| `-name PATTERN` | Match filename (case-sensitive glob) |
| `-iname PATTERN` | Match filename (case-insensitive) |
| `-path PATTERN` | Match full path |
| `-ipath PATTERN` | Match full path (case-insensitive) |
| `-regex PATTERN` | Match full path with regex (ERE) |
| `-type TYPE` | `f`=file, `d`=dir, `l`=symlink, `b`=block, `c`=char, `p`=FIFO, `s`=socket |
| `-size N[cwbkMG]` | File size: `c`=bytes, `k`=kilobytes, `M`=megabytes, `G`=gigabytes |
| `-mtime N` | Modified N*24h ago (exact), `-N`=less than, `+N`=more than |
| `-atime N` | Accessed N days ago |
| `-ctime N` | Status changed N days ago |
| `-mmin N` | Modified N minutes ago |
| `-amin N` | Accessed N minutes ago |
| `-newer FILE` | Modified more recently than FILE |
| `-newermt TIME` | Modified more recently than time string |
| `-perm MODE` | Exact permissions |
| `-perm -MODE` | All bits set (bitwise AND) |
| `-perm /MODE` | Any bits set (bitwise OR) |
| `-user NAME` | Owned by user |
| `-group NAME` | Owned by group |
| `-uid N` | Owned by numeric UID |
| `-gid N` | Owned by numeric GID |
| `-nouser` | No corresponding user in /etc/passwd |
| `-nogroup` | No corresponding group in /etc/group |
| `-empty` | Empty file or empty directory |
| `-readable` | Currently readable by you |
| `-writable` | Currently writable by you |
| `-executable` | Currently executable by you |
| `-links N` | Has N hard links |
| `-inum N` | Has inode number N |
| `-samefile FILE` | Same inode as FILE (finds hard links) |
| `-maxdepth N` | Descend at most N directory levels |
| `-mindepth N` | Skip first N levels |
| `-xdev` | Don't cross filesystem boundaries |
| `-follow` | Follow symlinks |
| `-L` | Follow symlinks (placed before starting point) |

#### Logical Operators

| Operator | Meaning |
|---------|---------|
| `EXPR1 EXPR2` | AND (implicit) |
| `-a` | Explicit AND |
| `-o` | OR |
| `!` or `-not` | NOT |
| `\( EXPR \)` | Grouping |

#### Actions

| Action | Meaning |
|--------|---------|
| `-print` | Print path (default action) |
| `-print0` | Print with null terminator (NUL-safe for pipes) |
| `-ls` | Like `ls -dils` for each result |
| `-delete` | Delete matching files (implies `-depth`) |
| `-exec CMD {} \;` | Run CMD on each match (one by one) |
| `-exec CMD {} +` | Run CMD with all matches batched (efficient) |
| `-execdir CMD {} \;` | Run CMD from within the file's directory |
| `-ok CMD {} \;` | Like `-exec` but prompts user |
| `-prune` | Don't descend into matching directory |

**Examples:**
```bash
# Find all Python files modified in the last 24 hours
find /opt/app -name '*.py' -mtime -1

# Find files larger than 100MB
find /var -type f -size +100M -ls

# Find and delete all .pyc files
find . -type f -name '*.pyc' -delete

# Find SUID executables (potential security issue)
find / -xdev -type f -perm -4000 -ls 2>/dev/null

# Find files owned by a specific user
find /home -user alice -type f

# Find world-writable files (excluding /proc and /sys)
find / -xdev -type f -perm -o+w -not -path '/proc/*' 2>/dev/null

# Find and safely process files with spaces in names
find . -name '*.log' -print0 | xargs -0 gzip

# Find directories modified more than 30 days ago and delete them
find /tmp -maxdepth 1 -type d -mtime +30 -exec rm -rf {} +

# Find files between 1MB and 10MB
find . -type f -size +1M -size -10M

# Find files matching multiple extensions
find . -type f \( -name '*.jpg' -o -name '*.png' -o -name '*.gif' \)

# Exclude a directory from search (prune)
find /var -name '*.log' -not -path '*/nginx/*'
# OR with prune (faster — doesn't enter the directory):
find /var \( -path '*/nginx' -prune \) -o \( -name '*.log' -print \)

# Find files and execute a complex command per-file
find /etc -name '*.conf' -exec sh -c 'echo "=== {} ===" && cat {}' \;

# Find hard links to a specific file
find / -xdev -inum $(stat -c '%i' /etc/passwd) 2>/dev/null

# Find empty files or directories
find /tmp -empty -type f
find /var -empty -type d

# Find recently changed config files (last 10 minutes)
find /etc -mmin -10 -type f

# Files NOT owned by root in /etc
find /etc -not -user root -type f 2>/dev/null

# Find broken symlinks
find /etc -type l ! -exec test -e {} \; -print
```

**Gotcha:** `-exec CMD {} \;` runs CMD once per file. `-exec CMD {} +` batches all results as arguments to a single CMD invocation — faster but requires the command to accept multiple arguments. `find -delete` is safer than piping to `xargs rm` because it won't accidentally delete a directory due to a race condition. Always use `-print0` with `xargs -0` when filenames may contain spaces.

---

### `locate` — Fast File Lookup via Database

**Syntax:** `locate [OPTION]... PATTERN...`

| Flag | Meaning |
|------|---------|
| `-i` | Case-insensitive |
| `-c` | Print count only |
| `-l N` | Limit to N results |
| `-n N` | Synonym for `-l` |
| `-r REGEX` | Use regex instead of glob |
| `-e` | Verify file exists before printing |
| `-b` | Match only the basename |
| `--database DBPATH` | Use alternate database |
| `-S` | Print database statistics |

**Examples:**
```bash
# Find all nginx configs
locate nginx.conf

# Case-insensitive search
locate -i readme.md

# Basename match only (not full path matches)
locate -b '*.service'

# Verify results exist (database may be stale)
locate -e libssl.so

# Count matches
locate -c '*.py'

# Database stats
locate -S
```

**Gotcha:** `locate` searches a pre-built database (usually at `/var/lib/mlocate/mlocate.db`), not the live filesystem. It will miss recently created files and show recently deleted files. Run `sudo updatedb` to refresh. Files in directories excluded in `/etc/updatedb.conf` (like `/tmp`, network mounts) are not indexed.

---

### `updatedb` — Update locate Database

**Syntax:** `updatedb [OPTION]...`

| Flag | Meaning |
|------|---------|
| `-U DIR` | Update only this directory subtree |
| `-o FILE` | Output to specified database file |
| `--prunepaths 'PATH...'` | Exclude these paths |
| `--prunefs 'FS...'` | Exclude these filesystem types |

**Examples:**
```bash
# Full system update (needs root)
sudo updatedb

# Update only a specific directory
sudo updatedb -U /opt/new-software

# Update with custom exclusions
sudo updatedb --prunepaths '/tmp /var/cache /proc /sys'
```

---

### `which` — Locate a Command

**Syntax:** `which [OPTION] COMMAND...`

| Flag | Meaning |
|------|---------|
| `-a` | Print all matches in PATH |

**Examples:**
```bash
# Find the python3 binary
which python3
# /usr/bin/python3

# Find all python versions in PATH
which -a python

# Check if a command exists in scripts
if which jq >/dev/null 2>&1; then
    echo "jq is available"
fi
```

**Gotcha:** `which` only searches `$PATH`. It won't find shell built-ins (`cd`, `echo`) or functions. Use `type` for a comprehensive answer.

---

### `whereis` — Locate Binary, Source, and Manual

**Syntax:** `whereis [OPTION]... COMMAND...`

| Flag | Meaning |
|------|---------|
| `-b` | Search only binaries |
| `-m` | Search only manuals |
| `-s` | Search only sources |
| `-u` | Show unusual entries (missing one of b/m/s) |
| `-B DIR` | Specify directory for binary search |

**Examples:**
```bash
# Find binary, source, and manpage for ssh
whereis ssh
# ssh: /usr/bin/ssh /usr/share/man/man1/ssh.1.gz

# Find only the binary
whereis -b nginx
# nginx: /usr/sbin/nginx

# Find commands with no manual page
whereis -u -m *
```

---

### `type` — Show How a Command Name Is Interpreted

**Syntax:** `type [OPTION] NAME...`

| Flag | Meaning |
|------|---------|
| `-a` | Show all locations |
| `-t` | Print type only: `alias`, `keyword`, `function`, `builtin`, `file` |
| `-p` | Force PATH search, like `which` |
| `-f` | Suppress function lookups |

**Examples:**
```bash
# What is 'cd'?
type cd
# cd is a shell builtin

# What is 'll'?
type ll
# ll is aliased to 'ls -l --color=auto'

# Find all versions including aliases and builtins
type -a ls
# ls is aliased to 'ls --color=auto'
# ls is /bin/ls

# Machine-readable type
type -t python3
# file
```

**Gotcha:** `type` is a bash built-in, not a standalone utility. In scripts, prefer `command -v NAME` for a portable equivalent to `which` that also respects functions and builtins.

---

## 4. Permissions

### Permission Model Overview

Linux permissions are a 12-bit mask applied to each file and directory:

```
Type  Owner   Group   Others
-      rwx     rwx     rwx
```

| Bit | File meaning | Directory meaning |
|-----|-------------|------------------|
| `r` (4) | Read file content | List directory (`ls`) |
| `w` (2) | Write/modify file | Create/delete files in dir |
| `x` (1) | Execute file | Enter directory (`cd`) |
| `s` on owner | setuid | setuid |
| `s` on group | setgid | Files inherit group |
| `t` on others | — | Sticky bit |

---

### `chmod` — Change File Mode Bits

**Syntax:** `chmod [OPTION]... MODE FILE...`  
**Syntax:** `chmod [OPTION]... OCTAL_MODE FILE...`

#### Symbolic Mode Reference

```
WHO:    u (user/owner)  g (group)  o (others)  a (all)
OP:     + (add)  - (remove)  = (set exactly)
PERM:   r  w  x  X  s  t  u  g  o
```

- `X` = execute only if file is a directory or already has execute for any user
- `s` = setuid/setgid  
- `t` = sticky bit

#### Octal Mode Reference

```
4000 = setuid
2000 = setgid
1000 = sticky
0400 = owner read
0200 = owner write
0100 = owner execute
0040 = group read
0020 = group write
0010 = group execute
0004 = other read
0002 = other write
0001 = other execute
```

| Flag | Meaning |
|------|---------|
| `-R` | Recursive |
| `-v` | Verbose |
| `-c` | Report only when change is made |
| `--reference=FILE` | Use reference file's permissions |

**Examples:**
```bash
# Make a script executable by owner
chmod u+x deploy.sh

# Set permissions exactly (owner: rwx, group: rx, others: r)
chmod 754 script.sh
# or symbolically:
chmod u=rwx,g=rx,o=r script.sh

# Remove write from group and others
chmod go-w sensitive.conf

# Add execute for all, but only if already executable for any
chmod a+X *

# Recursive permission reset (common for web directories)
chmod -R 755 /var/www/html/
chmod -R 644 /var/www/html/*.html

# Set setuid on a binary
chmod u+s /usr/local/bin/special-tool
chmod 4755 /usr/local/bin/special-tool    # same with octal

# Set setgid on a directory (new files inherit group)
chmod g+s /var/www/shared/
chmod 2775 /var/www/shared/

# Set sticky bit on /tmp
chmod +t /tmp
chmod 1777 /tmp     # same with octal

# Copy permissions from reference file
chmod --reference=/etc/passwd /tmp/myfile

# Remove all other permissions recursively
chmod -R o= /home/alice/private/
```

**Gotcha:** `chmod -R 777 .` is almost never correct and creates security holes. For web directories, the common correct pattern is `755` for directories and `644` for files. Use `find . -type d -exec chmod 755 {} +` and `find . -type f -exec chmod 644 {} +` to set them separately. The `X` (capital) bit is extremely useful here.

---

### `chown` — Change File Owner and Group

**Syntax:** `chown [OPTION]... [OWNER][:[GROUP]] FILE...`

| Flag | Meaning |
|------|---------|
| `-R` | Recursive |
| `-v` | Verbose |
| `-c` | Report only changes |
| `-h` | Change symlink itself (not target) |
| `--reference=FILE` | Use reference file's owner/group |
| `--from=OWNER:GROUP` | Change only if current owner:group matches |

**Examples:**
```bash
# Change owner
chown alice /home/alice/file.txt

# Change owner and group
chown alice:developers /var/www/html/

# Change only group (colon prefix, no owner)
chown :www-data /var/www/html/

# Recursive ownership change for web app
chown -R www-data:www-data /var/www/myapp/

# Change ownership of symlink itself
chown -h alice symlink-to-something

# Change from a specific owner only (safe)
chown --from=root:root alice:alice /tmp/myfile

# Match ownership of reference file
chown --reference=/etc/passwd /etc/shadow
```

**Gotcha:** `chown -R` follows symlinks into other directories by default on some systems. Use `chown -Rh` to change symlinks themselves without following. When changing ownership of web directories, be careful not to change ownership of files that need to be owned by specific system users.

---

### `chgrp` — Change Group Ownership

**Syntax:** `chgrp [OPTION]... GROUP FILE...`

| Flag | Meaning |
|------|---------|
| `-R` | Recursive |
| `-v` | Verbose |
| `-h` | Change symlink itself |
| `--reference=FILE` | Use reference file's group |

**Examples:**
```bash
# Change group
chgrp developers /opt/app/

# Recursive
chgrp -R www-data /var/www/html/

# Reference file
chgrp --reference=/etc/passwd /tmp/testfile
```

**Note:** `chgrp GROUP FILE` is equivalent to `chown :GROUP FILE`. `chown` is generally preferred as it handles both owner and group.

---

### `umask` — Set Default Permission Mask

**Syntax:** `umask [OPTION] [MASK]`

| Flag | Meaning |
|------|---------|
| `-S` | Display in symbolic notation |
| `-p` | Output in a form that can be reused as input |

The umask is **subtracted** from default permissions:
- Files default to `666` (no execute). With `umask 022` → `644`
- Directories default to `777`. With `umask 022` → `755`

**Examples:**
```bash
# Show current umask
umask
# 0022

# Show symbolic
umask -S
# u=rwx,g=rx,o=rx

# Tight umask for sensitive files (only owner can read/write)
umask 077
touch private.key
ls -l private.key
# -rw------- 1 alice alice ...

# Permissive umask for shared collaboration
umask 002    # group-writable: dirs 775, files 664

# Set umask in a script and restore
OLD_UMASK=$(umask)
umask 077
# ... create sensitive files ...
umask $OLD_UMASK
```

**Gotcha:** `umask` only affects newly created files and directories — it does not change existing ones. Changes to umask are per-process and are not inherited back by parent processes. Set umask in `/etc/profile`, `/etc/bash.bashrc`, or `~/.bashrc` for persistence. Note that `umask 022` does NOT mean permissions are `022` — it means permissions are `default MINUS 022`.

---

### ACLs — Access Control Lists

ACLs allow per-user and per-group permissions beyond the standard owner/group/others model.

#### `getfacl` — Get File ACL

**Syntax:** `getfacl [OPTION]... FILE...`

| Flag | Meaning |
|------|---------|
| `-a` | Display file ACL only |
| `-d` | Display default ACL only |
| `-R` | Recursive |
| `-t` | Use tabular output format |
| `-p` | Don't strip leading `/` from filenames |
| `-n` | Print numeric UIDs/GIDs |
| `-e` | Print effective permissions |

**Examples:**
```bash
# View ACL of a file
getfacl /var/www/html/index.html

# Recursive ACL dump
getfacl -R /var/www/ > acl-backup.txt

# Numeric UIDs
getfacl -n /etc/shadow
```

#### `setfacl` — Set File ACL

**Syntax:** `setfacl [OPTION]... ENTRY FILE...`

ACL entry format: `[d:]TYPE:NAME:PERMS`
- `d:` = default ACL (directory only, inherited by new files)
- TYPE: `u`/`user`, `g`/`group`, `o`/`other`, `m`/`mask`

| Flag | Meaning |
|------|---------|
| `-m ENTRY` | Modify (add or change) ACL entry |
| `-x ENTRY` | Remove ACL entry |
| `-b` | Remove all ACL entries |
| `-k` | Remove default ACL |
| `-R` | Recursive |
| `-d` | Apply to default ACL |
| `--set=ENTRIES` | Replace entire ACL |
| `--restore=FILE` | Restore ACLs from `getfacl` output |
| `-n` | Don't recalculate mask |

**Examples:**
```bash
# Grant read access to specific user
setfacl -m u:bob:r-- /var/www/html/private.html

# Grant rwx to a group on a directory
setfacl -m g:contractors:rwx /opt/shared/

# Set default ACL so new files inherit permissions
setfacl -d -m g:www-data:rx /var/www/html/

# Remove specific user's ACL
setfacl -x u:bob /var/www/html/private.html

# Remove all ACLs
setfacl -b /tmp/testfile

# Restore from backup
getfacl -R /var/www/ > acl-backup.txt
# ... after recovery ...
setfacl --restore=acl-backup.txt

# Mask: limits maximum permissions for named users/groups
setfacl -m m::r-x /shared/dir/
```

**Gotcha:** The ACL mask limits what named users/groups can actually do, regardless of their ACL entry. When you `chmod g+w` a file with ACLs, it modifies the mask, not the group ACL entry. Use `setfacl -n` if you need to set ACLs without recalculating the mask. ACLs require filesystem support (ext4, XFS, btrfs all support them). Check with `mount | grep acl` or `tune2fs -l /dev/sdX | grep features`.

---

### setuid / setgid / Sticky Bit

```bash
# setuid (4000): run executable as file owner
# Classic examples: passwd, sudo, ping
chmod u+s /usr/bin/myprog        # symbolic
chmod 4755 /usr/bin/myprog       # octal
ls -l /usr/bin/myprog
# -rwsr-xr-x    (lowercase s = setuid + execute set)
# -rwSr-xr-x    (uppercase S = setuid WITHOUT execute — warning!)

# setgid on file (2000): run as file group
chmod g+s /usr/bin/myprog
chmod 2755 /usr/bin/myprog

# setgid on directory: new files inherit directory's group
chmod g+s /var/www/shared/
chmod 2775 /var/www/shared/

# sticky bit on directory (1000): only file owner can delete
# Standard on /tmp
chmod +t /tmp
chmod 1777 /tmp
ls -ld /tmp
# drwxrwxrwt    (t = sticky + execute, T = sticky WITHOUT execute)

# Find all setuid files on system
find / -xdev -perm -4000 -type f 2>/dev/null
# Find setgid files
find / -xdev -perm -2000 -type f 2>/dev/null
```

**Gotcha:** A setuid bit on a shell script is **ignored** by the Linux kernel (security measure). Setuid only works on actual ELF executables. The uppercase `S` or `T` in `ls -l` output means the special bit is set but the execute bit is NOT — this is almost always unintentional and should be investigated.

---

## 5. Archives & Compression

### `tar` — Tape Archive

**Syntax:** `tar [OPERATION] [OPTIONS] [FILE]...`

#### Operations (mutually exclusive)

| Flag | Meaning |
|------|---------|
| `-c` | Create new archive |
| `-x` | Extract from archive |
| `-t` | List contents |
| `-r` | Append to archive |
| `-u` | Update (append only newer files) |
| `-A` | Concatenate archives |
| `-d` | Diff: compare archive with filesystem |

#### Common Options

| Flag | Meaning |
|------|---------|
| `-f FILE` | Archive filename (use `-` for stdin/stdout) |
| `-v` | Verbose |
| `-z` | Filter through gzip (`.tar.gz`, `.tgz`) |
| `-j` | Filter through bzip2 (`.tar.bz2`) |
| `-J` | Filter through xz (`.tar.xz`) |
| `--zstd` | Filter through zstd (`.tar.zst`) |
| `-p` | Preserve permissions |
| `--preserve-permissions` | Same as `-p` |
| `-P` | Preserve absolute paths (dangerous!) |
| `--strip-components=N` | Strip N leading path components on extract |
| `-C DIR` | Change to DIR before operation |
| `-X FILE` | Exclude files listed in FILE |
| `--exclude=PATTERN` | Exclude matching files/dirs |
| `--exclude-vcs` | Exclude VCS dirs (`.git`, `.svn`, etc.) |
| `--exclude-backups` | Exclude backup/temp files |
| `-h` | Dereference symlinks (archive content) |
| `--numeric-owner` | Use numeric UID/GID |
| `--same-owner` | Try to preserve ownership on extract |
| `--wildcards` | Enable globbing in `--exclude` |
| `--sparse` | Handle sparse files efficiently |
| `--checkpoint=N` | Display progress checkpoint every N records |
| `--totals` | Print totals at end |

**Examples:**
```bash
# Create a gzip-compressed archive
tar -czf archive.tar.gz /var/www/html/

# Extract to specific directory
tar -xzf archive.tar.gz -C /opt/restore/

# List contents without extracting
tar -tzf archive.tar.gz

# Create bzip2 archive (better compression, slower)
tar -cjf backup.tar.bz2 /home/alice/

# Create xz archive (best compression)
tar -cJf backup.tar.xz /home/alice/

# Extract only specific files
tar -xzf archive.tar.gz ./etc/nginx/nginx.conf

# Create archive excluding .git and node_modules
tar --exclude='.git' --exclude='node_modules' \
    --exclude-vcs -czf project.tar.gz /opt/myapp/

# Strip leading path components (common for extracting tarballs)
tar -xzf python-3.12.0.tar.gz --strip-components=1 -C /usr/local/

# Preserve permissions and ownership (as root)
tar -czpf full-backup.tar.gz --numeric-owner /etc/ /home/

# Pipe through network (no intermediate file)
tar -czf - /var/www/ | ssh user@backup-server 'cat > /backup/www.tar.gz'

# Split large archive
tar -czf - /bigdata/ | split -b 2G - backup.tar.gz.part

# Create archive with progress via pv
tar -cf - /var/www/ | pv | gzip > www.tar.gz

# Verify archive integrity
tar -tzf archive.tar.gz > /dev/null && echo "OK" || echo "CORRUPT"

# Update: append files newer than existing
tar -uf existing.tar newfile.txt

# Diff archive vs filesystem
tar -dzf archive.tar.gz
```

**Gotcha:** `tar -xzf archive.tar.gz` extracts to the CURRENT directory, creating whatever paths are in the archive. Always use `-t` first to inspect an untrusted archive — a "tarball bomb" can extract thousands of files into `/`. The `-P` (absolute path) flag is dangerous: archives created with it will overwrite absolute paths when extracted. By default GNU tar strips leading `/`.

---

### `gzip` / `gunzip`

**Syntax:** `gzip [OPTION]... [FILE]...`

| Flag | Meaning |
|------|---------|
| `-d` | Decompress (same as gunzip) |
| `-k` | Keep original file |
| `-c` | Write to stdout |
| `-r` | Recursive (compress files in directory tree) |
| `-l` | List compressed file info |
| `-v` | Verbose |
| `-t` | Test integrity |
| `-f` | Force (overwrite, compress already-compressed) |
| `-1` to `-9` | Compression level (1=fastest, 9=best) |
| `-n` | Don't save original filename/timestamp |
| `-N` | Save/restore original filename/timestamp |

**Examples:**
```bash
# Compress a file (replaces original)
gzip bigfile.log
# → bigfile.log.gz

# Compress keeping original
gzip -k bigfile.log

# Decompress
gunzip bigfile.log.gz
gzip -d bigfile.log.gz     # same thing

# Maximum compression
gzip -9 archive.tar

# Compress to stdout (pipe-friendly)
gzip -c access.log > /backup/access.log.gz

# List info about compressed file
gzip -l bigfile.log.gz

# Test integrity
gzip -t archive.tar.gz && echo "OK"

# Recursive compress a directory (compresses individual files)
gzip -r /var/log/old-logs/
```

**Gotcha:** `gzip` compresses individual files, it does not create archives. For directory archives, use `tar -z`. On large files, `pigz` (parallel gzip) is dramatically faster on multi-core systems: `pigz -p 4 bigfile.tar`.

---

### `bzip2`

**Syntax:** `bzip2 [OPTION]... [FILE]...`

| Flag | Meaning |
|------|---------|
| `-d` | Decompress |
| `-k` | Keep original |
| `-c` | Write to stdout |
| `-v` | Verbose |
| `-t` | Test integrity |
| `-f` | Force |
| `-1` to `-9` | Block size (compression level) |

**Examples:**
```bash
# Compress
bzip2 largefile.txt
# → largefile.txt.bz2

# Decompress
bunzip2 largefile.txt.bz2
bzip2 -d largefile.txt.bz2

# Keep original
bzip2 -k largefile.txt

# Stdout for piping
bzip2 -c < input.txt > output.txt.bz2
```

**Gotcha:** `bzip2` typically produces smaller files than gzip but is significantly slower. For CPU-bound environments, `pbzip2` provides parallel compression. bzip2 has block-level recovery — a corrupted `.bz2` can sometimes have undamaged blocks extracted with `bzip2recover`.

---

### `xz`

**Syntax:** `xz [OPTION]... [FILE]...`

| Flag | Meaning |
|------|---------|
| `-d` | Decompress |
| `-k` | Keep original |
| `-c` | Write to stdout |
| `-v` | Verbose |
| `-t` | Test integrity |
| `-l` | List info |
| `-f` | Force |
| `-0` to `-9` | Compression preset |
| `-e` | Extreme compression (slower, smaller) |
| `-T N` | Use N threads |

**Examples:**
```bash
# Best compression (slow but excellent ratio)
xz -9 -e kernel-source.tar

# Multithreaded compression
xz -T 4 -9 bigfile.tar

# Decompress
unxz file.tar.xz
xz -d file.tar.xz

# Info about compressed file
xz -l file.tar.xz
```

**Gotcha:** xz with `-9e` can use several GB of RAM. Use `-T 0` to automatically use all CPU threads. For `.tar.xz` files, always use `tar -xJf` rather than `xz -d` then `tar -xf` — it's faster due to streaming.

---

### `zip` / `unzip`

**Syntax:** `zip [OPTION]... ZIPFILE [FILE]...`  
**Syntax:** `unzip [OPTION]... ZIPFILE [FILE]... [-d DIR]`

#### zip options

| Flag | Meaning |
|------|---------|
| `-r` | Recursive |
| `-e` | Encrypt with password |
| `-P PWD` | Set password (insecure — use `-e`) |
| `-9` to `-0` | Compression level |
| `-u` | Update (add newer files) |
| `-d FILE` | Delete file from archive |
| `-v` | Verbose |
| `-j` | Junk paths (don't store directory names) |
| `-q` | Quiet |
| `-x PATTERN` | Exclude pattern |
| `--symlinks` | Store symlinks as symlinks |
| `-FS` | File sync (delete missing files from archive) |

#### unzip options

| Flag | Meaning |
|------|---------|
| `-l` | List contents |
| `-v` | Verbose list |
| `-t` | Test integrity |
| `-d DIR` | Extract to directory |
| `-o` | Overwrite without prompting |
| `-n` | Never overwrite |
| `-j` | Junk paths |
| `-q` | Quiet |
| `-P PWD` | Password |
| `-x PATTERN` | Exclude from extraction |

**Examples:**
```bash
# Create a zip archive
zip -r project.zip /opt/myapp/ -x '*.git*' -x '__pycache__/*'

# List contents
unzip -l archive.zip

# Extract to directory
unzip archive.zip -d /opt/restore/

# Test integrity
unzip -t archive.zip

# Extract specific file
unzip archive.zip config/settings.py

# Overwrite all without prompting
unzip -o update.zip -d /opt/app/

# Create encrypted zip
zip -er secrets.zip sensitive-dir/

# Add files to existing zip
zip existing.zip newfile.txt
```

**Gotcha:** zip does not preserve Unix permissions, symlinks, or hardlinks reliably across platforms. Use tar for Unix-to-Unix archiving. The zip format stores filenames as bytes, so non-ASCII filenames can have encoding issues between platforms.

---

### `7z` — 7-Zip

**Syntax:** `7z COMMAND [OPTIONS] ARCHIVE [FILES]...`

| Command | Meaning |
|---------|---------|
| `a` | Add (create/update) |
| `x` | Extract with full paths |
| `e` | Extract without paths |
| `l` | List |
| `t` | Test |
| `d` | Delete |
| `u` | Update |

| Option | Meaning |
|--------|---------|
| `-mx=N` | Compression level (0-9) |
| `-mmt=N` | Threads |
| `-p PASSWORD` | Set password |
| `-v SIZE` | Split into volumes |
| `-r` | Recursive |
| `-x!PATTERN` | Exclude |
| `-i!PATTERN` | Include only |
| `-so` | Write to stdout |
| `-si` | Read from stdin |

**Examples:**
```bash
# Create 7z archive with max compression
7z a -mx=9 archive.7z /opt/myapp/

# List contents
7z l archive.7z

# Extract
7z x archive.7z -o/opt/restore/

# Create encrypted archive
7z a -p'SecurePass123' -mhe=on secrets.7z sensitive/

# Split into 500MB volumes
7z a -v500m backup.7z /home/alice/

# Compress with multiple threads
7z a -mmt=4 -mx=9 archive.7z bigdir/
```

---

### `rsync` — Fast Incremental File Transfer

**Syntax:** `rsync [OPTION]... SRC [SRC]... DEST`

| Flag | Meaning |
|------|---------|
| `-a` | Archive mode: `-rlptgoD` (preserve almost everything) |
| `-r` | Recursive |
| `-v` | Verbose |
| `-z` | Compress during transfer |
| `-P` | `--progress --partial` (show progress, keep partial) |
| `--progress` | Show per-file progress |
| `-n`, `--dry-run` | Simulate, don't actually transfer |
| `--delete` | Delete destination files not in source |
| `--delete-before` | Delete before transfer |
| `--delete-after` | Delete after transfer |
| `-e CMD` | Use CMD as remote shell |
| `--exclude=PATTERN` | Exclude files |
| `--exclude-from=FILE` | Read exclude list from file |
| `--include=PATTERN` | Include (overrides exclude) |
| `--filter=RULE` | Combine include/exclude rules |
| `-b` | Backup modified files |
| `--backup-dir=DIR` | Where to put backups |
| `--suffix=SUFFIX` | Backup suffix (default `~`) |
| `-h` | Human-readable numbers |
| `--stats` | Print transfer statistics |
| `--checksum` | Skip based on checksum, not mtime/size |
| `--no-perms` | Don't preserve permissions |
| `--chmod=MODE` | Force permissions during transfer |
| `--chown=USER:GROUP` | Force ownership during transfer |
| `-l` | Copy symlinks as symlinks |
| `-L` | Transform symlinks into referents |
| `--bwlimit=KBPS` | Bandwidth limit |
| `--timeout=SECONDS` | Connection timeout |
| `--partial` | Keep partially transferred files |
| `--inplace` | Update files in-place |
| `--sparse` | Handle sparse files efficiently |
| `-W` | Whole-file (disable delta algorithm) |

**Examples:**
```bash
# Mirror a local directory (trailing slash = contents only)
rsync -av /source/dir/ /dest/dir/

# Same but delete files in dest not in source
rsync -av --delete /source/dir/ /dest/dir/

# Remote backup over SSH
rsync -avz -e ssh /var/www/ user@backup:/backup/www/

# Dry run to preview what would change
rsync -avn --delete /source/ /dest/

# Progress display for large transfers
rsync -avzP /large-data/ user@server:/backup/

# Exclude patterns
rsync -av --exclude='*.tmp' --exclude='.git/' /src/ /dst/

# With exclude file
rsync -av --exclude-from='/etc/rsync-excludes.txt' /src/ /dst/

# Preserve permissions, force ownership (for deployment)
rsync -av --chown=www-data:www-data --chmod=D755,F644 /src/ /var/www/

# Bandwidth-limited transfer
rsync -av --bwlimit=10240 /bigdata/ user@server:/backup/

# Incremental backup with versioned backup dir
rsync -av --backup --backup-dir="/backup/$(date +%Y%m%d)" \
    --delete /home/ /backup/current/
```

**Gotcha:** The trailing slash on source matters: `rsync -av /src/ /dst/` copies *contents* of `src` into `dst`. `rsync -av /src /dst/` copies the `src` *directory itself* into `dst`, creating `dst/src/`. This asymmetry with `cp -r` trips up many users. Use `--dry-run` before any `--delete` operation.

---

## 6. Disk & Filesystems

### `df` — Disk Free Space

**Syntax:** `df [OPTION]... [FILE]...`

| Flag | Meaning |
|------|---------|
| `-h` | Human-readable sizes |
| `-H` | Human-readable with powers of 1000 |
| `-T` | Show filesystem type |
| `-t TYPE` | Limit to filesystem type |
| `-x TYPE` | Exclude filesystem type |
| `-i` | Show inode usage instead of block usage |
| `-a` | Include all filesystems (including 0-block) |
| `-P` | POSIX output format (portable) |
| `--output=FIELDS` | Specify output fields |
| `-l` | Local filesystems only |

**Output fields for `--output`:** `source`, `fstype`, `size`, `used`, `avail`, `pcent`, `itotal`, `iused`, `iavail`, `ipcent`, `file`, `target`

**Examples:**
```bash
# All filesystems, human-readable with type
df -hT

# Specific path's filesystem
df -h /var/log

# Inode usage (critical when out of inodes but have disk space)
df -ih

# Exclude virtual filesystems
df -hT -x tmpfs -x devtmpfs -x squashfs

# Custom output
df --output=source,fstype,size,used,avail,pcent,target -h

# Monitor disk space in a loop (every 60s)
watch -n 60 'df -h'
```

**Gotcha:** "Disk full" errors can occur in two ways: blocks exhausted (shown by `df`) or inodes exhausted (shown by `df -i`). Check both when debugging. Docker and snap packages create many loop-device entries in `df` output — use `-x squashfs -x tmpfs` to clean up the view.

---

### `du` — Disk Usage

**Syntax:** `du [OPTION]... [FILE]...`

| Flag | Meaning |
|------|---------|
| `-h` | Human-readable |
| `-s` | Summary: total only, not per-subdirectory |
| `-a` | All: show files as well as directories |
| `-c` | Grand total |
| `-d N` | Max depth N (GNU) |
| `--max-depth=N` | Same as `-d N` |
| `-x` | Don't cross filesystem boundaries |
| `--exclude=PATTERN` | Exclude matching files |
| `--exclude-from=FILE` | Read exclusions from file |
| `-l` | Count hardlinks multiple times |
| `--inodes` | Show inode count instead of disk usage |
| `--apparent-size` | Show apparent size (not disk allocation) |
| `-b` | Bytes |
| `-k` | Kilobytes |
| `-m` | Megabytes |
| `-0` | NUL-delimited output |

**Examples:**
```bash
# Top 20 largest directories under /var
du -h --max-depth=2 /var | sort -rh | head -20

# Total size of current directory
du -sh .

# Size of each item in current directory, sorted
du -sh * | sort -rh

# Directory size excluding certain paths
du -sh --exclude='*.log' /var/log/

# Inode usage
du --inodes -s /var/

# Apparent vs actual size (important for sparse files)
du --apparent-size -sh bigfile.img
du -sh bigfile.img

# Don't cross filesystem boundaries
du -shx /

# Multiple directories with grand total
du -sch /var/log /var/cache /tmp
```

**Gotcha:** `du` reports allocated disk blocks (multiples of block size), not the apparent file size. A 1-byte file might report as 4KB. Use `--apparent-size` to see logical file sizes. Also, `du -sh /` on a system with bind mounts or tmpfs will show overlapping counts unless you use `-x`.

---

### `fdisk` — Partition Table Manipulation

**Syntax:** `fdisk [OPTION] DEVICE`

| Flag | Meaning |
|------|---------|
| `-l` | List partition tables |
| `-u` | Sectors instead of cylinders |
| `-b SECTORS` | Sector size |
| `-H HEADS` | Heads for geometry |
| `-S SECTORS` | Sectors per track |

**Examples:**
```bash
# List all partitions
fdisk -l

# List specific device
fdisk -l /dev/sda

# Interactive partition editor
fdisk /dev/sdb
# Interactive commands: n=new, d=delete, p=print, w=write, q=quit, t=type, a=bootable

# List in bytes
fdisk -l -u=bytes /dev/sda
```

**Gotcha:** `fdisk` modifies the in-memory partition table. Changes take effect after `w` (write). The kernel may need a reboot or `partprobe`/`kpartx` to recognize new partitions. `fdisk` does not support GPT well — use `gdisk` for GPT disks or `parted` for a unified tool.

---

### `parted` — Disk Partitioning

**Syntax:** `parted [OPTION] [DEVICE] [COMMAND]`

| Command | Meaning |
|---------|---------|
| `print` | Display partition table |
| `mklabel TYPE` | Create partition table (gpt, msdos) |
| `mkpart TYPE START END` | Create partition |
| `rm NUM` | Delete partition |
| `resizepart NUM END` | Resize partition |
| `name NUM NAME` | Set partition name (GPT) |
| `set NUM FLAG STATE` | Set flag (boot, esp, swap, lvm, raid) |
| `align-check TYPE NUM` | Check partition alignment |
| `rescue START END` | Rescue lost partition |

**Examples:**
```bash
# Print partition table
parted /dev/sda print

# Create GPT table and partitions (non-interactive, scriptable)
parted /dev/sdb --script \
    mklabel gpt \
    mkpart primary 1MiB 512MiB \
    mkpart primary 512MiB 100%

# Set ESP flag for EFI partition
parted /dev/sdb set 1 esp on

# Resize partition
parted /dev/sdb resizepart 2 100%

# Check optimal alignment
parted /dev/sdb align-check optimal 1
```

**Gotcha:** `parted` uses SI units by default (`MB` = 10^6 bytes). Use `MiB` for binary units (2^20). Misaligned partitions cause severe performance loss on SSDs — always align to at least 1MiB boundaries.

---

### `mount` / `umount`

**Syntax:** `mount [OPTION]... DEVICE MOUNTPOINT`  
**Syntax:** `umount [OPTION]... DEVICE|MOUNTPOINT`

| Flag (mount) | Meaning |
|------|---------|
| `-t TYPE` | Filesystem type |
| `-o OPTIONS` | Mount options (comma-separated) |
| `-r` | Read-only |
| `-w` | Read-write (default) |
| `-n` | Don't update `/etc/mtab` |
| `-a` | Mount all from `/etc/fstab` |
| `-v` | Verbose |
| `--bind` | Bind mount |
| `--rbind` | Recursive bind mount |
| `--make-shared` | Make mount point shared |
| `--make-private` | Make mount point private |

**Common mount options (`-o`):**

| Option | Meaning |
|--------|---------|
| `ro` | Read-only |
| `rw` | Read-write |
| `noexec` | No execution |
| `nosuid` | Ignore setuid bits |
| `nodev` | No device files |
| `relatime` | Update atime only if older than mtime (default) |
| `noatime` | Never update atime (performance) |
| `sync` | Synchronous writes |
| `async` | Asynchronous writes (default) |
| `remount` | Remount with new options |
| `bind` | Bind mount |
| `loop` | Use loop device |
| `uid=N,gid=N` | Override owner (FAT/NTFS) |
| `umask=MASK` | Permissions mask (FAT/NTFS) |

**Examples:**
```bash
# Mount a disk partition
mount /dev/sdb1 /mnt/data

# Mount an ISO image
mount -o loop /path/to/image.iso /mnt/iso

# Read-only mount
mount -o ro /dev/sdb1 /mnt/data

# Bind mount (expose directory at another path)
mount --bind /var/www/html /home/alice/public_html

# Remount root read-write (recovery)
mount -o remount,rw /

# Mount NFS share
mount -t nfs4 server:/export/share /mnt/nfs

# Mount with noexec,nosuid,nodev for security
mount -o noexec,nosuid,nodev /dev/sdb1 /mnt/data

# Show all mounts
mount | column -t

# Unmount
umount /mnt/data

# Lazy unmount (detach from filesystem, cleanup when idle)
umount -l /mnt/nfs

# Force unmount (dangerous, use only when lazy fails)
umount -f /mnt/nfs
```

**Gotcha:** "Device is busy" on `umount` means a process has an open file or current directory there. Use `lsof +D /mountpoint` or `fuser -m /mountpoint` to find the culprit. `umount -l` (lazy) detaches the mount immediately but cleans up only when all references are released — useful for NFS that became unreachable.

---

### `lsblk` — List Block Devices

**Syntax:** `lsblk [OPTION]... [DEVICE]...`

| Flag | Meaning |
|------|---------|
| `-a` | Include empty devices |
| `-f` | Show filesystem info |
| `-m` | Show permissions |
| `-o COLS` | Specify output columns |
| `-p` | Print full device paths |
| `-r` | Raw format |
| `-J` | JSON output |
| `-P` | Pairs format (key=value) |
| `-T` | Tree format |
| `-l` | List format (no tree) |
| `-d` | Don't print device holders |
| `-S` | SCSI info |
| `-t` | Topology info |
| `-b` | Bytes for SIZE |

**Available columns:** `NAME`, `KNAME`, `MAJ:MIN`, `FSTYPE`, `FSVER`, `LABEL`, `UUID`, `FSAVAIL`, `FSUSE%`, `MOUNTPOINT`, `MODEL`, `SERIAL`, `SIZE`, `STATE`, `OWNER`, `GROUP`, `MODE`, `TRAN`, `TYPE`, `ROTA`, `SCHED`, `RQ-SIZE`, `RM`, `HOTPLUG`, `ALIGNMENT`, `MIN-IO`, `OPT-IO`, `PHY-SEC`, `LOG-SEC`, `RAND`, `PKNAME`, `HCTL`, `VENDOR`, `REV`, `SUBSYSTEMS`, `ZONED`, `WWN`, `PTUUID`, `PTTYPE`

**Examples:**
```bash
# Show all block devices with filesystem info
lsblk -f

# Custom columns
lsblk -o NAME,SIZE,FSTYPE,LABEL,MOUNTPOINT,UUID

# Show rotation (SSD vs HDD)
lsblk -o NAME,ROTA,SIZE,MODEL

# JSON output for scripting
lsblk -J -o NAME,SIZE,TYPE,FSTYPE

# Specific device tree
lsblk /dev/sda
```

---

### `blkid` — Print Block Device Attributes

**Syntax:** `blkid [OPTION]... [DEVICE]...`

| Flag | Meaning |
|------|---------|
| `-o FORMAT` | Output format: `full`, `value`, `udev`, `export` |
| `-s TAG` | Show only specified tag |
| `-t NAME=VALUE` | Find device with matching tag |
| `-g` | Garbage-collect (remove stale entries) |
| `-p` | Low-level probe (bypass cache) |
| `-i` | Show I/O limits |
| `-U UUID` | Find device by UUID |
| `-L LABEL` | Find device by label |

**Examples:**
```bash
# List all block devices with UUIDs
blkid

# Get UUID of a specific device
blkid -s UUID -o value /dev/sda1

# Find device by UUID (for fstab verification)
blkid -U "550e8400-e29b-41d4-a716-446655440000"

# Find by label
blkid -L "DATA"

# Low-level probe (bypass cache)
blkid -p /dev/sdb1

# Export format for scripting
blkid -o export /dev/sda1
```

**Gotcha:** `blkid` uses a cache file (`/run/blkid/blkid.tab`) to avoid constant re-reads. Use `-p` to force a fresh probe when you've just formatted a partition. Always use UUID (not `/dev/sdX`) in `/etc/fstab` — device names can change on reboot.

---

### `fsck` — Filesystem Check and Repair

**Syntax:** `fsck [OPTION]... [FILESYSTEM]...`

| Flag | Meaning |
|------|---------|
| `-A` | Check all filesystems in `/etc/fstab` |
| `-T` | Don't show title |
| `-M` | Don't check mounted filesystems |
| `-N` | Dry run |
| `-P` | Check filesystems in parallel |
| `-R` | Skip root filesystem (with `-A`) |
| `-V` | Verbose |
| `-a` | Auto-repair (no questions) |
| `-n` | No repairs, just show problems |
| `-y` | Yes to all repair questions |
| `-t TYPE` | Specify filesystem type |
| `-f` | Force check even if marked clean |
| `-C [FD]` | Progress bar |

**Examples:**
```bash
# Check and repair a filesystem (must be unmounted!)
umount /dev/sdb1
fsck -y /dev/sdb1

# Force check even if clean
fsck -f /dev/sdb1

# Check without repair (report only)
fsck -n /dev/sdb1

# Check all fstab filesystems on boot
fsck -A -M

# ext4 specific check
e2fsck -p /dev/sdb1   # auto-fix
e2fsck -y /dev/sdb1   # answer yes to all

# Force fsck on next reboot (for root FS)
touch /forcefsck
# or
tune2fs -C 1 /dev/sda1    # set mount count to trigger check
```

**Gotcha:** NEVER run `fsck` on a mounted filesystem (except root in read-only emergency mode). It can corrupt data. To force a root filesystem check on next boot, use `touch /forcefsck` or set a high mount count with `tune2fs`. The `-y` flag blindly answers "yes" to all repair questions — use cautiously on important data.

---

### `mkfs` — Make Filesystem

**Syntax:** `mkfs [-t TYPE] [OPTIONS] DEVICE [SIZE]`

| Command | Creates |
|---------|---------|
| `mkfs.ext4` | ext4 filesystem |
| `mkfs.ext3` | ext3 filesystem |
| `mkfs.xfs` | XFS filesystem |
| `mkfs.btrfs` | Btrfs filesystem |
| `mkfs.vfat` | FAT32 filesystem |
| `mkfs.ntfs` | NTFS filesystem |
| `mkfs.f2fs` | F2FS (for NAND flash) |

**Examples:**
```bash
# Create ext4 filesystem
mkfs.ext4 /dev/sdb1

# ext4 with label and specific options
mkfs.ext4 -L "BACKUP" -m 1 -E lazy_itable_init=0 /dev/sdb1

# XFS filesystem (preferred for large files and high throughput)
mkfs.xfs -f /dev/sdb1
mkfs.xfs -L "DATA" /dev/sdb1

# Btrfs with label
mkfs.btrfs -L "STORAGE" /dev/sdb1

# FAT32 (for USB drives, EFI partitions)
mkfs.vfat -F 32 -n "USB" /dev/sdb1

# Swap partition
mkswap /dev/sdb2
swapon /dev/sdb2
```

**Gotcha:** `mkfs` is destructive — it permanently destroys all data on the device. The `-f` flag on `mkfs.xfs` is needed to overwrite an existing filesystem. After `mkfs`, get the new UUID with `blkid` and update `/etc/fstab` accordingly.

---

## 7. File Content

### `cat` — Concatenate and Print Files

**Syntax:** `cat [OPTION]... [FILE]...`

| Flag | Meaning |
|------|---------|
| `-n` | Number all output lines |
| `-b` | Number non-blank lines only |
| `-A` | Show all: equivalent to `-vET` |
| `-v` | Show non-printing characters (except tab/newline) |
| `-E` | Show `$` at end of each line (reveal trailing spaces) |
| `-T` | Show tabs as `^I` |
| `-s` | Squeeze multiple blank lines into one |

**Examples:**
```bash
# Display a file
cat /etc/hostname

# Display with line numbers
cat -n /etc/nginx/nginx.conf

# Show hidden whitespace (debug trailing spaces, tabs)
cat -A suspicious-script.sh

# Concatenate files
cat file1.txt file2.txt file3.txt > combined.txt

# Append to file
cat extra.conf >> main.conf

# Create file from stdin
cat > newfile.txt << 'EOF'
line one
line two
EOF

# View binary file, show control chars
cat -v binary-dump.bin | head -20
```

**Gotcha:** `cat file | command` is a "Useless Use of Cat" (UUOC) — prefer `command < file` or `command file` when the command accepts a filename. However, `cat` is appropriate when concatenating multiple files or piping with other operations. Never use `cat` to read binary files into variables — use `mapfile` or `read`.

---

### `tac` — Reverse Cat (Print Lines in Reverse)

**Syntax:** `tac [OPTION]... [FILE]...`

| Flag | Meaning |
|------|---------|
| `-b` | Attach separator before instead of after |
| `-r` | Interpret separator as regex |
| `-s SEP` | Use SEP as separator instead of newline |

**Examples:**
```bash
# Reverse line order of a file
tac access.log

# Last 10 events in chronological reverse
tac /var/log/auth.log | head -10

# Reverse records separated by blank lines
tac -s '' -r file.txt
```

---

### `less` — Paginated File Viewer

**Syntax:** `less [OPTION]... [FILE]...`

| Flag | Meaning |
|------|---------|
| `-N` | Show line numbers |
| `-S` | Don't wrap long lines (chop/truncate) |
| `-R` | Display raw ANSI color codes |
| `-i` | Case-insensitive search |
| `-I` | Case-insensitive search (even for uppercase patterns) |
| `-F` | Quit if content fits on one screen |
| `-X` | Don't clear screen on exit |
| `-G` | Don't highlight search matches |
| `+N` | Start at line N |
| `+/PATTERN` | Start at first match of PATTERN |
| `-p PATTERN` | Start at PATTERN |

**Key bindings inside less:**

| Key | Action |
|-----|--------|
| `Space`, `f` | Forward one page |
| `b` | Backward one page |
| `d` | Forward half page |
| `u` | Backward half page |
| `j`, `↓` | Forward one line |
| `k`, `↑` | Backward one line |
| `g` | Go to beginning |
| `G` | Go to end |
| `Ng` | Go to line N |
| `/pattern` | Search forward |
| `?pattern` | Search backward |
| `n` | Next search match |
| `N` | Previous search match |
| `&pattern` | Show only matching lines |
| `=` | Show file info and position |
| `q` | Quit |
| `F` | Follow mode (like `tail -f`) |
| `-N` | Toggle line numbers |
| `v` | Open in editor (`$VISUAL` or `$EDITOR`) |

**Examples:**
```bash
# View with line numbers and color support
less -NR /var/log/syslog

# Start at end of file (like tail)
less +G /var/log/nginx/access.log

# Start at first match
less +/ERROR /var/log/app.log

# View a compressed log without extracting
zless /var/log/syslog.1.gz

# Pipe output through less
journalctl -u nginx | less -R

# View without wrapping (useful for wide CSV/SQL output)
less -S report.csv
```

**Gotcha:** `less` is the preferred pager over `more` because it allows backward scrolling. Set `LESS=-R` in your environment to always enable color passthrough. The `F` key in less provides `tail -f`-like functionality — use it to monitor logs interactively.

---

### `more` — Simple Paginator

**Syntax:** `more [OPTION]... [FILE]...`

| Flag | Meaning |
|------|---------|
| `-N` | Show N lines per page |
| `-d` | Display user prompts |
| `-f` | Count logical lines (not screen lines) |
| `+N` | Start at line N |
| `+/PATTERN` | Start at PATTERN |

**Note:** `less` supersedes `more` in almost all cases. Use `more` only when `less` is unavailable (minimal systems, busybox environments) or when you want forward-only paging behavior for scripts.

---

### `head` — Output First Lines

**Syntax:** `head [OPTION]... [FILE]...`

| Flag | Meaning |
|------|---------|
| `-n N` | First N lines (default 10) |
| `-n -N` | All lines except last N |
| `-c N` | First N bytes |
| `-c -N` | All bytes except last N |
| `-q` | Quiet: no headers for multiple files |
| `-v` | Verbose: always print headers |

**Examples:**
```bash
# First 20 lines
head -n 20 /var/log/syslog

# First 1MB
head -c 1048576 bigfile.bin > first-mb.bin

# All lines except the last header line
head -n -1 data-with-footer.csv

# Preview first 5 lines of multiple files
head -n 5 *.conf
```

---

### `tail` — Output Last Lines

**Syntax:** `tail [OPTION]... [FILE]...`

| Flag | Meaning |
|------|---------|
| `-n N` | Last N lines (default 10) |
| `-n +N` | From line N onwards |
| `-c N` | Last N bytes |
| `-c +N` | From byte N onwards |
| `-f` | Follow: output appended data as file grows |
| `-F` | Follow by name: re-open if file is rotated |
| `-s N` | Sleep interval for `-f` (default 1s) |
| `--pid=PID` | Terminate following when PID dies |
| `-q` | Quiet: no file headers |
| `-v` | Verbose: always print file headers |

**Examples:**
```bash
# Live monitoring of nginx access log
tail -f /var/log/nginx/access.log

# Follow log file by name (survives log rotation)
tail -F /var/log/nginx/access.log

# Follow multiple files simultaneously
tail -f /var/log/nginx/access.log /var/log/nginx/error.log

# Follow process log and stop when process exits
tail -f --pid=$APP_PID /var/log/myapp.log

# Skip header line (from line 2 onwards)
tail -n +2 data.csv

# Last 50 lines with timestamps visible
tail -n 50 /var/log/syslog

# Combine: skip first line, then take first 10 of remaining
tail -n +2 data.csv | head -n 10

# Monitor log with grep filter (efficient — grep happens on tail output)
tail -f /var/log/auth.log | grep --line-buffered 'Failed password'
```

**Gotcha:** `tail -f` follows the file descriptor — if the file is deleted and recreated (log rotation), it continues reading the old (now unlinked) file. Use `tail -F` to follow by filename, which re-opens the file when it disappears and reappears. Add `--line-buffered` to `grep` in a pipeline with `tail -f` to prevent grep from buffering output.

---

### `wc` — Word, Line, Character Count

**Syntax:** `wc [OPTION]... [FILE]...`

| Flag | Meaning |
|------|---------|
| `-l` | Lines only |
| `-w` | Words only |
| `-c` | Bytes only |
| `-m` | Characters (multi-byte aware) |
| `-L` | Length of longest line |
| `--files0-from=FILE` | Read null-separated filenames from FILE |

**Examples:**
```bash
# Full count (lines, words, bytes)
wc /etc/passwd
# 37 74 2215 /etc/passwd

# Count log lines
wc -l /var/log/nginx/access.log

# Count files in a directory
ls /etc | wc -l

# Find the longest line length
wc -L /etc/nginx/nginx.conf

# Count words in multiple files with total
wc -w *.md

# Count unique lines in a log
sort -u /var/log/auth.log | wc -l
```

---

### `od` — Octal Dump

**Syntax:** `od [OPTION]... [FILE]...`

| Flag | Meaning |
|------|---------|
| `-t TYPE` | Output type: `x`=hex, `d`=decimal, `o`=octal, `c`=ASCII+escape, `a`=ASCII names |
| `-c` | Display as characters with C-style escapes |
| `-x` | Hexadecimal words (equivalent to `-t x2`) |
| `-A RADIX` | Address radix: `d`=decimal, `x`=hex, `o`=octal, `n`=none |
| `-j N` | Skip first N bytes |
| `-N N` | Read only N bytes |
| `-w N` | Output N bytes per line |
| `-v` | Output all data (no `*` for repeated lines) |
| `-s N` | Only output strings of at least N chars |

**Examples:**
```bash
# Hex dump of first 32 bytes
od -A x -t x1z -N 32 /bin/ls

# View as characters with escapes (debug binary files)
od -c /etc/hostname

# Dump with decimal addresses
od -A d -t x1 file.bin | head -20

# Look for printable strings in a binary
od -c binary.dat | grep -A1 '\\0'

# Skip 512 bytes, read 256 bytes
od -j 512 -N 256 -t x1 disk.img
```

---

### `xxd` — Hex Dump with ASCII Sidecar

**Syntax:** `xxd [OPTION]... [FILE [OUTFILE]]`

| Flag | Meaning |
|------|---------|
| `-l N` | Stop after N bytes |
| `-s +N` | Skip N bytes from start |
| `-s -N` | Start N bytes from end |
| `-c N` | N bytes per line (default 16) |
| `-g N` | Group bytes into N-byte chunks |
| `-r` | Reverse: hex dump back to binary |
| `-b` | Binary digit dump instead of hex |
| `-i` | Output as C include file |
| `-p` | Plain hex (no address or ASCII) |
| `-u` | Uppercase hex |
| `-e` | Little-endian |
| `-E` | Use EBCDIC for ASCII column |
| `-d` | Use decimal offset |

**Examples:**
```bash
# Standard hex+ASCII dump
xxd /bin/bash | head -20

# Dump as plain hex (no addresses/ASCII)
xxd -p /etc/hostname

# Dump first 64 bytes
xxd -l 64 /bin/bash

# 4-byte grouping for 32-bit word viewing
xxd -g 4 firmware.bin | head -20

# Convert hex back to binary
echo '48656c6c6f0a' | xxd -r -p > hello.bin

# Patch a binary (hex edit workflow)
xxd binary.bin > binary.hex
# edit binary.hex in editor
xxd -r binary.hex > binary-patched.bin

# Generate C array for embedding binary data
xxd -i image.png > image_data.c
```

**Gotcha:** `xxd -r` requires the format to be exactly as `xxd` produces it (with addresses). For plain hex-to-binary, use `xxd -r -p` which accepts plain hex without addresses or ASCII columns.

---

### `strings` — Extract Printable Strings from Binary

**Syntax:** `strings [OPTION]... FILE...`

| Flag | Meaning |
|------|---------|
| `-n N` | Minimum string length (default 4) |
| `-t FORMAT` | Print offset: `x`=hex, `d`=decimal, `o`=octal |
| `-a` | Scan entire file (default) |
| `-e ENCODING` | Character encoding: `s`=7-bit, `S`=8-bit, `b`=16bit-big-endian, `l`=16bit-little-endian |
| `-w` | Include whitespace in strings |
| `-o` | Same as `-t o` |
| `-T` | Treat file as BFD object |
| `-f` | Print filename before each string |

**Examples:**
```bash
# Extract strings from binary
strings /bin/bash | head -30

# Find strings 8+ characters long with offsets
strings -n 8 -t x suspicious.exe

# Extract Unicode (UTF-16 LE) strings from Windows binary
strings -e l malware.exe | grep -i 'http'

# Find embedded URLs
strings binary.so | grep -E 'https?://'

# Find potential hardcoded credentials
strings application.jar | grep -iE 'password|secret|apikey|token'

# Include whitespace-containing strings (longer minimum)
strings -n 10 -w firmware.bin | head -50
```

---

### `file` (binary content)

See the `file` entry in [Section 2](#file--determine-file-type) — it identifies binary formats by magic number inspection.

---

## Quick Reference: Permission Bits

```
Octal  Binary  Symbolic  Meaning
  7    111     rwx       read + write + execute
  6    110     rw-       read + write
  5    101     r-x       read + execute
  4    100     r--       read only
  3    011     -wx       write + execute
  2    010     -w-       write only
  1    001     --x       execute only
  0    000     ---       no permissions

Special bits (prefix to 3-digit octal):
  4xxx   setuid       (4755 = rwsr-xr-x)
  2xxx   setgid       (2755 = rwxr-sr-x)
  1xxx   sticky       (1777 = rwxrwxrwt)
  6xxx   setuid+setgid
```

## Quick Reference: find Expressions Cheat Sheet

```bash
# Age
-mtime -1          # modified < 1 day ago
-mtime +30         # modified > 30 days ago
-mmin -60          # modified < 60 minutes ago
-newer /tmp/ref    # newer than ref file

# Size
-size +1M          # > 1 MiB
-size -100k        # < 100 KiB
-size +1G          # > 1 GiB
-empty             # zero-length

# Type
-type f            # regular file
-type d            # directory
-type l            # symlink
-type s            # socket

# Permissions
-perm 644          # exactly 644
-perm -644         # all of 644 bits set
-perm /111         # any execute bit set
-perm -4000        # setuid set

# Actions
-delete            # delete match
-ls                # detailed listing
-exec CMD {} \;    # run once per match
-exec CMD {} +     # run batched
-print0            # NUL-delimited output
-prune             # don't descend
```

## Quick Reference: tar Mode Cheat Sheet

```bash
# Create
tar -czf  file.tar.gz   dir/   # gzip
tar -cjf  file.tar.bz2  dir/   # bzip2
tar -cJf  file.tar.xz   dir/   # xz
tar -cf   file.tar      dir/   # no compression

# Extract
tar -xzf  file.tar.gz   -C /dest/   # gzip → dir
tar -xjf  file.tar.bz2  -C /dest/   # bzip2 → dir
tar -xJf  file.tar.xz   -C /dest/   # xz → dir

# List
tar -tzf  file.tar.gz              # list contents

# Common extras
--exclude='.git'                   # exclude pattern
--strip-components=1               # strip top dir
--numeric-owner                    # preserve numeric ids
-p                                 # preserve permissions
```
