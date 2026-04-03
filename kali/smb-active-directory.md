# SMB & Active Directory Tools

## netexec (nxc)
**Category:** SMB/Active Directory
**Description:** The successor to CrackMapExec (crackmapexec/cme). Network execution tool for pentesting Active Directory environments across multiple protocols.
**Version:** 1.5.1
**Note:** `crackmapexec` is NOT installed; use `netexec` or `nxc` instead.
**Common Usage:** `netexec smb <target> -u <user> -p <pass>` | `nxc smb <target> -u <user> -p <pass>`
**Supported Protocols:** smb, ldap, winrm, mssql, ssh, ftp, rdp, vnc, wmi, nfs
**Key Flags:**
- `-u <user>` — Username or username list
- `-p <pass>` — Password or password list
- `-H <hash>` — NTLM hash for pass-the-hash
- `-d <domain>` — Domain
- `--shares` — Enumerate SMB shares
- `--users` — Enumerate users
- `--groups` — Enumerate groups
- `--sam` — Dump SAM database (requires admin)
- `--lsa` — Dump LSA secrets (requires admin)
- `--ntds` — Dump NTDS.dit (DC only, requires admin)
- `-x <cmd>` — Execute command via cmd.exe
- `-X <cmd>` — Execute PowerShell command
- `--local-auth` — Authenticate locally (not domain)
- `--pass-pol` — Get password policy
- `--continue-on-success` — Continue spraying even after finding a valid credential
**Help Output:**
```
usage: netexec [-h] [--version] [-t THREADS] [--timeout TIMEOUT]
               [--jitter INTERVAL] [--no-progress] [--log LOG] [--verbose | --debug]
               [-6] [--dns-server DNS_SERVER] [--dns-tcp] [--dns-timeout DNS_TIMEOUT]
               {rdp,ldap,nfs,smb,winrm,vnc,mssql,wmi,ftp,ssh} ...

The network execution tool

positional arguments:
  {rdp,ldap,nfs,smb,winrm,vnc,mssql,wmi,ftp,ssh}

options:
  -h, --help            show this help message and exit
  --version             Display nxc's version
  -t THREADS            Set how many concurrent threads to use (default: 100)
  --timeout TIMEOUT     Max timeout in seconds of each thread (default: None)
  --jitter INTERVAL     Sets a random delay between each connection
  --no-progress         Disable progress bar
  --log LOG             Export result into a log file
  --verbose             Enable verbose output
  --debug               Enable debug level information
  -6                    Enable IPv6
```

**Common usage examples:**
```bash
# Check if creds are valid on a subnet
netexec smb 192.168.1.0/24 -u admin -p 'Password123'

# Password spray against domain
netexec smb <DC_IP> -u users.txt -p 'Winter2024!' --continue-on-success

# Pass the hash
netexec smb <target> -u Administrator -H aad3b435b51404eeaad3b435b51404ee:8846f7eaee8fb117ad06bdd830b7586c

# Enumerate shares
netexec smb <target> -u user -p pass --shares

# Execute command
netexec smb <target> -u admin -p pass -x "whoami"

# Dump SAM
netexec smb <target> -u admin -p pass --sam
```
---

## enum4linux
**Category:** SMB/Active Directory
**Description:** Linux wrapper around samba tools (rpcclient, smbclient, net) to enumerate information from Windows and Samba systems similar to enum.exe.
**Version:** 0.9.1
**Common Usage:** `enum4linux -a <target>` | `enum4linux -U -S -G <target>`
**Key Flags:**
- `-a` — Do all simple enumeration (default if no options provided)
- `-U` — Get user list
- `-S` — Get share list
- `-P` — Get password policy
- `-G` — Get group and member list
- `-M` — Get machine list
- `-r` — Enumerate users via RID cycling
- `-R <range>` — RID ranges to enumerate (default: 500-550,1000-1050)
- `-u <user>` — Username (default: "")
- `-p <pass>` — Password (default: "")
- `-d` — Detailed output for -U and -S
- `-o` — Get OS information
- `-l` — Get info via LDAP (DCs only)
**Help Output:**
```
enum4linux v0.9.1

Usage: ./enum4linux.pl [options] ip

Options are (like "enum"):
    -U        get userlist
    -M        get machine list
    -S        get sharelist
    -P        get password policy information
    -G        get group and member list
    -d        be detailed, applies to -U and -S
    -u user   specify username to use (default "")
    -p pass   specify password to use (default "")

Additional options:
    -a        Do all simple enumeration (-U -S -G -P -r -o -n -i)
    -h        Display this help message and exit
    -r        enumerate users via RID cycling
    -R range  RID ranges to enumerate (default: 500-550,1000-1050)
    -K n      Keep searching RIDs until n consecutive RIDs don't correspond to a username
    -l        Get some (limited) info via LDAP 389/TCP (for DCs only)
    -s file   brute force guessing for share names
    -o        Get OS information
    -i        Get printer information
```
---

