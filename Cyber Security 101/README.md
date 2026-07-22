### Cybersecurity Research Resources

Knowing **where** to search is just as important as knowing **what** to search for. These platforms are widely used by both offensive and defensive security professionals.

### Shodan

Shodan is often called the **“search engine for the Internet of Things”**. It continuously scans the internet for publicly exposed devices and services.

**Use cases:**

- Finding specific software versions (e.g., vulnerable Apache servers)
- Discovering exposed industrial control systems, cameras, routers, etc.
- During penetration testing and reconnaissance

**Useful Shodan Filters:**

| Filter   | Description                   | Example                   |
| -------- | ----------------------------- | ------------------------- |
| country  | Filter by country code        | country:IE                |
| port     | Filter by port number         | port:22                   |
| org      | Filter by organization or ASN | org:"Amazon Web Services" |
| hostname | Search by hostname or domain  | hostname:example.com      |

### VirusTotal

VirusTotal aggregates results from **70+ antivirus engines** and website scanners.

**What you can submit:**

- Files
- URLs
- Domains
- File hashes

**Use cases:**

- Checking if a file or link is malicious
- Gathering threat intelligence on new malware
- Blue team analysis and investigation

> **Note**: Not 100% accurate, but provides a good consensus view.

### CVE (Common Vulnerabilities and Exposures)

The **CVE** program provides a standardized way to identify and reference vulnerabilities.

- Format: CVE-YEAR-NUMBER (e.g., CVE-2025-55182)
- Some vulnerabilities receive names (e.g., Heartbleed, Log4Shell)
- Scored using **CVSS** (Common Vulnerability Scoring System) based on:
    - Impact
    - Complexity
    - Exploitability

**Related Resources:**

- **ExploitDB**: Contains CVEs along with Proof-of-Concept (PoC) exploits.

### Documentation Resources

#### Official Tool & Product Documentation

Always prioritize **official documentation** over third-party tutorials when learning or troubleshooting tools. It is usually the most accurate and up-to-date.

#### Linux Man Pages

Linux manual pages provide built-in documentation for commands and tools directly in the terminal.

**Usage:**

```Bash
man <command>
```

**Example:**

```Bash
man nc
```

Man pages are especially useful for cybersecurity tools that run in the terminal.

#### GitHub

GitHub is a valuable resource for:

- Proof-of-Concept (PoC) exploits
- Security tools and scripts
- Technical write-ups and vulnerability analyses

**Tip**: Searching a CVE ID (e.g., CVE-2026-1337) on GitHub often surfaces relevant repositories quickly.

> **Caution**: Not all PoCs are reliable. Some may be incomplete, broken, or even malicious. Always review and verify code before running it.

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Cyber%20Security%20101/Pasted%20image.png)

---

### Linux Fundamentals – Part 1

### What is Linux?

**Linux** is an open-source operating system (based on UNIX) used in a wide variety of devices and environments, including:

- Websites and web servers
- Android smartphones
- Supercomputers
- Cars, smart appliances, and industrial systems
- Enterprise servers

Linux is lightweight and powerful. Many distributions (also called “flavours”) exist. In this series, we use **Ubuntu**.

### The Terminal

Most Linux servers do **not** have a Graphical User Interface (GUI). Interaction happens through the **Terminal** (command line).

Example prompt:

```Bash
tryhackme@linux1:~$
```

### Basic Commands

| Command | Description                          | Example              |
| ------- | ------------------------------------ | -------------------- |
| echo    | Prints text to the terminal          | echo "Hello Friend!" |
| whoami  | Shows the current logged-in username | whoami               |

**Note**: Use double quotes with echo when the text contains spaces.

### Interacting with the Filesystem

| Command | Full Name               | Description                                 |
| ------- | ----------------------- | ------------------------------------------- |
| ls      | List                    | List files and directories                  |
| cd      | Change Directory        | Change to a different directory             |
| cat     | Concatenate             | Display the contents of a file              |
| pwd     | Print Working Directory | Show the full path of the current directory |

**Examples:**

