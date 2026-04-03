# Password Attack Tools

## john
**Category:** Password Attacks
**Description:** John the Ripper — the most popular offline password cracking tool. Supports hundreds of hash types and multiple attack modes.
**Version:** 1.9.0-Jumbo-1+bleeding 2021-11-02
**Common Usage:** `john --wordlist=<file> <hashfile>` | `john --format=<type> <hashfile>`
**Key Flags:**
- `--wordlist=<file>` — Wordlist mode with specified file
- `--stdin` — Read words from stdin
- `--single` — Single crack mode (uses username and GECOS info)
- `--incremental` — Incremental (brute force) mode
- `--mask=<mask>` — Mask mode (e.g., `?u?l?l?l?d?d`)
- `--rules` — Enable word mangling rules
- `--format=<type>` — Force hash format (e.g., md5crypt, sha512crypt, ntlm, bcrypt)
- `--show` — Show cracked passwords
- `--pot=<file>` — Pot file to use/write
- `-p <n>` — Number of processes (OpenMP)
- `--list=formats` — List all supported formats
**Help Output:**
```
Usage: john [OPTIONS] [PASSWORD-FILES]

--help                     Print usage summary
--single[=SECTION[,..]]    "Single crack" mode
--wordlist[=FILE] --stdin  Wordlist mode, read words from FILE or stdin
--rules[=SECTION[,..]]     Enable word mangling rules (for wordlist mode)
--incremental[=MODE]       "Incremental" mode (brute force)
--mask[=MASK]              Mask mode using MASK (or default from john.conf)
--markov[=OPTIONS]         "Markov" mode
--prince[=FILE]            PRINCE mode, read words from FILE
--external=MODE            External mode or word filter
--show                     Show cracked passwords
--format=NAME              Force hash of type NAME
--list=WHAT                List capabilities, try --list=help or --list=formats
--restore[=NAME]           Restore an interrupted session
--session=NAME             Give a new session the NAME
--status[=NAME]            Print status of a session
--pot=NAME                 Pot file to use
```

**Common hash format examples:**
```bash
john --format=ntlm --wordlist=/usr/share/wordlists/rockyou.txt hashes.txt
john --format=md5crypt --wordlist=/usr/share/wordlists/rockyou.txt shadow.txt
john --format=bcrypt hashes.txt --wordlist=/usr/share/wordlists/rockyou.txt
john --show hashes.txt
```
---

## hashcat
**Category:** Password Attacks
**Description:** World's fastest and most advanced GPU-based password recovery tool. Supports over 300 hash types and multiple attack modes.
**Version:** 7.1.2
**Common Usage:** `hashcat -m <hash-type> -a <attack-mode> <hashfile> <wordlist/mask>`
**Key Flags:**
- `-m <type>` — Hash type (e.g., 0=MD5, 100=SHA1, 1000=NTLM, 1800=sha512crypt, 3200=bcrypt)
- `-a <mode>` — Attack mode: 0=dictionary, 1=combination, 3=brute-force/mask, 6=hybrid wordlist+mask, 7=hybrid mask+wordlist
- `-w <level>` — Workload profile 1-4
- `--force` — Ignore warnings
- `--show` — Show cracked passwords from potfile
- `-o <file>` — Output file for cracked hashes
- `-r <rules>` — Rules file
- `--status` — Enable automatic status screen
- `-O` — Optimized kernels (limits password length)
- `-S` — Slow candidates (more accurate)
- `--username` — Ignore usernames in hashfile
**Help Output:**
```
hashcat (v7.1.2) starting in help mode

Usage: hashcat [options]... hash|hashfile|hccapxfile [dictionary|mask|directory]...

Options:
 -m, --hash-type    Num   Hash-type (otherwise autodetect)       | -m 1000
 -a, --attack-mode  Num   Attack-mode                            | -a 3
 -V, --version            Print version
 -h, --help               Print help (use -hh for all hash-modes)
     --quiet              Suppress output
     --force              Ignore warnings
     --status             Enable automatic update of the status screen
     --runtime      Num   Abort session after X seconds of runtime
     --session      Str   Define specific session name
     --restore            Restore session from --session
 -o, --outfile      File  Define outfile for recovered hash
     --show               Compare hashlist with potfile; show cracked hashes
     --left               Compare hashlist with potfile; show uncracked hashes
     --remove             Enable removal of hashes once they are cracked
 -p, --separator    Char  Separator char for hashlists and outfile (default: :)
```

