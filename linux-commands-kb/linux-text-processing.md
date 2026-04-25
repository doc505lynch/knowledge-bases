# Linux Text Processing — Exhaustive Reference

> Covers every major text processing tool with full depth. Designed for RAG upload or direct reference.
> Last updated: 2026-04-25

---

## Table of Contents

1. [grep / egrep / fgrep](#1-grep--egrep--fgrep)
2. [sed](#2-sed)
3. [awk](#3-awk)
4. [cut](#4-cut)
5. [sort](#5-sort)
6. [uniq](#6-uniq)
7. [tr](#7-tr)
8. [paste and join](#8-paste-and-join)
9. [diff and patch](#9-diff-and-patch)
10. [wc](#10-wc)
11. [head and tail](#11-head-and-tail)
12. [xargs](#12-xargs)
13. [tee](#13-tee)
14. [column](#14-column)
15. [Bash String Operations](#15-bash-string-operations)

---

## 1. grep / egrep / fgrep

### Overview

`grep` searches files or stdin for lines matching a pattern and prints matching lines. The three variants differ only in how patterns are interpreted:

| Command | Equivalent | Pattern Type |
|---------|-----------|--------------|
| `grep` | `grep -G` | Basic Regular Expressions (BRE) |
| `egrep` | `grep -E` | Extended Regular Expressions (ERE) |
| `fgrep` | `grep -F` | Fixed strings (no regex — fastest) |

On modern systems, `egrep` and `fgrep` are deprecated aliases; use `grep -E` and `grep -F` instead.

### Syntax

```
grep [OPTIONS] PATTERN [FILE...]
grep [OPTIONS] -e PATTERN [-e PATTERN...] [FILE...]
grep [OPTIONS] -f PATTERN_FILE [FILE...]
```

### Core Flags

| Flag | Long form | Meaning |
|------|-----------|---------|
| `-i` | `--ignore-case` | Case-insensitive match |
| `-v` | `--invert-match` | Print non-matching lines |
| `-r` | `--recursive` | Recurse into directories |
| `-R` | `--dereference-recursive` | Like -r but follows symlinks |
| `-l` | `--files-with-matches` | Print only filenames that match |
| `-L` | `--files-without-match` | Print only filenames that do NOT match |
| `-n` | `--line-number` | Prefix output with line number |
| `-c` | `--count` | Print count of matching lines per file |
| `-A N` | `--after-context=N` | Print N lines after each match |
| `-B N` | `--before-context=N` | Print N lines before each match |
| `-C N` | `--context=N` | Print N lines before AND after each match |
| `-P` | `--perl-regexp` | Use Perl-Compatible Regular Expressions (PCRE) |
| `-E` | `--extended-regexp` | Use Extended Regular Expressions |
| `-F` | `--fixed-strings` | Treat pattern as literal fixed string |
| `-o` | `--only-matching` | Print only the matched portion of lines |
| `-w` | `--word-regexp` | Match whole words only |
| `-x` | `--line-regexp` | Match whole lines only |
| `-m N` | `--max-count=N` | Stop after N matches |
| `-q` | `--quiet` | Suppress output; exit 0 if match found |
| `-s` | `--no-messages` | Suppress error messages |
| `-H` | `--with-filename` | Always print filename (default when multiple files) |
| `-h` | `--no-filename` | Never print filename |
| `--include=GLOB` | — | Only search files matching glob |
| `--exclude=GLOB` | — | Skip files matching glob |
| `--exclude-dir=DIR` | — | Skip directories matching name |
| `-z` | `--null-data` | Use NUL as line separator (for binary/null-delimited) |
| `--color` | — | Highlight matching text |
| `-a` | `--text` | Process binary files as text |

### Basic Regular Expressions (BRE) — grep default

In BRE, most metacharacters must be escaped with `\` to gain special meaning:

| Pattern | Meaning |
|---------|---------|
| `.` | Any single character except newline |
| `*` | Zero or more of preceding |
| `^` | Start of line |
| `$` | End of line |
| `[abc]` | Character class — a, b, or c |
| `[^abc]` | Negated class — not a, b, or c |
| `[a-z]` | Range |
| `\+` | One or more (BRE requires backslash) |
| `\?` | Zero or one |
| `\{n,m\}` | Between n and m occurrences |
| `\(foo\)` | Grouping (BRE requires backslash) |
| `\1` | Backreference to group 1 |

### Extended Regular Expressions (ERE) — grep -E

In ERE, metacharacters `+`, `?`, `{`, `}`, `(`, `)`, `|` work without backslash:

| Pattern | Meaning |
|---------|---------|
| `+` | One or more |
| `?` | Zero or one |
| `{n,m}` | Between n and m |
| `(foo\|bar)` | Alternation |
| `(foo)` | Grouping |
| `\1` | Backreference |

### PCRE — grep -P

Enables Perl-style syntax with rich features:

| Pattern | Meaning |
|---------|---------|
| `\d` | Digit `[0-9]` |
| `\D` | Non-digit |
| `\w` | Word character `[a-zA-Z0-9_]` |
| `\W` | Non-word character |
| `\s` | Whitespace |
| `\S` | Non-whitespace |
| `\b` | Word boundary |
| `\B` | Non-word boundary |
| `(?=...)` | Positive lookahead |
| `(?!...)` | Negative lookahead |
| `(?<=...)` | Positive lookbehind |
| `(?<!...)` | Negative lookbehind |
| `(?:...)` | Non-capturing group |
| `(?P<name>...)` | Named capture group |
| `(?P=name)` | Reference to named group |
| `\K` | Reset start of match (like variable-length lookbehind) |

### POSIX Character Classes

Used inside `[[ ]]` in patterns:

| Class | Equivalent |
|-------|-----------|
| `[:alpha:]` | `[a-zA-Z]` |
| `[:digit:]` | `[0-9]` |
| `[:alnum:]` | `[a-zA-Z0-9]` |
| `[:space:]` | Whitespace including tab |
| `[:upper:]` | `[A-Z]` |
| `[:lower:]` | `[a-z]` |
| `[:punct:]` | Punctuation characters |
| `[:blank:]` | Space and tab only |
| `[:xdigit:]` | `[0-9a-fA-F]` |

Usage: `grep '[[:alpha:]][[:digit:]]' file`

### Examples

```bash
# Find lines containing "error" (case-insensitive) in all log files
grep -i "error" /var/log/*.log

# Recursive search for "TODO" in all .py files, with line numbers
grep -rn "TODO" --include="*.py" /project/

# Print only filenames containing "password" (no matches printed)
grep -rl "password" /etc/

# Show 3 lines of context around each match
grep -C 3 "segfault" /var/log/kern.log

# Count matches per file
grep -c "404" /var/log/nginx/access.log

# Invert: lines that do NOT contain "debug"
grep -v "debug" app.log

# Match whole word "foo" but not "foobar"
grep -w "foo" file.txt

# Extract IP addresses using PCRE
grep -oP '\b\d{1,3}(\.\d{1,3}){3}\b' access.log

# Lookahead: lines with "foo" only when followed by "bar"
grep -P "foo(?=bar)" file.txt

# Lookbehind: "bar" only when preceded by "foo"
grep -P "(?<=foo)bar" file.txt

# Named capture groups (PCRE): extract username from log
grep -oP 'user=(?P<user>\w+)' auth.log

# Multiple patterns (-e)
grep -e "error" -e "warning" -e "critical" syslog

# Use -F for literal string (no regex interpretation — faster)
grep -F "192.168.1.1" access.log

# Null-terminated output for use with xargs -0
grep -rlZ "pattern" /dir/ | xargs -0 rm

# Stop after first match in a file
grep -m 1 "FATAL" app.log

# Match empty lines
grep "^$" file.txt

# Lines with exactly 5 characters
grep -P "^.{5}$" file.txt

# Find lines NOT ending with semicolon (useful for code)
grep -v ";$" source.c
```

### Common Idioms

```bash
# Count total occurrences (not just lines)
grep -o "pattern" file | wc -l

# Search and show only matched part with filename
grep -rnoH "TODO:.*" --include="*.py" .

# Exclude binary files automatically
grep -rI "pattern" .

# Search compressed files
zgrep "error" /var/log/syslog.gz

# Recursive, exclude version control dirs
grep -r --exclude-dir=".git" --exclude-dir="node_modules" "pattern" .

# Case-insensitive, print filename only
grep -ril "admin" /etc/

# Pipeline: top 10 most common errors
grep "ERROR" app.log | sort | uniq -c | sort -rn | head -10
```

---

## 2. sed

### Overview

`sed` (stream editor) reads input line by line, applies editing commands, and writes to stdout. It is non-interactive and ideal for in-place file transforms and pipeline transformations.

### Syntax

```
sed [OPTIONS] 'SCRIPT' [FILE...]
sed [OPTIONS] -e 'CMD1' -e 'CMD2' [FILE...]
sed [OPTIONS] -f SCRIPT_FILE [FILE...]
```

### Core Options

| Option | Meaning |
|--------|---------|
| `-n` | Suppress automatic printing (use `p` command explicitly) |
| `-e 'script'` | Add script expression |
| `-f file` | Read script from file |
| `-i[SUFFIX]` | In-place editing; optional backup suffix (e.g., `-i.bak`) |
| `-i ''` | In-place with no backup (macOS requires the empty string explicitly) |
| `-r` or `-E` | Extended regex (ERE) instead of BRE |
| `-z` | Use NUL as line delimiter (for multiline with null-terminated input) |
| `--sandbox` | Disable e/r/w commands (security) |

### Address Syntax

Commands can be prefixed with an address to apply only to specific lines:

| Address | Meaning |
|---------|---------|
| `N` | Line number N |
| `$` | Last line |
| `N,M` | Lines N through M |
| `N~S` | Every S-th line starting at N (e.g., `0~2` = even lines) |
| `/regex/` | Lines matching regex |
| `/regex1/,/regex2/` | Range from first match to second match |
| `addr!` | Negate — all lines NOT matching address |
| `0,/regex/` | From start through first match of regex |

### Commands

| Command | Syntax | Meaning |
|---------|--------|---------|
| `s` | `s/REGEX/REPLACEMENT/FLAGS` | Substitute |
| `d` | `d` | Delete line |
| `p` | `p` | Print line |
| `q` | `q [code]` | Quit (optionally with exit code) |
| `Q` | `Q [code]` | Quit without printing current line |
| `i` | `i\TEXT` | Insert TEXT before line |
| `a` | `a\TEXT` | Append TEXT after line |
| `c` | `c\TEXT` | Replace line with TEXT |
| `y` | `y/SOURCE/DEST/` | Transliterate characters (like tr) |
| `n` | `n` | Print current line and advance to next |
| `N` | `N` | Append next line to pattern space |
| `P` | `P` | Print first line of pattern space |
| `D` | `D` | Delete first line of pattern space |
| `h` | `h` | Copy pattern space to hold space |
| `H` | `H` | Append pattern space to hold space |
| `g` | `g` | Get hold space into pattern space |
| `G` | `G` | Append hold space to pattern space |
| `x` | `x` | Exchange pattern and hold spaces |
| `l` | `l` | Print pattern space visually (non-printable as escapes) |
| `=` | `=` | Print current line number |
| `r file` | `r file` | Read and append file contents |
| `R file` | `R file` | Read one line from file |
| `w file` | `w file` | Write pattern space to file |
| `b label` | `b [label]` | Branch to label (or end of script if no label) |
| `t label` | `t [label]` | Branch if substitution made since last t |
| `T label` | `T [label]` | Branch if NO substitution since last t |
| `: label` | `: label` | Define a label |
| `e` | `e [cmd]` | Execute pattern space (or cmd) as shell command |

### Substitution Flags

After the third delimiter in `s/RE/REPLACEMENT/FLAGS`:

| Flag | Meaning |
|------|---------|
| `g` | Replace all occurrences (global) |
| `N` (number) | Replace only N-th occurrence |
| `i` or `I` | Case-insensitive match |
| `p` | Print if substitution was made (use with `-n`) |
| `w file` | Write to file if substitution was made |
| `e` | Execute result as shell command |
| `m` or `M` | Multiline mode — `^` and `$` match embedded newlines |

### Replacement Special Characters

| Sequence | Meaning |
|----------|---------|
| `&` | Entire matched string |
| `\1` through `\9` | Backreference to capture group |
| `\n` | Newline in replacement |
| `\u` | Uppercase next character |
| `\l` | Lowercase next character |
| `\U` | Uppercase until `\E` |
| `\L` | Lowercase until `\E` |
| `\E` | End `\U` or `\L` |

### Pattern Space and Hold Space

sed maintains two buffers:
- **Pattern space**: the current line being processed (reset each cycle)
- **Hold space**: persistent buffer across lines (initially empty)

The execution cycle:
1. Read next line into pattern space
2. Execute all commands
3. (Unless `-n`) print pattern space
4. Repeat

### Examples

```bash
# Simple substitution: replace first "foo" with "bar" per line
sed 's/foo/bar/' file.txt

# Global substitution: replace ALL occurrences per line
sed 's/foo/bar/g' file.txt

# Case-insensitive global replace
sed 's/foo/bar/gI' file.txt

# In-place replacement with backup
sed -i.bak 's/oldvalue/newvalue/g' config.txt

# In-place, no backup
sed -i 's/oldvalue/newvalue/g' config.txt

# Delete lines matching pattern
sed '/^#/d' config.txt        # remove comment lines
sed '/^[[:space:]]*$/d' f.txt # remove blank lines

# Print only lines 5 through 10
sed -n '5,10p' file.txt

# Print only lines matching regex
sed -n '/ERROR/p' app.log

# Delete lines 3 through 7
sed '3,7d' file.txt

# Insert a line before line 5
sed '5i\New line here' file.txt

# Append a line after pattern match
sed '/^Host /a\  StrictHostKeyChecking no' ~/.ssh/config

# Replace entire line matching pattern
sed '/^version=/c\version=2.0' config.ini

# Print line numbers alongside content
sed -n '=' file.txt | paste - <(cat file.txt)

# Remove trailing whitespace
sed 's/[[:space:]]*$//' file.txt

# Remove leading whitespace
sed 's/^[[:space:]]*//' file.txt

# Remove both leading and trailing whitespace
sed 's/^[[:space:]]*//;s/[[:space:]]*$//' file.txt

# Double-space a file (add blank line after every line)
sed 'G' file.txt

# Number non-blank lines
sed '/./=' file.txt | sed '/./N; s/\n/ /'

# Extract lines between two markers (inclusive)
sed -n '/START/,/END/p' file.txt

# Extract lines between markers (exclusive)
sed -n '/START/,/END/{/START/d;/END/d;p}' file.txt

# Transliterate (like tr): swap upper/lower
sed 'y/abcdefghijklmnopqrstuvwxyz/ABCDEFGHIJKLMNOPQRSTUVWXYZ/' f

# Join continuation lines (backslash at end of line)
sed -e ':a' -e '/\\$/N; s/\\\n//; ta' file.txt

# Reverse order of lines (tac equivalent using hold space)
sed -n '1!G;h;$p' file.txt

# Print last 3 lines (tail -3 equivalent)
sed -n '$p;N;$p;$p' file.txt   # simple version
# More robust:
sed -n -e ':a' -e '$p' -e 'N' -e '4,$D' -e 'ba' file.txt

# Delete lines from pattern to end of file
sed '/MARKER/,$d' file.txt

# Every other line: delete even-numbered lines
sed 'n;d' file.txt

# Replace Nth occurrence only (3rd in this case)
sed 's/foo/bar/3' file.txt

# Use & to reference the match
sed 's/[0-9]*/[&]/' file.txt   # wrap first number in brackets

# Multiline: join line ending in backslash with next
sed ':a;N;$!ba;s/\\\n//g' file.txt

# Print line count equivalent
sed -n '$=' file.txt
```

### Hold Space Idioms

```bash
# Swap adjacent lines
sed -n 'h;n;p;g;p' file.txt

# Print every second line starting with line 2
sed -n 'n;p' file.txt

# Duplicate every line
sed 'p' file.txt

# Collect all lines into hold space then print once
sed -n 'H;${g;s/^\n//;p}' file.txt
```

---

## 3. awk

### Overview

`awk` is a full programming language for text processing. It reads input record by record (default: line by line), splits each record into fields, and executes code for matching patterns.

The three main implementations:
- `awk` — usually POSIX awk or gawk on Linux
- `gawk` — GNU awk; most feature-rich, highly recommended
- `mawk` — fast minimal awk (often the default `awk` on Debian)
- `nawk` — "new awk" (original Bell Labs version)

### Syntax

```
awk [OPTIONS] 'PROGRAM' [FILE...]
awk [OPTIONS] -f PROGRAM_FILE [FILE...]
```

### Options

| Option | Meaning |
|--------|---------|
| `-F sep` | Set field separator FS to sep (string or regex) |
| `-v var=val` | Assign variable before program runs |
| `-f file` | Read program from file |
| `--` | End of options |

### Program Structure

```
awk '
    BEGIN { initialization }
    /pattern/ { action }
    pattern { action }
    END { cleanup }
' file
```

- **BEGIN**: runs once before any input is read
- **END**: runs once after all input is processed
- **Pattern**: can be a regex `/regex/`, an expression, or a range `pat1,pat2`
- **Action**: arbitrary awk code in `{ }`
- Pattern or action can be omitted; missing action defaults to `{ print }`

### Built-in Variables

| Variable | Meaning | Default |
|----------|---------|---------|
| `FS` | Input field separator | `" "` (any whitespace) |
| `OFS` | Output field separator | `" "` |
| `RS` | Input record separator | `"\n"` |
| `ORS` | Output record separator | `"\n"` |
| `NR` | Total records read so far | — |
| `NF` | Number of fields in current record | — |
| `FNR` | Record number within current file | — |
| `FILENAME` | Name of current input file | — |
| `$0` | Entire current record | — |
| `$1..$NF` | Fields 1 through NF | — |
| `ARGC` | Number of command-line arguments | — |
| `ARGV` | Array of command-line arguments | — |
| `ENVIRON` | Array of environment variables | — |
| `SUBSEP` | Separator for multi-dim array keys | `\034` |

### gawk-Specific Variables

| Variable | Meaning |
|----------|---------|
| `OFMT` | Output format for numbers (default `"%.6g"`) |
| `CONVFMT` | Conversion format for numbers to strings |
| `BINMODE` | Binary mode for files (Windows) |
| `FIELDWIDTHS` | Space-separated list of field widths (fixed-width input) |
| `FPAT` | Regex that defines what a field IS (vs. FS which is the separator) |

### Operators

| Operator | Meaning |
|----------|---------|
| `+`, `-`, `*`, `/`, `%`, `^` | Arithmetic |
| `==`, `!=`, `<`, `>`, `<=`, `>=` | Comparison |
| `&&`, `\|\|`, `!` | Logical |
| `~`, `!~` | Regex match / non-match |
| `?:` | Ternary |
| `++`, `--` | Increment/decrement |
| `+=`, `-=`, etc. | Compound assignment |
| `in` | Array membership test |

### String Functions

| Function | Meaning |
|----------|---------|
| `length([str])` | Length of str (or $0 if omitted) |
| `substr(str, start [, len])` | Substring starting at start (1-based), optional length |
| `index(str, find)` | Position of find in str (0 if not found) |
| `split(str, arr [, sep])` | Split str into array arr using sep; returns element count |
| `sub(regex, repl [, str])` | Replace first match in str (default $0) |
| `gsub(regex, repl [, str])` | Replace all matches in str |
| `match(str, regex)` | Find regex in str; sets RSTART, RLENGTH; returns position |
| `sprintf(fmt, args)` | Format string (like C printf) |
| `printf(fmt, args)` | Print formatted (no auto newline) |
| `tolower(str)` | Convert to lowercase |
| `toupper(str)` | Convert to uppercase |
| `gensub(r, s, h [, str])` | gawk: replace; h="g" for all, h=N for Nth (returns new string) |
| `patsplit(str, arr, fpat)` | gawk: split by pattern |
| `strftime(fmt, timestamp)` | gawk: format timestamp |
| `systime()` | gawk: current Unix timestamp |

### Math Functions

| Function | Meaning |
|----------|---------|
| `int(x)` | Truncate to integer |
| `sqrt(x)` | Square root |
| `log(x)` | Natural log |
| `exp(x)` | e^x |
| `sin(x)`, `cos(x)`, `atan2(y,x)` | Trig |
| `rand()` | Random float in [0,1) |
| `srand([seed])` | Seed random number generator |

### I/O Functions

| Function | Meaning |
|----------|---------|
| `print [args] > "file"` | Write to file (overwrites) |
| `print [args] >> "file"` | Append to file |
| `print [args] \| "cmd"` | Pipe to command |
| `"cmd" \| getline var` | Read from command |
| `getline var < "file"` | Read line from file |
| `getline` | Read next record from current input |
| `close("file_or_cmd")` | Close file or command (flush) |
| `system("cmd")` | Execute shell command |
| `fflush([file])` | Flush output buffers |

### Control Flow

```awk
if (condition) { ... } else { ... }
while (condition) { ... }
do { ... } while (condition)
for (init; cond; update) { ... }
for (key in array) { ... }
break
continue
next            # skip to next input record
nextfile        # skip to next file (gawk)
exit [code]     # jump to END block
delete arr[key] # delete array element
delete arr      # delete entire array
```

### Arrays

awk arrays are associative (hash maps). Keys are strings (numbers auto-convert).

```awk
# Declare implicitly by assignment
arr["key"] = "value"
arr[1] = "one"

# Multi-dimensional (SUBSEP separator)
arr[i,j] = value
if ((i,j) in arr) ...

# Iterate
for (k in arr) print k, arr[k]

# Delete
delete arr["key"]
delete arr   # delete all

# Check membership
if ("key" in arr) ...
```

### Examples

```bash
# Print specific fields (columns 1 and 3)
awk '{print $1, $3}' file.txt

# Use comma as field separator
awk -F, '{print $2}' data.csv

# Use regex as field separator
awk -F'[,;:]' '{print $1}' file.txt

# Print last field of each line
awk '{print $NF}' file.txt

# Print second-to-last field
awk '{print $(NF-1)}' file.txt

# Print lines where field 3 > 100
awk '$3 > 100' data.txt

# Sum a column
awk '{sum += $1} END {print sum}' numbers.txt

# Average a column
awk '{sum += $3; count++} END {print sum/count}' data.txt

# Count occurrences of each unique value in field 2
awk '{count[$2]++} END {for (k in count) print count[k], k}' f.txt

# Change output field separator
awk -F: 'BEGIN{OFS=","} {print $1,$3,$6}' /etc/passwd

# Filter lines and print with custom format
awk -F: '$3 >= 1000 {printf "User: %-15s UID: %d\n", $1, $3}' /etc/passwd

# NR == FNR pattern for comparing two files (join)
awk 'NR==FNR {seen[$0]=1; next} seen[$0]' file1.txt file2.txt

# Print lines in file2 NOT in file1
awk 'NR==FNR {a[$0]; next} !($0 in a)' file1.txt file2.txt

# Add line numbers
awk '{print NR": "$0}' file.txt

# Print lines 5-10
awk 'NR>=5 && NR<=10' file.txt

# Skip header, process data
awk 'NR>1 {print $2}' data.csv

# Multi-file: track which file each record came from
awk '{print FILENAME": "$0}' file1.txt file2.txt

# In-place-like editing (replace awk output back to file)
awk '{gsub(/foo/, "bar"); print}' file.txt > tmp && mv tmp file.txt

# Use getline to read another file
awk '{while ((getline line < "lookup.txt") > 0) if ($1 == line) print}' data

# Multiline records (RS as blank line)
awk 'BEGIN{RS=""; FS="\n"} {print NR": "$1}' paragraphs.txt

# Print duplicate lines
awk 'seen[$0]++' file.txt

# Print unique lines (first occurrence)
awk '!seen[$0]++' file.txt

# Transpose (pivot) a matrix
awk '{for(i=1;i<=NF;i++) a[i][NR]=$i} END{for(i=1;i<=NF;i++){for(j=1;j<=NR;j++) printf a[i][j](j==NR?"\n":"\t")}}' matrix.txt

# Word frequency count
awk '{for(i=1;i<=NF;i++) freq[$i]++} END{for(w in freq) print freq[w], w}' text.txt | sort -rn

# Reporting: pad and align columns
awk '{printf "%-20s %10.2f\n", $1, $2}' sales.txt

# CSV with quoted fields (basic — gawk FPAT)
gawk 'BEGIN{FPAT="([^,]+)|(\"[^\"]+\")"} {print $2}' data.csv

# Running total
awk '{total += $1; print $0, total}' numbers.txt

# Group by field and sum
awk '{totals[$1] += $2} END {for (k in totals) printf "%-15s %d\n", k, totals[k]}' data.txt | sort

# Strip ANSI color codes
awk '{gsub(/\033\[[0-9;]*m/, ""); print}' colored_output.txt
```

### Practical Reporting: /etc/passwd Analysis

```awk
#!/usr/bin/awk -f
BEGIN {
    FS = ":"
    OFS = "\t"
    print "Username", "UID", "Shell"
    print "--------", "---", "-----"
}
$3 >= 1000 {          # regular users
    users++
    shells[$7]++
    printf "%-20s %-6d %s\n", $1, $3, $7
}
END {
    print "\nTotal regular users:", users
    print "\nShell distribution:"
    for (sh in shells)
        printf "  %-30s %d\n", sh, shells[sh]
}
```

---

## 4. cut

### Overview

`cut` extracts sections from each line of input — by byte position, character position, or field (delimiter-based).

### Syntax

```
cut OPTION... [FILE...]
```

### Options

| Option | Meaning |
|--------|---------|
| `-b LIST` | Select bytes (byte positions) |
| `-c LIST` | Select characters (character positions; UTF-8 aware) |
| `-f LIST` | Select fields (delimiter-separated) |
| `-d DELIM` | Field delimiter character (default: TAB); used with `-f` |
| `--complement` | Invert selection — print all EXCEPT specified |
| `-s` | Suppress lines with no delimiter (with `-f`) |
| `--output-delimiter=STR` | Use STR instead of input delimiter on output |
| `-z` | NUL as line delimiter |

### List Syntax

LIST is a comma-separated set of positions or ranges:

| Syntax | Meaning |
|--------|---------|
| `N` | N-th byte/char/field (1-based) |
| `N-M` | From N to M |
| `N-` | From N to end |
| `-M` | From 1 to M |
| `N,M,P` | Multiple individual positions |

### Examples

```bash
# Extract the 2nd colon-separated field from /etc/passwd (username)
cut -d: -f1 /etc/passwd

# Extract multiple fields: fields 1, 3, 6
cut -d: -f1,3,6 /etc/passwd

# Extract a range of fields: fields 2 through 5
cut -d: -f2-5 /etc/passwd

# Extract characters 1-10 from each line
cut -c1-10 file.txt

# Extract bytes 1-3 and 8-10
cut -b1-3,8-10 file.txt

# Print everything EXCEPT field 2 (complement)
cut -d, -f2 --complement data.csv

# Change output delimiter to pipe
cut -d: -f1,3 --output-delimiter='|' /etc/passwd

# Suppress lines without the delimiter
cut -d, -f1 -s mixed.txt

# Extract first field from CSV, skip header with tail
tail -n +2 data.csv | cut -d, -f1

# Extract last N characters (using rev trick)
rev file.txt | cut -c1-5 | rev

# Extract specific byte range from binary (e.g., file magic bytes)
cut -b1-4 binary.bin | xxd
```

### Limitations

`cut` cannot:
- Reorder fields (use `awk` instead)
- Use multi-character delimiters (use `awk -F`)
- Handle quoted CSV fields containing delimiters

---

## 5. sort

### Overview

`sort` sorts lines of text files or stdin. By default, sorts lexicographically in ascending order.

### Syntax

```
sort [OPTIONS] [FILE...]
```

### Options

| Option | Meaning |
|--------|---------|
| `-n` | Numeric sort (compare as numbers) |
| `-r` | Reverse order (descending) |
| `-k POS1[,POS2]` | Sort by key starting at field POS1, ending at POS2 |
| `-t SEP` | Field separator (default: non-blank to blank transition) |
| `-u` | Unique — remove duplicate lines |
| `-f` | Fold case (case-insensitive) |
| `-b` | Ignore leading blanks |
| `-i` | Ignore non-printable characters |
| `-d` | Dictionary order (only alphanumerics and blanks) |
| `-h` | Human-readable sort (e.g., 1K < 2M < 1G) |
| `-V` | Version sort (e.g., 1.9 < 1.10) |
| `-R` | Random shuffle (but keeps identical lines together) |
| `-g` | General numeric (handles scientific notation) |
| `-M` | Month sort (JAN < FEB < ... < DEC) |
| `-o FILE` | Write output to FILE (safe for in-place sort) |
| `-c` | Check if already sorted (exit 0 if yes) |
| `-C` | Like -c but silent |
| `-m` | Merge sorted files (assumes already sorted) |
| `-s` | Stable sort (preserve original order for equal keys) |
| `-z` | NUL-terminated lines |
| `--parallel=N` | Use N threads |
| `--buffer-size=SIZE` | Buffer size for sort |
| `--temporary-directory=DIR` | Use DIR for temp files |

### Key Specification (-k)

Format: `-k START[TYPE][,END[TYPE]]`

Where TYPE is one of: `n` (numeric), `r` (reverse), `g` (general numeric), `h` (human), `V` (version), `f` (fold case), `b` (ignore blanks), `d` (dictionary), `i` (ignore non-print), `M` (month), `R` (random)

The `.` notation: `2.3` means field 2, starting at character 3 within that field.

```bash
# Sort by field 2 numerically
sort -k2,2n file.txt

# Sort by field 3 reverse numerically, then field 1 alphabetically
sort -k3,3rn -k1,1 file.txt

# Sort by characters 3-5 of field 2
sort -k2.3,2.5 file.txt
```

### Examples

```bash
# Basic lexicographic sort
sort file.txt

# Numeric sort
sort -n numbers.txt

# Reverse sort (largest first)
sort -rn numbers.txt

# Sort and remove duplicates
sort -u file.txt

# Sort case-insensitively
sort -f file.txt

# Sort by second field (tab-separated)
sort -k2 data.tsv

# Sort CSV by 3rd field numerically
sort -t, -k3,3n data.csv

# Sort by multiple keys: field 1 alpha, then field 2 numeric
sort -k1,1 -k2,2n data.txt

# Human-readable numeric sort (for du, ls -lh output)
du -sh * | sort -h

# Version sort (1.2.10 after 1.2.9)
ls *.tar.gz | sort -V

# In-place sort (safe — uses -o)
sort -o file.txt file.txt

# Sort and count unique (combined with uniq)
sort file.txt | uniq -c | sort -rn

# Random shuffle
sort -R file.txt

# Sort by month name
sort -M months.txt   # JAN, FEB, ... DEC

# Stable sort (preserve original relative order for equal keys)
sort -s -k1,1 data.txt

# Check if file is sorted
sort -c file.txt && echo "sorted" || echo "not sorted"

# Merge two pre-sorted files
sort -m sorted1.txt sorted2.txt

# Sort by last field (awk to get NF, then sort)
awk '{print $NF, $0}' file.txt | sort -k1,1 | cut -d' ' -f2-

# Sort IP addresses numerically
sort -t. -k1,1n -k2,2n -k3,3n -k4,4n ip_list.txt
```

---

## 6. uniq

### Overview

`uniq` filters adjacent duplicate lines from sorted input. Almost always used after `sort`.

### Syntax

```
uniq [OPTIONS] [INPUT [OUTPUT]]
```

### Options

| Option | Meaning |
|--------|---------|
| `-c` | Prefix lines with count of occurrences |
| `-d` | Print only duplicate lines (lines that appear more than once) |
| `-D` | Print all lines that are duplicates |
| `-u` | Print only unique lines (lines that appear exactly once) |
| `-i` | Case-insensitive comparison |
| `-f N` | Skip first N fields before comparing |
| `-s N` | Skip first N characters before comparing |
| `-w N` | Compare at most N characters |
| `-z` | NUL-terminated lines |
| `--group` | Print all groups (with blank line between groups) |

### Examples

```bash
# Count occurrences of each line (must be sorted first)
sort file.txt | uniq -c

# Show only duplicate lines
sort file.txt | uniq -d

# Show only unique (non-duplicated) lines
sort file.txt | uniq -u

# Case-insensitive uniqueness
sort -f file.txt | uniq -i

# Top 10 most common lines
sort file.txt | uniq -c | sort -rn | head -10

# Top 10 most common IP addresses in nginx log
awk '{print $1}' /var/log/nginx/access.log | sort | uniq -c | sort -rn | head -10

# Compare only first 5 characters
sort file.txt | uniq -w5

# Skip first 2 fields when comparing (useful for timestamped logs)
sort -k3 log.txt | uniq -f2

# Find duplicate filenames in directory listing
ls -1 | sort | uniq -d

# Count distinct values
sort file.txt | uniq | wc -l

# Show groups of duplicates with blank line between
sort file.txt | uniq --group=separate
```

### Combining sort and uniq

```bash
# Full pipeline: sort → unique with counts → sort by frequency
sort words.txt | uniq -c | sort -rn

# Lines in both files (intersection)
sort file1.txt file2.txt | uniq -d

# Lines unique to either file (symmetric difference)
sort file1.txt file2.txt | uniq -u

# Lines only in file1 (not in file2)
sort file1.txt file2.txt file2.txt | uniq -u
```

---

## 7. tr

### Overview

`tr` translates, squeezes, or deletes characters. It reads stdin and writes to stdout. It operates on characters, not lines.

### Syntax

```
tr [OPTIONS] SET1 [SET2]
```

### Options

| Option | Meaning |
|--------|---------|
| `-d` | Delete characters in SET1 (no SET2 needed) |
| `-s` | Squeeze consecutive repeated characters in SET1 to one |
| `-c` | Complement SET1 (use all characters NOT in SET1) |
| `-t` | Truncate SET1 to length of SET2 before processing |

### Character Sets

| Notation | Meaning |
|----------|---------|
| `a-z` | Range: a through z |
| `A-Z` | Range: A through Z |
| `0-9` | Range: 0 through 9 |
| `\n` | Newline |
| `\t` | Tab |
| `\r` | Carriage return |
| `\a` | Alert (bell) |
| `\b` | Backspace |
| `\f` | Form feed |
| `\v` | Vertical tab |
| `\NNN` | Octal value NNN |
| `\\` | Literal backslash |
| `[:alpha:]` | All letters |
| `[:digit:]` | All digits |
| `[:alnum:]` | All alphanumerics |
| `[:space:]` | All whitespace |
| `[:upper:]` | Uppercase letters |
| `[:lower:]` | Lowercase letters |
| `[:blank:]` | Space and tab |
| `[:punct:]` | Punctuation |
| `[:print:]` | Printable characters |
| `[:graph:]` | Printable non-space characters |
| `[:cntrl:]` | Control characters |

### Examples

```bash
# Uppercase to lowercase
tr 'A-Z' 'a-z' < file.txt

# Lowercase to uppercase (using POSIX classes)
tr '[:lower:]' '[:upper:]' < file.txt

# Delete digits
tr -d '0-9' < file.txt

# Delete all non-printable characters
tr -cd '[:print:]' < file.txt

# Delete all characters NOT alphanumeric or space
tr -cd '[:alnum:] \n' < file.txt

# Squeeze multiple spaces to single space
tr -s ' ' < file.txt

# Squeeze multiple blank lines to one
tr -s '\n' < file.txt

# Replace newlines with spaces (join all lines)
tr '\n' ' ' < file.txt

# Replace spaces with newlines (one word per line)
tr ' ' '\n' < file.txt

# Remove Windows carriage returns (CRLF → LF)
tr -d '\r' < windows.txt > unix.txt

# Replace tabs with spaces
tr '\t' ' ' < file.txt

# Replace runs of whitespace with single space
tr -s '[:space:]' ' ' < file.txt

# ROT13 encoding
tr 'A-Za-z' 'N-ZA-Mn-za-m' < file.txt

# Remove null bytes
tr -d '\000' < file.bin > cleaned.bin

# Count words: replace non-alpha with newlines, then count non-empty lines
tr -cs '[:alpha:]' '\n' < file.txt | sort | uniq -c | sort -rn

# Reverse complement SET1 example: keep only hex digits
tr -cd '[:xdigit:]\n' < file.txt
```

---

## 8. paste and join

### paste

`paste` merges lines of multiple files side by side (column merge).

#### Syntax

```
paste [OPTIONS] [FILE...]
```

#### Options

| Option | Meaning |
|--------|---------|
| `-d DELIM` | Use DELIM as separator (default: TAB); can be a list of chars (cycled) |
| `-s` | Serial mode: paste all lines of each file into one line |
| `-z` | NUL-terminated lines |

#### Examples

```bash
# Paste two files side by side (tab-separated)
paste file1.txt file2.txt

# Paste with comma separator
paste -d, file1.txt file2.txt

# Paste three files with different separators (cycled)
paste -d',:' file1.txt file2.txt file3.txt
# Output: col1:col2,col3 (: and , cycle between files)

# Paste all lines of one file into single line (serial)
paste -s file.txt

# Paste serial with comma separator
paste -s -d, file.txt

# Create two-column output from single-column list (every 2 lines)
paste - - < file.txt

# Create four-column output from single-column list
paste - - - - < file.txt

# Paste numbered list
nl file.txt | paste - -

# Combine numbered columns from separate files
paste <(cut -d: -f1 /etc/passwd) <(cut -d: -f3 /etc/passwd)

# Interleave two files line by line
paste -d'\n' file1.txt file2.txt | cat
```

### join

`join` joins two files on a common field (relational join). Both files must be sorted on the join field.

#### Syntax

```
join [OPTIONS] FILE1 FILE2
```

#### Options

| Option | Meaning |
|--------|---------|
| `-1 FIELD` | Join on FIELD in file 1 (default: 1) |
| `-2 FIELD` | Join on FIELD in file 2 (default: 1) |
| `-t CHAR` | Field separator (default: any whitespace) |
| `-i` | Case-insensitive comparison |
| `-a FILENUM` | Print unpairable lines from file FILENUM (1 or 2) |
| `-v FILENUM` | Print ONLY unpairable lines from file FILENUM |
| `-o FORMAT` | Output format: space-separated list of `FILENUM.FIELD` |
| `-e STRING` | Replace missing fields with STRING |
| `--header` | Treat first line as header (join and print) |
| `-z` | NUL-terminated |

#### Examples

```bash
# Inner join on first field (must be sorted)
sort -k1 file1.txt > s1.txt
sort -k1 file2.txt > s2.txt
join s1.txt s2.txt

# Join on different fields: field 2 in file1, field 1 in file2
join -1 2 -2 1 file1.txt file2.txt

# Left outer join (all from file1, with or without match in file2)
join -a 1 file1.txt file2.txt

# Full outer join
join -a 1 -a 2 file1.txt file2.txt

# Right outer join (all from file2)
join -a 2 file1.txt file2.txt

# Print only unmatched lines from file 1
join -v 1 file1.txt file2.txt

# Custom output format
join -o 1.1,2.2,1.3 file1.txt file2.txt

# Replace missing fields with "N/A"
join -a 1 -e "N/A" -o 1.1,2.2 file1.txt file2.txt

# Tab-separated join
join -t $'\t' -1 2 -2 1 data1.tsv data2.tsv

# Join /etc/passwd and /etc/shadow on username (field 1)
join -t: /etc/passwd /etc/shadow

# Case-insensitive join
join -i file1.txt file2.txt
```

---

## 9. diff and patch

### diff

`diff` compares two files line by line and shows differences.

#### Syntax

```
diff [OPTIONS] FILE1 FILE2
diff [OPTIONS] DIR1 DIR2
```

#### Options

| Option | Meaning |
|--------|---------|
| `-u [N]` | Unified format with N lines of context (default 3) |
| `-c [N]` | Context format with N lines of context |
| `-y` | Side-by-side output |
| `-n` | RCS format |
| `-e` | ed script format |
| `-q` | Report only whether files differ |
| `-i` | Case-insensitive |
| `-b` | Ignore whitespace changes |
| `-w` | Ignore all whitespace |
| `-B` | Ignore blank line changes |
| `-r` | Recursive directory comparison |
| `-l` | Paginate output (like more) |
| `-s` | Report when files are identical |
| `-N` | Treat absent files as empty (with -r) |
| `-a` | Treat all files as text |
| `--color` | Colorize output |
| `-x PATTERN` | Exclude files matching PATTERN (with -r) |
| `-X FILE` | Read exclusion patterns from FILE |
| `--strip-trailing-cr` | Strip carriage return on input |

#### Unified Format Explanation

```
--- file1   (original file, with timestamp)
+++ file2   (new file, with timestamp)
@@ -L,S +L,S @@  (chunk header: line L, S lines from each file)
 context line      (space: unchanged)
-removed line      (minus: only in file1)
+added line        (plus: only in file2)
```

#### Examples

```bash
# Basic diff
diff old.txt new.txt

# Unified diff (most common format for patches)
diff -u old.txt new.txt

# Unified diff with more context
diff -u3 old.txt new.txt   # 3 lines context (default)
diff -u10 old.txt new.txt  # 10 lines context

# Save patch to file
diff -u old.txt new.txt > changes.patch

# Side-by-side comparison
diff -y --width=120 file1.txt file2.txt

# Recursive directory diff
diff -r dir1/ dir2/

# Recursive diff, unified, excluding .git
diff -ru --exclude='.git' dir1/ dir2/

# Ignore whitespace
diff -w file1.txt file2.txt

# Ignore blank lines
diff -B file1.txt file2.txt

# Just report if different
diff -q file1.txt file2.txt && echo "same" || echo "different"

# Compare two commands' output
diff <(command1) <(command2)

# Diff two sorted versions of the same file
diff <(sort file1.txt) <(sort file2.txt)

# Word-level diff (using wdiff or diff --word-diff)
diff --word-diff file1.txt file2.txt

# Color output
diff --color=always file1.txt file2.txt

# Check if two binary files differ
diff -q binary1 binary2

# Three-way diff (merge)
diff3 mine.txt original.txt theirs.txt
```

### patch

`patch` applies a diff file to the original source.

#### Syntax

```
patch [OPTIONS] [ORIGINAL_FILE] < PATCHFILE
patch [OPTIONS] -i PATCHFILE [ORIGINAL_FILE]
```

#### Options

| Option | Meaning |
|--------|---------|
| `-p N` | Strip N leading path components from filenames in patch |
| `-R` | Reverse — apply patch in reverse (undo it) |
| `-i FILE` | Read patch from FILE |
| `-o FILE` | Write output to FILE (don't modify original) |
| `-b` | Create backup of original before patching |
| `--backup-if-mismatch` | Backup only if patch doesn't apply cleanly |
| `-u` | Interpret as unified diff |
| `-c` | Interpret as context diff |
| `-N` | Ignore patches that are already applied |
| `--dry-run` | Test if patch applies without changing files |
| `-F N` | Set fuzz factor to N (lines of context to ignore) |
| `-s` | Silent — only report errors |
| `-d DIR` | Change to DIR before applying |
| `--no-backup-if-mismatch` | Don't create backup files |

#### Examples

```bash
# Apply a patch (patch in same directory)
patch < changes.patch

# Apply with path stripping (-p1 strips one leading path component)
# Use -p1 when patch was made from repo root (paths like a/src/file.c)
patch -p1 < changes.patch

# Apply to specific file
patch original.txt < changes.patch

# Reverse a patch (undo)
patch -R -p1 < changes.patch

# Dry run — check if patch applies
patch --dry-run -p1 < changes.patch

# Create backup before patching
patch -b -p1 < changes.patch
# Creates original.txt.orig

# Apply patch to a different output file
patch original.txt -o patched.txt < changes.patch

# Strip specific number of path levels
# Patch has: --- a/src/main/java/App.java
patch -p2 < changes.patch   # strips "a/src", applies to "main/java/App.java"

# Complete workflow: make change, create patch, apply elsewhere
diff -u original.txt modified.txt > fix.patch
patch -p0 original_copy.txt < fix.patch
```

---

## 10. wc

### Overview

`wc` counts lines, words, characters, or bytes in files.

### Syntax

```
wc [OPTIONS] [FILE...]
```

### Options

| Option | Meaning |
|--------|---------|
| `-l` | Count lines (newlines) |
| `-w` | Count words (whitespace-separated tokens) |
| `-c` | Count bytes |
| `-m` | Count characters (multibyte-aware) |
| `-L` | Print length of longest line |
| `-z` | NUL-terminated lines |

Default (no options): print lines, words, bytes.

### Examples

```bash
# Count lines in a file
wc -l file.txt

# Count words
wc -w file.txt

# Count bytes
wc -c file.txt

# Count characters (UTF-8 aware)
wc -m file.txt

# All counts
wc file.txt

# Multiple files (also prints total)
wc -l *.txt

# Count lines from stdin
cat file.txt | wc -l

# How many processes are running
ps aux | wc -l

# Count files in a directory
ls -1 | wc -l

# Find the longest line
wc -L file.txt

# Count total lines in all .py files recursively
find . -name "*.py" -exec wc -l {} + | tail -1

# Count words after grep filter
grep "ERROR" app.log | wc -l

# Print only the number (no filename) from stdin
wc -l < file.txt

# Byte size of string
echo -n "hello" | wc -c
```

---

## 11. head and tail

### head

`head` outputs the first part of files.

#### Syntax

```
head [OPTIONS] [FILE...]
```

#### Options

| Option | Meaning |
|--------|---------|
| `-n K` | Print first K lines (default 10) |
| `-n -K` | Print all but last K lines |
| `-c K` | Print first K bytes |
| `-c -K` | Print all but last K bytes |
| `-q` | Suppress file headers |
| `-v` | Always print file headers |
| `-z` | NUL-terminated |

#### Examples

```bash
# First 10 lines (default)
head file.txt

# First 20 lines
head -n 20 file.txt

# All but last 5 lines
head -n -5 file.txt

# First 100 bytes
head -c 100 file.txt

# First line only
head -1 file.txt

# Skip header and process (using tail)
tail -n +2 file.txt   # from line 2 to end

# First line of multiple files
head -1 *.txt

# First 4k bytes (useful for checking file magic)
head -c 4096 binary_file | xxd
```

### tail

`tail` outputs the last part of files.

#### Syntax

```
tail [OPTIONS] [FILE...]
```

#### Options

| Option | Meaning |
|--------|---------|
| `-n K` | Print last K lines (default 10) |
| `-n +K` | Print from line K to end |
| `-c K` | Print last K bytes |
| `-c +K` | Print from byte K to end |
| `-f` | Follow: keep file open and print new data as it appears |
| `-F` | Like -f but also handles file rotation (reopens if renamed/deleted) |
| `--pid=PID` | With -f, stop following when process PID exits |
| `-s N` | With -f, sleep N seconds between checks |
| `-q` | Suppress file headers |
| `-v` | Always print file headers |
| `-z` | NUL-terminated |

#### Examples

```bash
# Last 10 lines (default)
tail file.txt

# Last 50 lines
tail -n 50 file.txt

# From line 5 to end (skip first 4 lines)
tail -n +5 file.txt

# Skip header line (from line 2 to end)
tail -n +2 data.csv

# Last 100 bytes
tail -c 100 file.txt

# Follow log file in real time
tail -f /var/log/nginx/access.log

# Follow log, stop when PID exits
tail -f --pid=$! app.log &

# Follow with log rotation support (more robust than -f)
tail -F /var/log/app.log

# Follow multiple log files
tail -f /var/log/nginx/access.log /var/log/nginx/error.log

# Follow and filter with grep
tail -f app.log | grep --line-buffered "ERROR"

# Follow and parse with awk in real time
tail -f access.log | awk '{print $1, $7}'

# Last line only
tail -1 file.txt

# Print from byte 1024 to end
tail -c +1024 file.bin

# Efficiently get last 5 lines (then reverse)
tail -5 file.txt | tac

# Real-time monitoring with timestamps
tail -f app.log | while read line; do echo "$(date +%T) $line"; done
```

---

## 12. xargs

### Overview

`xargs` reads items from stdin and executes a command with those items as arguments. Essential for building command pipelines that exceed shell argument limits.

### Syntax

```
xargs [OPTIONS] [COMMAND [INITIAL-ARGS]]
```

### Options

| Option | Meaning |
|--------|---------|
| `-I REPLACE` | Replace REPLACE string in command with each input item |
| `-n N` | Pass at most N arguments per command invocation |
| `-P N` | Run up to N parallel processes |
| `-0` | Input items are NUL-terminated (use with find -print0) |
| `-d DELIM` | Use DELIM as input item delimiter |
| `-L N` | Use at most N input lines per command |
| `-r` | Do not run if stdin is empty (--no-run-if-empty) |
| `-p` | Prompt before executing each command |
| `-t` | Print command before executing (trace) |
| `-a FILE` | Read items from FILE instead of stdin |
| `-s N` | Limit command line length to N bytes |
| `-x` | Exit if command line would exceed size limit |
| `--show-limits` | Display limits and exit |

### Examples

```bash
# Basic use: pass all lines as args to echo
echo "a b c" | xargs echo

# Delete files found by find (safe with -print0)
find . -name "*.tmp" -print0 | xargs -0 rm -f

# Process one file at a time (-n 1)
find . -name "*.log" | xargs -n 1 gzip

# Replace placeholder (-I {})
find . -name "*.txt" | xargs -I {} cp {} {}.bak

# Parallel processing (4 workers)
find . -name "*.jpg" -print0 | xargs -0 -P 4 -I {} convert {} -resize 800x600 {}

# Run command on each file, showing command (-t)
ls *.conf | xargs -t -I {} cp {} /backup/

# Avoid running if no input (-r)
find . -name "*.tmp" | xargs -r rm

# Process N items at a time (batch)
cat urls.txt | xargs -n 5 curl -O

# Use with grep to search specific files
find . -name "*.py" -print0 | xargs -0 grep -l "import numpy"

# Rename files (with shell -c)
ls *.jpeg | xargs -I {} bash -c 'mv "$1" "${1%.jpeg}.jpg"' _ {}

# Pass args from file
xargs -a file_list.txt -I {} chmod 644 {}

# Use custom delimiter
echo "file1:file2:file3" | xargs -d: -n1 echo

# Combine with find and parallel compression
find /logs -name "*.log" -mtime +7 -print0 | xargs -0 -P 8 -I {} gzip {}

# Download list of URLs in parallel (5 at a time)
cat urls.txt | xargs -n 1 -P 5 wget -q

# Count lines in multiple files (xargs handles large file lists)
find . -name "*.py" | xargs wc -l

# Prompt before each action
ls *.old | xargs -p -I {} rm {}

# Build complex command with multiple replacements (use sh -c)
find . -name "*.txt" -print0 | xargs -0 -I FILE sh -c 'echo "Processing FILE"; wc -l FILE'
```

### xargs vs find -exec

```bash
# These are equivalent but xargs is more efficient for many files:
find . -name "*.c" -exec gcc -c {} \;        # spawns one process per file
find . -name "*.c" | xargs gcc -c            # batches — fewer processes

# find -exec with + (like xargs) is most efficient:
find . -name "*.c" -exec gcc -c {} +         # batches automatically
```

---

## 13. tee

### Overview

`tee` reads stdin and writes to both stdout and one or more files simultaneously. Like a T-junction in a pipe.

### Syntax

```
tee [OPTIONS] [FILE...]
```

### Options

| Option | Meaning |
|--------|---------|
| `-a` | Append to files instead of overwriting |
| `-i` | Ignore SIGINT |
| `-p` | Diagnose errors writing to non-pipes |
| `--output-error=MODE` | Set behavior on write error: `warn`, `warn-nopipe`, `exit`, `exit-nopipe` |

### Examples

```bash
# Write to file and display on terminal
command | tee output.log

# Append to log while showing output
command | tee -a running.log

# Write to multiple files
command | tee file1.txt file2.txt

# Write to file and pipe to another command
cat data.txt | tee backup.txt | grep "ERROR"

# Save intermediate pipeline output for debugging
cat input.txt | tee /tmp/stage1.txt | sed 's/foo/bar/' | tee /tmp/stage2.txt | awk '{print $1}'

# Use with sudo (write to root-owned file)
echo "config" | sudo tee /etc/app.conf

# Append to root-owned log as non-root
echo "entry" | sudo tee -a /var/log/app.log

# Discard stdout but keep file (redirect to /dev/null)
command | tee output.log > /dev/null

# Write to file in background while main pipeline continues
long_command | tee >(gzip > output.gz) | process_output

# Process substitution: write to multiple files with different transforms
cat data.txt | tee >(grep "ERROR" > errors.txt) >(grep "WARN" > warnings.txt) > /dev/null

# Keep a log of all build output
make 2>&1 | tee build.log

# Write stderr and stdout to file
command 2>&1 | tee output.log
```

---

## 14. column

### Overview

`column` formats input into tabular columns. Useful for making output readable.

### Syntax

```
column [OPTIONS] [FILE...]
```

### Options

| Option | Meaning |
|--------|---------|
| `-t` | Create a table; determine column widths from input |
| `-s SEP` | Specify column separator for `-t` (default: whitespace) |
| `-o SEP` | Specify output column separator for `-t` (default: two spaces) |
| `-n` | Don't merge empty columns (with `-t`) |
| `-e` | Extend each row to full width (with `-t`) |
| `-H COLS` | Specify header columns (column header for `-t`) |
| `-R COLS` | Right-align specified columns |
| `-L COLS` | Left-align specified columns (default) |
| `-J` | JSON output (util-linux 2.37+) |
| `-c N` | Column output width (for non-table mode) |
| `-x` | Fill columns across before down (non-table mode) |

Note: The `-s`, `-o`, `-n`, `-e`, `-H`, `-R`, `-L`, `-J` options require util-linux's column (version 2.23+). The BSd/macOS version is more limited.

### Examples

```bash
# Format ps output as table
ps aux | column -t

# Format /etc/passwd as table
column -t -s: /etc/passwd

# Format CSV as table
column -t -s, data.csv

# Custom output separator
column -t -s, -o' | ' data.csv

# Multi-column display (like ls)
ls | column

# Specify width for multi-column display
ls | column -c 80

# Fill columns across (left-to-right) instead of down
ls | column -x

# Right-align column 2 and 3
printf "Name Price Qty\nApple 1.50 100\nBanana 0.75 200\n" | column -t -R 2,3

# Format mount output
mount | column -t

# Create readable table from colon-separated data
awk -F: '{print $1, $3, $7}' /etc/passwd | column -t

# JSON output (modern util-linux)
column -t -s: -J --json-key-type string /etc/passwd 2>/dev/null || echo "JSON not supported on this version"

# Align environment variables
env | sort | column -t -s=

# Format key=value config file
grep -v "^#" /etc/some.conf | column -t -s=

# Table with headers from first line
{ echo "NAME UID SHELL"; awk -F: '$3>=1000 {print $1, $3, $7}' /etc/passwd; } | column -t
```

---

## 15. Bash String Operations

### Overview

Bash provides powerful parameter expansion for string manipulation — no external tools needed. All operations use the `${...}` syntax.

### Length

| Expression | Meaning |
|------------|---------|
| `${#var}` | Length of string in `var` |
| `${#arr[@]}` | Number of elements in array |
| `${#arr[N]}` | Length of element N in array |

```bash
str="Hello, World"
echo ${#str}       # 12

arr=(a bb ccc)
echo ${#arr[@]}    # 3
echo ${#arr[1]}    # 2 (length of "bb")
```

### Substring Extraction

| Expression | Meaning |
|------------|---------|
| `${var:offset}` | From offset to end (0-based) |
| `${var:offset:length}` | Length characters starting at offset |
| `${var: -N}` | Last N characters (space before minus required) |
| `${var: -N:M}` | M characters starting at N from end |

```bash
str="Hello, World"
echo ${str:7}       # World
echo ${str:7:5}     # World
echo ${str:0:5}     # Hello
echo ${str: -5}     # World
echo ${str: -5:3}   # Wor
```

### Prefix Removal (# and ##)

| Expression | Meaning |
|------------|---------|
| `${var#pattern}` | Remove shortest match of pattern from front |
| `${var##pattern}` | Remove longest match of pattern from front |

```bash
path="/home/user/docs/file.txt"
echo ${path#/}           # home/user/docs/file.txt  (removes leading /)
echo ${path#*/}          # home/user/docs/file.txt  (shortest: removes first /)
echo ${path##*/}         # file.txt  (longest: removes up to last /)

filename="archive.tar.gz"
echo ${filename#*.}      # tar.gz  (removes up to first dot)
echo ${filename##*.}     # gz  (removes up to last dot)

url="https://www.example.com/page"
echo ${url#*://}         # www.example.com/page
echo ${url##*/}          # page
```

### Suffix Removal (% and %%)

| Expression | Meaning |
|------------|---------|
| `${var%pattern}` | Remove shortest match of pattern from end |
| `${var%%pattern}` | Remove longest match of pattern from end |

```bash
path="/home/user/docs/file.txt"
echo ${path%/*}          # /home/user/docs  (dirname)
echo ${path%%/*}         # (empty — removes all after first /)

filename="archive.tar.gz"
echo ${filename%.*}      # archive.tar  (removes last extension)
echo ${filename%%.*}     # archive  (removes all extensions)

version="v1.2.3-beta"
echo ${version%-*}       # v1.2.3  (removes -beta suffix)

# Common idiom: strip extension
file="document.pdf"
base=${file%.*}          # document
ext=${file##*.}          # pdf
```

### Substitution (/ and //)

| Expression | Meaning |
|------------|---------|
| `${var/pattern/replace}` | Replace first match of pattern with replace |
| `${var//pattern/replace}` | Replace ALL matches |
| `${var/#pattern/replace}` | Replace if pattern matches at START |
| `${var/%pattern/replace}` | Replace if pattern matches at END |
| `${var/pattern}` | Delete first match (replace with empty) |
| `${var//pattern}` | Delete all matches |

```bash
str="foo bar foo baz foo"
echo ${str/foo/XXX}      # XXX bar foo baz foo  (first only)
echo ${str//foo/XXX}     # XXX bar XXX baz XXX  (all)
echo ${str/#foo/START}   # START bar foo baz foo  (anchor at start)
echo ${str/%foo/END}     # foo bar foo baz END  (anchor at end)
echo ${str//foo}         # " bar  baz "  (delete all)

# Replace spaces with underscores
name="John Doe Smith"
echo ${name// /_}        # John_Doe_Smith

# Remove all digits
str="abc123def456"
echo ${str//[0-9]/}      # abcdef
```

### Case Modification (Bash 4+)

| Expression | Meaning |
|------------|---------|
| `${var^}` | Uppercase first character |
| `${var^^}` | Uppercase all characters |
| `${var,}` | Lowercase first character |
| `${var,,}` | Lowercase all characters |
| `${var^pattern}` | Uppercase chars matching pattern |
| `${var^^pattern}` | Uppercase all chars matching pattern |

```bash
str="hello WORLD"
echo ${str^}     # Hello WORLD
echo ${str^^}    # HELLO WORLD
echo ${str,}     # hello WORLD
echo ${str,,}    # hello world

# Title case (capitalize each word)
str="hello world foo"
echo ${str@u}              # Bash 5.1+: Uppercase all
# Or with older bash:
echo "${str}" | sed 's/\b./\u&/g'

# Uppercase only vowels
str="hello"
echo ${str^^[aeiou]}       # hEllO
```

### Default Values

| Expression | Meaning |
|------------|---------|
| `${var:-default}` | Use default if var is unset or empty |
| `${var-default}` | Use default if var is unset (not empty) |
| `${var:=default}` | Assign default if var is unset or empty |
| `${var=default}` | Assign default if var is unset |
| `${var:+alternate}` | Use alternate if var IS set and non-empty |
| `${var+alternate}` | Use alternate if var IS set (even if empty) |
| `${var:?message}` | Error with message if var is unset or empty |
| `${var?message}` | Error with message if var is unset |

```bash
name=""
echo ${name:-"Anonymous"}    # Anonymous (name is empty)
echo ${name-"Anonymous"}     # (empty — name IS set, just empty)

unset name
echo ${name:-"Anonymous"}    # Anonymous (name is unset)

# Set default if unset
echo ${name:="Default Name"} # Default Name; also sets $name
echo $name                   # Default Name

# Alternate: use only when set
debug=""
echo "Mode: ${debug:+DEBUG}"  # Mode: (empty — debug is empty)
debug=1
echo "Mode: ${debug:+DEBUG}"  # Mode: DEBUG

# Require variable (exit with error if unset)
: ${REQUIRED_VAR:?"REQUIRED_VAR must be set"}
```

### Indirection and Name References (Bash 4.3+)

```bash
# Variable indirection
varname="greeting"
greeting="Hello"
echo ${!varname}     # Hello

# nameref (Bash 4.3+)
declare -n ref=greeting
echo $ref            # Hello
ref="Hi"
echo $greeting       # Hi

# List variables matching prefix
prefix_one=1
prefix_two=2
echo ${!prefix_@}    # prefix_one prefix_two

# Indirect array access
arr=(a b c)
idx=1
echo ${arr[$idx]}    # b
```

### String Testing Patterns

```bash
str="hello world"

# Test if string contains substring
if [[ "$str" == *"world"* ]]; then echo "contains world"; fi

# Test prefix
if [[ "$str" == hello* ]]; then echo "starts with hello"; fi

# Test suffix
if [[ "$str" == *world ]]; then echo "ends with world"; fi

# Regex match (=~)
if [[ "$str" =~ ^hello\ (.+)$ ]]; then
    echo "Matched; captured: ${BASH_REMATCH[1]}"  # world
fi
```

### Practical Idioms

```bash
# Get basename without external command
path="/home/user/file.txt"
basename="${path##*/}"       # file.txt

# Get dirname without external command
dirname="${path%/*}"         # /home/user

# Strip extension
noext="${basename%.*}"       # file

# Get extension
ext="${basename##*.}"        # txt

# Trim leading whitespace
ltrim() { local v="$1"; echo "${v#"${v%%[! ]*}"}"; }

# Trim trailing whitespace
rtrim() { local v="$1"; echo "${v%"${v##*[! ]}"}"; }

# Trim both
trim() { local v="$1"; v="${v#"${v%%[! ]*}"}"; echo "${v%"${v##*[! ]}"}"; }

# Repeat a string N times
printf '%0.s=' {1..40}   # 40 equal signs

# Pad string to width
printf '%-20s' "hello"   # right-padded to 20
printf '%20s' "hello"    # left-padded to 20

# Join array elements with delimiter
arr=(a b c d)
IFS=, joined="${arr[*]}"
echo "$joined"           # a,b,c,d

# Split string into array
str="a:b:c:d"
IFS=: read -ra arr <<< "$str"
echo "${arr[2]}"         # c

# Check if string is a number
[[ "$str" =~ ^[0-9]+$ ]] && echo "is integer"
[[ "$str" =~ ^[0-9]*\.[0-9]+$ ]] && echo "is float"

# URL encode (basic)
urlencode() {
    local s="$1"
    local encoded=""
    local i c
    for ((i=0; i<${#s}; i++)); do
        c="${s:$i:1}"
        case "$c" in
            [a-zA-Z0-9.~_-]) encoded+="$c" ;;
            *) printf -v encoded '%s%%%02X' "$encoded" "'$c" ;;
        esac
    done
    echo "$encoded"
}

# Count substring occurrences (no external tools)
count_substr() {
    local str="$1" sub="$2"
    local count=0 pos=0
    while [[ "${str:$pos}" == *"$sub"* ]]; do
        (( count++ ))
        pos=$(( pos + ${#sub} + ${str%%"$sub"*} ))
        # simpler:
        str="${str#*"$sub"}"
    done
    echo $count
}
# Simpler version using tr+wc:
echo "foo bar foo baz foo" | tr ' ' '\n' | grep -c "^foo$"
```

---

## Quick Reference: Pipeline Recipes

### Log Analysis

```bash
# Top 10 IPs in nginx access log
awk '{print $1}' /var/log/nginx/access.log | sort | uniq -c | sort -rn | head -10

# Count HTTP status codes
awk '{print $9}' /var/log/nginx/access.log | sort | uniq -c | sort -rn

# Extract all ERROR lines with context
grep -B2 -A5 "ERROR" app.log

# Show requests per minute (last 100 lines)
tail -100 access.log | awk '{print $4}' | cut -c2-18 | cut -d: -f1-3 | uniq -c

# Find slowest requests (if response time is last field)
awk '{print $NF, $0}' access.log | sort -n | tail -20 | cut -d' ' -f2-
```

### File Processing

```bash
# Find and replace in multiple files
grep -rl "oldstring" . | xargs sed -i 's/oldstring/newstring/g'

# Remove blank lines from all .txt files
for f in *.txt; do sed -i '/^[[:space:]]*$/d' "$f"; done

# Add line numbers to a file
cat -n file.txt   # or: nl file.txt

# Remove duplicate lines preserving order
awk '!seen[$0]++' file.txt

# Merge multiple CSV files (skip header after first)
awk 'FNR==1 && NR!=1 {next} {print}' *.csv

# Count unique values per column in CSV
cut -d, -f2 data.csv | sort | uniq -c | sort -rn
```

### Data Transformation

```bash
# Transpose CSV (rows become columns)
awk -F, '{for(i=1;i<=NF;i++) col[i][NR]=$i; max=(NF>max?NF:max)} END{for(i=1;i<=max;i++){sep=""; for(j=1;j<=NR;j++){printf "%s%s",sep,col[i][j]; sep=","} print ""}}' data.csv

# JSON array from line-separated values
printf '[\n'; sed 's/.*/  "&",/' list.txt | sed '$s/,//'; printf ']\n'

# Convert space-separated to CSV
sed 's/ \+/,/g' data.txt

# Flatten JSON-like nested field
awk -F'"' '{print $4}' file.json

# Sum a CSV column
awk -F, '{sum += $3} END {print sum}' data.csv

# Running average
awk '{sum+=$1; print sum/NR}' numbers.txt
```

### System Administration

```bash
# Find large files and sort by size
find /var -type f -exec du -h {} + 2>/dev/null | sort -h | tail -20

# List 10 largest directories
du -sh /* 2>/dev/null | sort -h | tail -10

# Find duplicate files by MD5
find . -type f | xargs md5sum | sort | awk '$1==prev{print $2, prev_file} {prev=$1; prev_file=$2}' - 

# Extract unique domains from URLs in a file
grep -oP 'https?://[^/]+' urls.txt | sort -u

# Parse /proc/net/tcp for listening ports (convert hex to decimal)
awk 'NR>1 && $4=="0A" {printf "%d\n", strtonum("0x"substr($2,index($2,":")+1))}' /proc/net/tcp | sort -n
```

---

*Reference generated for Zia Venture Group AI Stack — RAG-ready for Open WebUI.*
