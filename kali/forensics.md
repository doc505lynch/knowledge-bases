# Forensics Tools

## binwalk
**Category:** Forensics
**Description:** Firmware analysis and extraction tool. Scans binary files for embedded file signatures, executable code, and entropy analysis.
**Version:** 2.4.3 (also binwalk3 3.1.0 available)
**Common Usage:** `binwalk <file>` | `binwalk -e <file>` | `binwalk -Me <file>` (recursive extraction)
**Key Flags:**
- `-B` / `--signature` — Scan for common file signatures (default behavior)
- `-e` / `--extract` — Automatically extract known file types
- `-M` / `--matryoshka` — Recursively scan extracted files (nested extraction)
- `-d <n>` / `--depth=<n>` — Limit recursion depth (default: 8)
- `-C <dir>` / `--directory=<dir>` — Extract to custom directory
- `-E` / `--entropy` — Calculate file entropy
- `-J` / `--save` — Save entropy plot as PNG
- `-Y` / `--disasm` — Identify CPU architecture (capstone disassembler)
- `-A` / `--opcodes` — Scan for executable opcode signatures
- `-W` / `--hexdump` — Hex dump / diff of a file or files
- `-R <str>` / `--raw=<str>` — Scan for raw byte sequence
- `-x <str>` / `--exclude=<str>` — Exclude results matching string
- `-y <str>` / `--include=<str>` — Only show results matching string
- `-r` / `--rm` — Delete carved files after extraction
**Help Output:**
```
Binwalk v2.4.3

Usage: binwalk [OPTIONS] [FILE1] [FILE2] [FILE3] ...

Disassembly Scan Options:
    -Y, --disasm                 Identify the CPU architecture using capstone
    -k, --continue               Don't stop at the first match

Signature Scan Options:
    -B, --signature              Scan target file(s) for common file signatures
    -R, --raw=<str>              Scan for the specified sequence of bytes
    -A, --opcodes                Scan for common executable opcode signatures
    -x, --exclude=<str>          Exclude results that match <str>
    -y, --include=<str>          Only show results that match <str>

Extraction Options:
    -e, --extract                Automatically extract known file types
    -M, --matryoshka             Recursively scan extracted files
    -d, --depth=<int>            Limit matryoshka recursion depth (default: 8)
    -C, --directory=<str>        Extract files/folders to a custom directory
    -r, --rm                     Delete carved files after extraction
    -z, --carve                  Carve data from files, but don't execute extraction utilities

Entropy Options:
    -E, --entropy                Calculate file entropy
    -J, --save                   Save plot as a PNG
    -H, --high=<float>           Rising edge entropy trigger (default: 0.95)
    -L, --low=<float>            Falling edge entropy trigger (default: 0.85)

Binary Diffing Options:
    -W, --hexdump                Perform a hexdump / diff of a file or files
```

**Common usage examples:**
```bash
# Scan firmware for embedded files
binwalk firmware.bin

# Extract all embedded files
binwalk -e firmware.bin

# Recursive extraction of all nested files
binwalk -Me firmware.bin

# Entropy analysis (high entropy = compressed/encrypted)
binwalk -E firmware.bin

# Hexdump diff between two files
binwalk -W file1.bin file2.bin
```
---

## sleuthkit
**Category:** Forensics
**Description:** Collection of command-line digital forensic tools for investigating disk images. The backend for the Autopsy GUI.
**Version:** 4.12.1
**Key Tools:**
- `fls` — List files and directory names in a disk image
- `icat` — Output the contents of a file by inode number
- `fsstat` — Display file system details and statistics
- `mmls` — Display partition table layout
- `img_stat` — Display details of an image file
- `blkcat` — Display contents of disk blocks
- `blkls` — List or copy block contents of a file system
- `tsk_recover` — Recover files from disk image (including deleted)
- `tsk_loaddb` — Load disk image into SQLite database for analysis
- `sorter` — Sort files in a disk image by type
- `sigfind` — Find signature in a disk image

**Common usage examples:**
```bash
# List partition table
mmls disk.img

# List all files (including deleted) in partition
fls -r -o <partition_offset> disk.img

# Extract file by inode
icat -o <partition_offset> disk.img <inode_number> > recovered_file

# Recover all recoverable files from image
tsk_recover -e disk.img output_dir/

# File system statistics
fsstat -o <offset> disk.img
```
---