**Common hash type references:**
```
0     = MD5
100   = SHA1
1000  = NTLM
1400  = SHA-256
1800  = sha512crypt (Linux $6$)
2500  = WPA-PMKID-PBKDF2 (wifi)
3200  = bcrypt
5500  = NetNTLMv1
5600  = NetNTLMv2
13100 = Kerberoast (TGS-REP)
18200 = Kerberoast AS-REP (ASREProast)
```

**Common attack examples:**
```bash
# Dictionary attack on NTLM
hashcat -m 1000 -a 0 hashes.txt /usr/share/wordlists/rockyou.txt

# Brute force mask (8 chars, alpha)
hashcat -m 0 -a 3 hash.txt ?a?a?a?a?a?a?a?a

# Dictionary + rules
hashcat -m 1000 -a 0 hashes.txt wordlist.txt -r /usr/share/hashcat/rules/best64.rule
```
---

## hydra
**Category:** Password Attacks
**Description:** Network login cracker supporting dozens of protocols. Used for online password spraying and brute-force attacks.
**Version:** 9.6
**Common Usage:** `hydra -l <user> -P <passlist> <protocol>://<target>`
**Key Flags:**
- `-l <login>` — Single username
- `-L <file>` — Username list file
- `-p <pass>` — Single password
- `-P <file>` — Password list file
- `-C <file>` — Colon-separated login:pass file
- `-e nsr` — Try null, login-as-pass, and reversed login
- `-t <n>` — Parallel tasks per target (default: 16)
- `-f` — Exit after first found login/pass pair
- `-o <file>` — Output file
- `-s <port>` — Service on non-default port
- `-v / -V` — Verbose / show each attempt
- `-M <file>` — List of servers to attack
**Supported Protocols:** ssh, ftp, http-get, http-post-form, smb, smb2, rdp, mysql, mssql, vnc, telnet, imap, pop3, smtp, snmp, ldap2, ldap3, postgres, redis, socks5, and many more
**Help Output:**
```
Hydra v9.6 (c) 2023 by van Hauser/THC

Syntax: hydra [[[-l LOGIN|-L FILE] [-p PASS|-P FILE]] | [-C FILE]] [-e nsr] [-o FILE] [-t TASKS] [-M FILE] [-w TIME] [-f] [-s PORT] [service://server[:PORT][/OPT]]

Options:
  -R        restore a previous aborted/crashed session
  -S        perform an SSL connect
  -l LOGIN  login with LOGIN name
  -L FILE   load several logins from FILE
  -p PASS   try password PASS
  -P FILE   load several passwords from FILE
  -C FILE   colon separated "login:pass" format
  -e nsr    try "n" null password, "s" login as pass, "r" reversed login
  -o FILE   write found login/password pairs to FILE
  -f / -F   exit when a login/pass pair is found
  -t TASKS  run TASKS number of connects in parallel per target (default: 16)
  -w / -W TIME  wait time for a response (32s) / between connects (0s)
  -v / -V / -d  verbose / show login+pass for each attempt / debug mode
  -U        service module usage details

Supported services: adam6500 asterisk cisco cisco-enable cvs firebird
ftp[s] http[s]-{head|get|post} http[s]-{get|post}-form http-proxy imap[s]
irc ldap2[s] ldap3[-{cram|digest}md5][s] memcached mongodb mssql mysql
nntp oracle-listener pcnfs pop3[s] postgres radmin2 rdp redis rexec
rlogin rsh rtsp s7-300 sip smb smb2 smtp[s] smtp-enum snmp socks5
ssh sshkey svn teamspeak telnet[s] vmauthd vnc xmpp
```

**Common usage examples:**
```bash
# SSH brute force
hydra -l root -P /usr/share/wordlists/rockyou.txt ssh://192.168.1.1

# HTTP POST form login
hydra -l admin -P passlist.txt 192.168.1.1 http-post-form "/login:user=^USER^&pass=^PASS^:Invalid credentials"

# SMB password spray
hydra -L users.txt -p 'Password123' smb://192.168.1.0/24
```
---