```Bash
ls                    # List current directory
ls Pictures           # List contents of Pictures without entering it

cd Documents          # Change into Documents folder
cd ..                 # Go up one directory level

cat todo.txt          # View contents of todo.txt
cat /home/ubuntu/Documents/todo.txt   # View file using full path

pwd                   # Show current full path (e.g. /home/ubuntu/Documents)
```

### Searching for Files and Content

#### find – Search for files

```Bash
find -name passwords.txt          # Find a file by exact name
find -name "*.txt"                # Find all files with .txt extension
```

#### grep – Search inside files

```Bash
grep "81.143.211.90" access.log   # Search for a string in a file
```

**Recursive search** (search in current directory + all subdirectories):

```Bash
grep -R "PRETTY_NAME" /etc/
```

### Shell Operators

| Operator | Name                 | Description                                                | Example                    |
| -------- | -------------------- | ---------------------------------------------------------- | -------------------------- |
| &        | Background           | Run a command in the background                            | cp largefile.zip /backup & |
| &&       | AND                  | Run the next command **only if** the previous one succeeds | cd /tmp && ls              |
| >        | Redirect (Overwrite) | Send output to a file (overwrites existing content)        | echo "hello" > welcome     |
| >>       | Redirect (Append)    | Send output to a file (appends to existing content)        | echo "hello" >> welcome    |

**Examples:**

```Bash
echo hey > welcome          # Create/overwrite file with "hey"
echo hello >> welcome       # Append "hello" to the file

cat welcome
# Output:
# hey
# hello
```

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Cyber%20Security%20101/Pasted%20image%20(2).png)

---

### Linux Fundamentals – Part 2 (Continued)

### Command Flags & Switches

Most Linux commands accept **flags** (also called switches or options) that modify their default behaviour.

**Common Examples with ls:**

|Command|Description|
|---|---|
|ls|List visible files and directories|
|ls -a|List **all** files (including hidden ones starting with .)|
|ls --help|Show available options for the command|

### Manual Pages (man)

The man command displays the full documentation for a command.

```bash
man ls
```

Press q to quit the manual page.

### File & Directory Management Commands

| Command | Full Name        | Purpose                             | Example                |
| ------- | ---------------- | ----------------------------------- | ---------------------- |
| touch   | touch            | Create an empty file                | touch note.txt         |
| mkdir   | make directory   | Create a new directory              | mkdir myfolder         |
| cp      | copy             | Copy a file or directory            | cp note.txt note2.txt  |
| mv      | move             | Move or rename a file/directory     | mv note2.txt note3.txt |
| rm      | remove           | Delete a file                       | rm note.txt            |
| rm -R   | remove recursive | Delete a directory and its contents | rm -R myfolder         |
| file    | file             | Determine the type of a file        | file note.txt          |

**Notes:**

- cp and mv require two arguments: source and destination.
- rm -R is required to delete directories.
- You can use full paths with all of these commands (e.g. cat /home/ubuntu/Documents/todo.txt).

### File Permissions

View detailed permissions with:

```Bash
ls -lh
```

Permissions are shown in three groups:

|Group|Applies To|
|---|---|
|First 3|Owner|
|Next 3|Group|
|Last 3|Others|

**Permission Letters:**

|Letter|Meaning|Numeric Value|
|---|---|---|
|r|Read|4|
|w|Write|2|
|x|Execute|1|

**Common Numeric Permissions:**

|Symbolic|Numeric|Meaning|
|---|---|---|
|rwxrwxrwx|777|Full access for everyone|
|rwxr-xr-x|755|Owner: full, Group/Others: read + execute|
|rw-r--r--|644|Owner: read/write, Others: read only|
|rwx------|700|Only the owner has access|

**Example:**

```Bash
chmod 750 system_overview.txt
```

### Switching Users (su)

```Bash
su username          # Switch to another user
su -l username       # Switch and load the user's full environment
```

You will be prompted for the target user's password (unless you are root).

### Important Linux Directories

| Directory | Purpose                                                    |
| --------- | ---------------------------------------------------------- |
| /etc      | System configuration files (e.g. passwd, shadow, sudoers)  |
| /var      | Variable data (logs, temporary files used by services)     |
| /root     | Home directory of the root user                            |
| /tmp      | Temporary files (cleared on reboot, writable by all users) |

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Cyber%20Security%20101/Pasted%20image%20(3).png)

---