## bulk-extractor
**Category:** Forensics
**Description:** Scans disk images, files, or directories for email addresses, URLs, credit card numbers, IP addresses, phone numbers, and other features — without mounting the image.
**Version:** 2.1.1
**Common Usage:** `bulk-extractor -o <outdir> <image>`
**Key Flags:**
- `-o <dir>` — Output directory (required)
- `-E all` — Enable all scanners
- `-S <name=value>` — Set scanner-specific option
- `-x <scanner>` — Disable a specific scanner
- `-e <scanner>` — Enable a specific scanner
- `-j <n>` — Number of threads
- `-r <file>` — Recurse into file (for zip/gzip/etc)
- `-R <dir>` — Recursively process directory
- `--reprocess` — Reprocess a previous output directory
**Output files include:**
- `email.txt` — Email addresses found
- `url.txt` — URLs found
- `creditcard.txt` — Credit card numbers
- `telephone.txt` — Phone numbers
- `ip_histogram.txt` — IP addresses
- `domain.txt` — Domain names
- `json.txt` — JSON objects

**Common usage examples:**
```bash
# Scan disk image
bulk-extractor -o results/ disk.img

# Scan with all scanners enabled
bulk-extractor -E all -o results/ disk.img

# Scan a directory
bulk-extractor -R /mnt/suspicious -o results/
```
---

## scalpel
**Category:** Forensics
**Description:** File carver that reads a database of header and footer definitions and extracts matching files from disk images regardless of file system.
**Version:** 1.60
**Common Usage:** `scalpel -o <outdir> <image>`
**Key Flags:**
- `-o <dir>` — Output directory
- `-c <config>` — Config file (default /etc/scalpel/scalpel.conf)
- `-b` — Carve files from unallocated space only
- `-q` — Carve files from allocated space only
- `-r` — Recurse into subdirectories
- `-n` — Do not add extensions (use header-only carving)
**Note:** Edit `/etc/scalpel/scalpel.conf` to uncomment file types to carve.
---

## testdisk
**Category:** Forensics
**Description:** Powerful disk partition recovery and undelete tool that can fix partition tables and recover deleted files from FAT, NTFS, ext2/3/4, and other file systems.
**Version:** 7.2
**Common Usage:** `testdisk [disk_image]`
**PhotoRec:** Also includes `photorec` for recovering photos and documents from disk images.

**Key capabilities:**
- Fix/rebuild partition tables
- Recover deleted FAT/NTFS/ext2/ext3/ext4 files
- Recover lost partitions
- Undelete FAT and NTFS files
- Copy files from damaged file systems
---

## foremost / magicrescue
**Category:** Forensics
**Note:** `foremost` is NOT installed. Use `scalpel` as an alternative for file carving, or `magicrescue` (version 1.1.10, installed).

**magicrescue** — Scans a block device for file types it knows how to recover, based on "recipes" in `/usr/share/magicrescue/recipes/`.
**Common Usage:** `magicrescue -r <recipe> -d <outdir> <device>`
---

## hashdeep
**Category:** Forensics
**Description:** Recursively computes hashes for files and directories. Supports MD5, SHA1, SHA256, Tiger, and Whirlpool.
**Version:** 4.4
**Common Usage:** `hashdeep -r <directory>` | `hashdeep -r -a -k known.hashes /path`
**Key Flags:**
- `-r` — Recursive mode
- `-a` — Audit mode (compare against known hashes)
- `-k <file>` — File containing known hashes
- `-m` — Match mode (only print matched hashes)
- `-x` — Negative match mode (only print non-matched hashes)
- `-c <alg>` — Hash algorithm: md5, sha1, sha256, tiger, whirlpool

**Common usage examples:**
```bash
# Hash all files recursively
hashdeep -r /suspicious/files/ > hashes.txt

# Audit against known-good hash set
hashdeep -r -a -k known_hashes.txt /suspicious/
```
---

## Volatility (NOT installed)
**Note:** Neither `volatility3`, `vol`, nor `vol.py` are installed in this container. For memory forensics, you would need to install volatility3 manually:
```bash
pip3 install volatility3
# or
git clone https://github.com/volatilityfoundation/volatility3
```
---
