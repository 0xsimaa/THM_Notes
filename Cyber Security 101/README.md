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

### Linux Fundamentals – Part 3

### Terminal Text Editors

#### Nano

Simple and beginner-friendly text editor.

```Bash
nano filename
```

**Useful Shortcuts** (Ctrl is shown as ^):

|Shortcut|Action|
|---|---|
|Ctrl + O|Save (Write Out)|
|Ctrl + X|Exit|
|Ctrl + W|Search|
|Ctrl + K|Cut line|
|Ctrl + U|Paste|

#### VIM

More advanced and powerful text editor. Features include:

- Highly customisable
- Syntax highlighting
- Available on almost all systems

(TryHackMe has a dedicated room for learning VIM.)

### Transferring Files

#### Download Files with wget

```Bash
wget https://example.com/file.txt
```

#### Secure Copy (scp)

**Local → Remote:**

```Bash
scp important.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt
```

**Remote → Local:**

```bash
scp ubuntu@192.168.1.30:/home/ubuntu/documents.txt notes.txt
```

#### Serve Files with Python HTTP Server

```Bash
python3 -m http.server
```

- Serves files from the current directory on **port 8000**.
- Download using:

```Bash
wget http://MACHINE_IP:8000/filename
```

> Keep the Python server running in one terminal and use another terminal for wget.

### Processes

Processes are running programs managed by the kernel. Each process has a unique **PID**.

|Command|Description|
|---|---|
|ps|Show processes for the current user|
|ps aux|Show **all** processes (including system ones)|
|top|Real-time process monitoring|
|kill PID|Terminate a process|

**Common Signals:**

- SIGTERM → Graceful termination
- SIGKILL → Force kill
- SIGSTOP → Pause process

#### Backgrounding & Foregrounding

|Action|Method|
|---|---|
|Run in background|Add & at the end|
|Pause / Send to background|Ctrl + Z|
|Bring to foreground|fg|

### Managing Services with systemctl

```bash
systemctl start apache2
systemctl stop apache2
systemctl enable apache2      # Start on boot
systemctl disable apache2
systemctl status apache2
```

### Cron Jobs (Scheduled Tasks)

Edit your crontab:

```bash
crontab -e
```

**Crontab Format:**

```text
MIN  HOUR  DOM  MON  DOW  COMMAND
```

|Field|Meaning|
|---|---|
|MIN|Minute (0–59)|
|HOUR|Hour (0–23)|
|DOM|Day of Month (1–31)|
|MON|Month (1–12)|
|DOW|Day of Week (0–7)|
|CMD|Command to execute|

**Example** – Backup every 12 hours:

```Bash
0 */12 * * * cp -R /home/user/Documents /var/backups/
```

Useful tools: [Crontab Generator](https://crontab-generator.org) and [Cron Guru](https://crontab.guru)

### Package Management (apt)

|Command|Purpose|
|---|---|
|apt update|Update package lists|
|apt install package-name|Install a package|
|apt remove package-name|Remove a package|
|add-apt-repository|Add a new repository|

**Adding a third-party repository (example):**

1. Add GPG key
2. Create a .list file in /etc/apt/sources.list.d/
3. Run apt update
4. Install the package with apt install

### Log Files

Located in **/var/log**.

Common important logs:

- Apache access & error logs
- Fail2ban logs
- UFW (firewall) logs
- Authentication logs

These logs are essential for monitoring system health and investigating security incidents.

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Cyber%20Security%20101/Pasted%20image%20(4).png)

---

### Windows Fundamentals – Part 1

### Brief History of Windows

|Version|Notes|
|---|---|
|Windows XP|Extremely popular for many years|
|Windows Vista|Poorly received and short-lived|
|Windows 7|Widely adopted after Vista|
|Windows 8 / 8.1|Short-lived|
|Windows 10|Long support cycle (support ends Oct 14, 2025)|
|**Windows 11**|Current desktop OS (Home & Pro editions)|
|Windows Server 2025|Current server OS|

> The lab machine in this room runs **Windows Server 2019 Standard**.

### Windows Desktop (GUI)

Main components of the Windows Desktop:

1. **Desktop** – Area for shortcuts, files, and folders
2. **Start Menu** – Access to apps, settings, and power options
3. **Search Box** (Cortana)
4. **Task View** – Switch between open windows
5. **Taskbar** – Shows open and pinned applications
6. **Toolbars**
7. **Notification Area** – Date/time, volume, network icons, etc.

**Useful Tips:**

- Right-click the desktop to change icon size, arrange icons, or create new items.
- Right-click the taskbar to customize which components are visible.

### File System: NTFS

Modern Windows systems use **NTFS** (New Technology File System).

|Feature|NTFS|FAT32|
|---|---|---|
|Max File Size|Very large|4 GB limit|
|Permissions|Yes (detailed)|No|
|Compression|Yes|No|
|Encryption (EFS)|Yes|No|
|Journaling|Yes (can recover after crash)|No|

**NTFS Permissions:**

- Full control
- Modify
- Read & Execute
- List folder contents
- Read
- Write

**How to view permissions:**

1. Right-click file/folder → **Properties**
2. Go to the **Security** tab

**Alternate Data Streams (ADS)** NTFS allows files to contain more than one stream of data.

- Legitimate use: Marking files downloaded from the Internet
- Malicious use: Hiding data (used by some malware)

### Important Folders

|Path|Purpose|
|---|---|
|C:\Windows|Contains the operating system files|
|C:\Windows\System32|Critical system files and tools|
|C:\Users\|User profile folders|

**Environment Variable:**

- %windir% → Points to the Windows directory (usually C:\Windows)

> **Warning:** Be extremely careful when modifying anything inside System32. Deleting files here can make Windows unbootable.


### User Accounts

There are two main account types on a local Windows system:

|Account Type|Capabilities|
|---|---|
|**Administrator**|Can install software, manage users, change system settings|
|**Standard User**|Limited to their own files and settings|

**User Profile Location:** C:\Users\Username

**Useful Tool:**

```text
lusrmgr.msc
```

Opens **Local Users and Groups** management console.

### User Account Control (UAC)

UAC is a security feature that prevents programs from making unauthorized system changes.

- When a standard user (or even an admin in a non-elevated session) tries to perform a privileged action, Windows shows a consent prompt.
- The built-in Administrator account is not affected by UAC by default.
- Programs that require elevation show a **shield icon**.

### Settings vs Control Panel

|Menu|Purpose|
|---|---|
|**Settings**|Modern interface (introduced in Windows 8). Primary place for most user changes.|
|**Control Panel**|Older, more advanced system configuration tools.|

You can often start in **Settings** and be redirected to the **Control Panel** for deeper options (e.g., Network Adapter settings).

### Task Manager

**How to open:**

- Right-click the taskbar → **Task Manager**
- Or press Ctrl + Shift + Esc

**Main Tabs:**

- Processes
- Performance
- Users
- Details
- Services

Task Manager shows running applications, CPU/RAM usage, and allows you to end unresponsive processes.

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Cyber%20Security%20101/Pasted%20image%20(5).png)

---

### Windows Fundamentals – Part 2

### System Configuration (MSConfig)

**Purpose:** Advanced troubleshooting tool, mainly used to diagnose startup issues.

**How to open:**

- Search for msconfig in the Start Menu
- Requires local administrator rights

**Tabs:**

|Tab|Purpose|
|---|---|
|**General**|Choose boot mode: Normal / Diagnostic / Selective|
|**Boot**|Configure boot options|
|**Services**|View and manage system services|
|**Startup**|Shows startup items (on client Windows; limited on Server)|
|**Tools**|List of useful system utilities that can be launched|

> On **Windows Server**, startup programs are managed through the **Startup folder** (Win + R → shell:startup) instead of the Startup tab in MSConfig or Task Manager.

### Advanced System Settings

**How to open:** Search for **“View advanced system settings”**

#### Performance Options

- Controls visual effects and virtual memory (page file)
- Page file is used when physical RAM is full

#### Startup and Recovery

- Configures what happens when Windows crashes (Blue Screen of Death)
- Crash dump types:
    - Automatic memory dump
    - Kernel memory dump
    - Small memory dump (256 KB)
    - Complete memory dump
    - None

### User Account Control (UAC) Settings

UAC has four notification levels:

| Level                      | Description                                                  |
| -------------------------- | ------------------------------------------------------------ |
| **Always notify**          | Highest security – notifies for all changes (Secure Desktop) |
| **Notify for apps**        | Default – notifies only when apps try to make changes        |
| **Notify without dimming** | Same as above, but desktop does not dim                      |
| **Never notify**           | UAC is effectively disabled (not recommended)                |

### Computer Management (compmgmt.msc)

Contains three main sections:

#### 1. System Tools

- **Task Scheduler** → Create and manage automated tasks
- **Event Viewer** → View system, security, and application logs
- **Shared Folders** → View current shares, sessions, and open files
- **Local Users and Groups** (lusrmgr.msc)
- **Performance Monitor** (perfmon)
- **Device Manager** → Manage hardware

#### 2. Storage

- **Disk Management** → Create, shrink, extend partitions, change drive letters

#### 3. Services and Applications

- **Services** → View and manage Windows services
- **WMI Control** → Windows Management Instrumentation settings

**Service Startup Types:**

- Automatic
- Manual
- Disabled

### System Information (msinfo32)

Provides a comprehensive overview of the system.

**Main sections:**

- **System Summary** – General hardware and OS information
- **Hardware Resources**
- **Components** – Details about installed hardware
- **Software Environment** – Drivers, environment variables, network connections, etc.

You can also search within the tool (e.g., search for “IP address”).

### Resource Monitor (resmon)

Real-time monitoring tool that shows detailed resource usage.

**Tabs:**

- **Overview**
- **CPU**
- **Memory**
- **Disk**
- **Network**

Useful for advanced performance troubleshooting.

### Command Prompt Basics

|Command|Description|
|---|---|
|hostname|Shows computer name|
|whoami|Shows current logged-in user|
|ipconfig|Displays network configuration|
|ipconfig /?|Shows help for a command|
|netstat|Shows active network connections|
|net|Manage network resources (shares, users, sessions, etc.)|
|cls|Clears the command prompt screen|

**Useful net sub-commands:**

- net user
- net localgroup
- net share
- net session

### Windows Registry (regedit)

Central hierarchical database that stores configuration settings for:

- User profiles
- Installed applications
- Hardware
- System settings

> **Warning:** Editing the registry incorrectly can break the system. Only advanced users should modify it.


![](https://github.com/0xsimaa/THM_Notes/blob/main/Cyber%20Security%20101/Pasted%20image%20(6).png)

---

### Windows Fundamentals – Part 3: Security Features
### Windows Update

Windows Update provides:

- Security updates
- Feature enhancements
- Patches for Windows and other Microsoft products (e.g., Microsoft Defender)

**Key points:**

- Updates are usually released on **Patch Tuesday** (2nd Tuesday of each month).
- Critical updates can be released outside of Patch Tuesday.
- In modern Windows (10/11), updates cannot be permanently skipped — only postponed.

**How to open:**

- Settings → Windows Update
- Or run: control /name Microsoft.WindowsUpdate

### Windows Security

Windows Security is the central dashboard for device protection.

**Protection Areas:**

- Virus & threat protection
- Firewall & network protection
- App & browser control
- Device security

**Status Icons:**

|Color|Meaning|
|---|---|
|Green|Device is protected|
|Yellow|Recommendation available|
|Red|Immediate action required|

### Virus & Threat Protection

#### Current Threats

- **Quick Scan** → Scans common locations
- **Full Scan** → Scans entire system
- **Custom Scan** → Scans selected files/folders

#### Threat History

- Last scan results
- Quarantined threats
- Allowed threats

#### Key Settings

|Setting|Description|
|---|---|
|**Real-time protection**|Detects and blocks malware in real time|
|**Cloud-delivered protection**|Uses latest cloud threat data|
|**Automatic sample submission**|Sends samples to Microsoft|
|**Controlled folder access**|Protects important folders from ransomware|
|**Exclusions**|Files/folders excluded from scanning (use carefully)|

> **Tip:** You can right-click any file/folder → **Scan with Microsoft Defender**.


### Firewall & Network Protection

Windows Firewall controls inbound and outbound traffic.

**Firewall Profiles:**

|Profile|Used When|
|---|---|
|**Domain**|Connected to a domain network|
|**Private**|Home or trusted networks|
|**Public**|Public networks (cafés, airports, etc.)|

You can:

- Turn the firewall on/off per profile
- Block all incoming connections
- Allow specific apps through the firewall

**Advanced Settings:** Open with WF.msc

> **Recommendation:** Keep the firewall enabled unless you fully understand the risks.


### App & Browser Control

#### Microsoft Defender SmartScreen

Protects against:

- Phishing websites
- Malicious apps
- Dangerous downloads

**Options:**

- Warn
- Block
- Off

#### Exploit Protection

Built-in protections against common exploitation techniques.

### Device Security

#### Core Isolation

- **Memory Integrity** → Prevents attacks from injecting malicious code into critical processes.

#### Trusted Platform Module (TPM)

Hardware-based security chip that provides cryptographic functions and helps protect against tampering.

#### BitLocker

Full-disk encryption feature that protects data if the device is lost or stolen. Works best when combined with a TPM.

### Volume Shadow Copy Service (VSS)

Also known as **System Protection** or **Shadow Copies**.

**What it does:**

- Creates point-in-time snapshots (restore points) of the system.

**You can:**

- Create a restore point
- Perform a System Restore
- Configure restore settings
- Delete restore points

**Security Note:** Ransomware often tries to delete Volume Shadow Copies to prevent recovery. Having offline/off-site backups is essential.

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Cyber%20Security%20101/Pasted%20image%20(7).png)