## smbmap
**Category:** SMB/Active Directory
**Description:** SMB share enumerator that allows users to enumerate samba share drives across an entire domain.
**Version:** 1.10.7
**Common Usage:** `smbmap -H <host> -u <user> -p <pass>`
**Key Flags:**
- `-H <host>` — IP or FQDN
- `--host-file <file>` — File containing list of hosts
- `-u <user>` — Username (null session if omitted)
- `-p <pass>` — Password or NTLM hash (LMHASH:NTHASH)
- `-d <domain>` — Domain name
- `-P <port>` — SMB port (default 445)
- `-k` — Use Kerberos authentication
- `-s <share>` — Specify share (default C$)
- `-L` — List all drives on the host
- `-r <path>` — Recursively list contents of directory
- `-A <pattern>` — Search file names matching pattern (with -r)
- `-F <pattern>` — Search file content matching pattern
- `--download <path>` — Download a file
- `--upload <src> <dst>` — Upload a file
- `-x <command>` — Execute command on target
- `--no-color` — Disable color output
**Help Output:**
```
SMBMap - Samba Share Enumerator v1.10.7

options:
  -H HOST               IP or FQDN
  --host-file FILE      File containing a list of hosts
  -u, --username USERNAME   Username, null session assumed if omitted
  -p, --password PASSWORD   Password or NTLM hash (LMHASH:NTHASH)
  -k, --kerberos        Use Kerberos authentication
  -s SHARE              Specify a share (default C$)
  -d DOMAIN             Domain name (default WORKGROUP)
  -P PORT               SMB port (default 445)
  -v, --version         Return the OS version of the remote host
  --signing             Check if host has SMB signing disabled/enabled/required
  --admin               Report if the user is an admin

  -L                    List all drives on the host
  -r [PATH]             Recursively list contents of directory
  -A PATTERN            Search file names matching pattern
  -F PATTERN            Search file content matching pattern
  --download PATH       Download a file
  --upload SRC DST      Upload a file
  -x COMMAND            Execute a command
```
---

## rpcclient
**Category:** SMB/Active Directory
**Description:** Samba tool for executing MS-RPC functions against Windows machines. Used for user/group enumeration, policy retrieval, and more.
**Common Usage:** `rpcclient -U <user> <target>`
**Key Flags:**
- `-U <user>[%pass]` — Set network username (and optional password)
- `-N` — No password prompt
- `-c <commands>` — Execute semicolon-separated commands
- `-I <ip>` — Destination IP address
- `--use-kerberos=desired|required|off` — Kerberos auth
**Key Commands (interactive mode):**
- `enumdomusers` — Enumerate domain users
- `enumdomgroups` — Enumerate domain groups
- `queryuser <RID>` — Query user by RID
- `querygroup <RID>` — Query group by RID
- `getdompwinfo` — Get domain password policy
- `netshareenum` — Enumerate shares
- `lookupsids <sid>` — Look up SIDs
- `lookupnames <name>` — Look up names to SIDs
**Help Output:**
```
Usage: rpcclient [OPTION...] BINDING-STRING|HOST

Options:
  -c, --command=COMMANDS    Execute semicolon separated cmds
  -I, --dest-ip=IP          Specify destination IP address
  -p, --port=PORT           Specify port number

Credential options:
  -U, --user=[DOMAIN/]USERNAME[%PASSWORD]  Set the network username
  -N, --no-pass             Don't ask for a password
  --password=STRING         Password
  --pw-nt-hash              The supplied password is the NT hash
  -A, --authentication-file=FILE  Get the credentials from a file
  -P, --machine-pass        Use stored machine account password
  --use-kerberos=desired|required|off  Use Kerberos authentication
```
---