## crunch
**Category:** Password Attacks
**Description:** Wordlist generator that creates wordlists based on specified criteria (character sets, patterns, min/max length).
**Version:** 3.6
**Common Usage:** `crunch <min> <max> [charset] [options]`
**Key Flags:**
- `<min>` — Minimum word length
- `<max>` — Maximum word length
- `[charset]` — Character set to use (default: lowercase alpha)
- `-o <file>` — Output file
- `-t <pattern>` — Pattern: `@` lowercase, `,` uppercase, `%` digits, `^` symbols
- `-p <words>` — Permutate specified words
- `-d <value>` — Limit duplicate adjacent characters
- `-f <charset-file> <charset-name>` — Use built-in charset from file
- `-c <n>` — Number of lines per output file
- `-b <size>` — Max bytes per output file (kb, mb, gb)
**Help Output:**
```
crunch version 3.6

Crunch can create a wordlist based on criteria you specify.
Output from crunch can be sent to the screen, file, or to another program.

Usage: crunch <min> <max> [options]
where min and max are numbers

Options:
 -b number[type]    max unit of data to write to file (requires -o START)
 -c number          number of lines per file (requires -o START)
 -d numbersymbol    limit number of duplicate adjacent characters
 -e string          stop generating words at string
 -f /path/to/charset.lst charset-name  read charset from file
 -i                 invert the output order
 -l                 treat @,%^ literally (use with -t)
 -o wordlist.txt    output file
 -p string | -p strings  print permutations without repeating
 -q filename.txt    read from file and permute (no repeating)
 -r                 resume previous session
 -s startblock      skip ahead to startblock
 -t @,%^            pattern: @=lower, ,=upper, %=digit, ^=special
 -z gzip,bzip2,lzma,7z  compress output
```

**Examples:**
```bash
# Generate 8-char passwords with lowercase + digits
crunch 8 8 abcdefghijklmnopqrstuvwxyz0123456789 -o wordlist.txt

# Pattern: 4 digits followed by 4 lowercase
crunch 8 8 -t %%%%@@@@

# Permutate specific words
crunch 1 1 -p password admin letmein
```
---

## cewl
**Category:** Password Attacks
**Description:** Custom wordlist generator that spiders a given URL and returns a list of words for use in password attacks.
**Version:** 6.2.1
**Common Usage:** `cewl -d <depth> -m <min_length> -w <outfile> <url>`
**Key Flags:**
- `-d <n>` — Depth to spider (default: 2)
- `-m <n>` — Minimum word length (default: 3)
- `-x <n>` — Maximum word length
- `-w <file>` — Write output to file
- `-o` — Follow links to other sites (offsite)
- `-e` — Include email addresses
- `-a` — Include meta data
- `-c` — Show count for each word
- `--with-numbers` — Include words with numbers
- `--lowercase` — Lowercase all words
- `-u <agent>` — User-Agent string
- `--auth_type <digest|basic>` — Authentication type
- `--auth_user <user>` — Auth username
- `--auth_pass <pass>` — Auth password
**Help Output:**
```
CeWL 6.2.1 Robin Wood (robin@digi.ninja) (https://digi.ninja/)
Usage: cewl [OPTIONS] ... <url>

    OPTIONS:
    -h, --help          Show help.
    -k, --keep          Keep the downloaded file.
    -d <x>,--depth <x>  Depth to spider to, default 2.
    -m, --min_word_length  Minimum word length, default 3.
    -x, --max_word_length  Maximum word length, default unset.
    -o, --offsite       Let the spider visit other sites.
    -w, --write         Write the output to the file.
    -u, --ua <agent>    User agent to send.
    -n, --no-words      Don't output the wordlist.
    --lowercase         Lowercase all parsed words
    --with-numbers      Accept words with numbers in as well
    -a, --meta          Include meta data.
    -e, --email         Include email addresses.
    -c, --count         Show the count for each word found.
    -v, --verbose       Verbose.

    Authentication:
    --auth_type         Digest or basic.
    --auth_user         Authentication username.
    --auth_pass         Authentication password.

    Proxy Support:
    --proxy_host        Proxy host.
    --proxy_port        Proxy port, default 8080.
```
---

## hashid
**Category:** Password Attacks
**Description:** Identifies the type of a given hash using a regex database of hash patterns.
**Version:** 3.1.4
**Common Usage:** `hashid <hash>` | `hashid -f <hashfile>`
**Key Flags:**
- `-m` — Include Hashcat mode in output
- `-j` — Include John the Ripper format in output
- `-f <file>` — Read hashes from file
- `-o <file>` — Write output to file
---