---

### Windows Domains & Active Directory

### What is a Windows Domain?

A **Windows Domain** is a group of users and computers managed centrally by a business.

The central repository is called **Active Directory (AD)**. The server that runs Active Directory is called a **Domain Controller (DC)**.

**Main advantages:**

- Centralised identity management
- Centralised security policy management (via Group Policy)

### Active Directory Objects

Active Directory stores information about objects on the network.

#### Users

Users are **security principals** (can be authenticated and assigned privileges).

Two types:

- **People** → Employees who need access to the network
- **Services** → Accounts used by services (IIS, MSSQL, etc.)

#### Machines

Every computer that joins the domain gets a **machine account**.

- Naming convention: ComputerName$ (e.g., DC01$)
- Passwords are automatically rotated and very long (~120 characters)

#### Security Groups

Groups allow you to assign permissions to multiple users/machines at once.

| Group                  | Description                                       |
| ---------------------- | ------------------------------------------------- |
| **Domain Admins**      | Full administrative rights over the entire domain |
| **Server Operators**   | Can administer Domain Controllers                 |
| **Backup Operators**   | Can access any file (for backups)                 |
| **Account Operators**  | Can create/modify accounts                        |
| **Domain Users**       | All user accounts in the domain                   |
| **Domain Computers**   | All computers in the domain                       |
| **Domain Controllers** | All Domain Controllers                            |

### Organizational Units (OUs) vs Security Groups

| Feature         | Organizational Units (OUs)       | Security Groups                  |
| --------------- | -------------------------------- | -------------------------------- |
| **Purpose**     | Apply policies (GPOs)            | Grant permissions to resources   |
| **Membership**  | A user can only be in **one** OU | A user can be in **many** groups |
| **Typical Use** | Department-based policies        | Access to shares, printers, etc. |

### Active Directory Users and Computers

Tool used to manage users, groups, and computers.

**Default Containers:**

- **Builtin** → Default groups
- **Computers** → New machines join here by default
- **Domain Controllers** → Contains DCs
- **Users** → Default domain users and groups
- **Managed Service Accounts**

**Note:** OUs are protected against accidental deletion by default. To delete an OU:

1. Enable **Advanced Features** (View menu)
2. Right-click OU → Properties → Object tab
3. Uncheck “Protect object from accidental deletion”

### Delegation

Delegation allows you to give specific users limited control over an OU without making them Domain Admins.

**Common use case:** Allow IT Support to reset passwords.

**How to delegate:**

1. Right-click the OU → **Delegate Control**
2. Select the user
3. Choose the task (e.g., “Reset user passwords and force password change at next logon”)

**Example PowerShell commands (as delegated user):**

```PowerShell
Set-ADAccountPassword sophie -Reset -NewPassword (Read-Host -AsSecureString -Prompt 'New Password')

Set-ADUser -ChangePasswordAtLogon $true -Identity sophie
```