## impacket-scripts
**Category:** SMB/Active Directory
**Description:** Collection of Python scripts from the Impacket library for network protocol manipulation and Active Directory attacks.
**Version:** 1.10
**Location:** `/usr/bin/impacket-*`

**Available Scripts (60+ total):**

| Script | Description |
|--------|-------------|
| `impacket-psexec` | Execute commands via SMB (like PsExec) |
| `impacket-wmiexec` | Execute commands via WMI |
| `impacket-smbexec` | Execute commands via SMB (no binary upload) |
| `impacket-dcomexec` | Execute commands via DCOM |
| `impacket-atexec` | Execute commands via Task Scheduler (AT) |
| `impacket-secretsdump` | Dump hashes from SAM, LSA, NTDS.dit |
| `impacket-GetNPUsers` | Kerberos AS-REP roasting |
| `impacket-GetUserSPNs` | Kerberos Kerberoasting |
| `impacket-getTGT` | Request Kerberos TGT |
| `impacket-getST` | Request Kerberos service ticket |
| `impacket-ticketer` | Create/modify Kerberos tickets (Golden/Silver) |
| `impacket-lookupsid` | Enumerate users via RID brute force |
| `impacket-samrdump` | SAMR enumeration |
| `impacket-rpcdump` | Enumerate RPC endpoints |
| `impacket-ntlmrelayx` | NTLM relay attack tool |
| `impacket-smbclient` | SMB client |
| `impacket-smbserver` | SMB server (for file serving/capture) |
| `impacket-mssqlclient` | MSSQL client |
| `impacket-GetADUsers` | Enumerate AD users |
| `impacket-GetADComputers` | Enumerate AD computers |
| `impacket-GetLAPSPassword` | Retrieve LAPS passwords |
| `impacket-dacledit` | DACL editing for AD attacks |
| `impacket-rbcd` | Resource-Based Constrained Delegation attacks |
| `impacket-findDelegation` | Find delegation settings in AD |
| `impacket-goldenPac` | MS14-068 Kerberos privilege escalation |
| `impacket-changepasswd` | Change user password |
| `impacket-describeTicket` | Describe Kerberos ticket contents |
| `impacket-dpapi` | DPAPI secrets extraction |
| `impacket-reg` | Windows registry operations |
| `impacket-sniff` | Simple network sniffer |

**Common usage examples:**
```bash
# Dump credentials from remote host
impacket-secretsdump domain/user:pass@192.168.1.1

# Kerberoasting - get TGS tickets for offline cracking
impacket-GetUserSPNs -request -dc-ip 192.168.1.1 domain.local/user:pass

# AS-REP roasting - users with no pre-auth required
impacket-GetNPUsers -dc-ip 192.168.1.1 -usersfile users.txt domain.local/

# Remote command execution (pass-the-hash)
impacket-psexec -hashes aad3b435:ntlmhash Administrator@192.168.1.1

# SMB relay
impacket-ntlmrelayx -tf targets.txt -smb2support
```
---

## smbclient
**Category:** SMB/Active Directory
**Description:** FTP-like client for accessing SMB/CIFS resources on servers. Part of the Samba suite.
**Version:** 4.23.5
**Common Usage:** `smbclient //<host>/<share> -U <user>`
**Key Flags:**
- `-L <host>` — List available services on host
- `-U <user>[%pass]` — Username and password
- `-N` — No password
- `-W <domain>` — Domain/workgroup name
- `-p <port>` — SMB port
- `-c <commands>` — Execute comma-separated commands
**Common interactive commands:** `ls`, `get`, `put`, `mget`, `mput`, `cd`, `pwd`, `mkdir`
---
