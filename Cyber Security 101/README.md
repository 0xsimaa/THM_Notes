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

### Organizing Machines

Recommended OU structure for machines:

- **Workstations** → User computers and laptops
- **Servers** → Servers providing services
- **Domain Controllers** → Already in their own default OU

Move machines from the default **Computers** container into the appropriate OUs.

### Group Policy Objects (GPOs)

GPOs are collections of settings that can be applied to OUs.

**How GPOs work:**

1. Create a GPO under **Group Policy Objects**
2. Link the GPO to the desired OU(s)
3. GPOs apply to the linked OU **and all child OUs**

**Important tools:**

- **Group Policy Management** (gpmc.msc)
- Force update on a machine: gpupdate /force

**GPO Distribution:** GPOs are stored in the **SYSVOL** share (C:\Windows\SYSVOL\sysvol\) on Domain Controllers.

**Example GPOs from the room:**

- Restrict Control Panel access for non-IT users
- Auto-lock screens after 5 minutes of inactivity

### Authentication Protocols

#### Kerberos (Default)

1. User authenticates to the **KDC** (usually on the DC) and receives a **TGT** (Ticket Granting Ticket).
2. User uses the TGT to request a **TGS** (Ticket Granting Service) for a specific service.
3. User presents the TGS to the service to gain access.

- TGT is encrypted with the krbtgt account hash.
- TGS is encrypted with the service account’s hash.

#### NetNTLM (Legacy)

Challenge-response protocol kept for compatibility.

1. Client requests authentication.
2. Server sends a challenge.
3. Client responds using its NTLM hash.
4. Server forwards challenge + response to the DC for verification.

> The password (or hash) is never sent over the network.

### Trees, Forests, and Trusts

#### Trees

Multiple domains that share the same namespace Example: thm.local → uk.thm.local and us.thm.local

#### Forests

Multiple trees with **different namespaces** joined together Example: thm.local + mht.local

#### Trust Relationships

|Trust Type|Description|
|---|---|
|**One-way**|Domain A trusts Domain B → Users from B can access resources in A|
|**Two-way**|Mutual trust (default when domains are in the same tree/forest)|

**Important:** A trust relationship does **not** automatically grant access. You still need to explicitly authorize users.

**Enterprise Admins** have administrative rights over **all domains** in a forest.

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Cyber%20Security%20101/Pasted%20image%20(8).png)

---

### Windows Command Line (cmd.exe)

### Why Use the CLI?

- **Speed & efficiency** – Faster than clicking through GUIs
- **Lower resource usage** – Ideal for older hardware or cloud instances
- **Easy automation** – Simple to create scripts/batch files
- **Remote management** – Works well over SSH even on slow connections

### Basic System Information

| Command    | Description                                              |
| ---------- | -------------------------------------------------------- |
| ver        | Shows Windows version                                    |
| systeminfo | Detailed system information (OS, hardware, memory, etc.) |
| set        | Displays environment variables (including Path)          |
| help       | Lists available commands                                 |
| cls        | Clears the screen                                        |

> **Tip:** Pipe long output through more to view page-by-page:  
   "**driverquery | more**"

### Networking Commands

| Command                 | Description                                              |
| ----------------------- | -------------------------------------------------------- |
| ipconfig                | Basic network configuration (IP, subnet, gateway)        |
| ipconfig /all           | Detailed network info (MAC, DHCP, DNS servers)           |
| ping target             | Tests connectivity to a host                             |
| tracert target          | Traces the route to a target                             |
| nslookup domain         | Resolves domain name to IP address                       |
| nslookup domain 1.1.1.1 | Lookup using a specific DNS server                       |
| netstat                 | Shows active connections                                 |
| netstat -abon           | All connections + listening ports + process names + PIDs |

### Working with Directories

| Command          | Description                                            |
| ---------------- | ------------------------------------------------------ |
| cd               | Shows current directory                                |
| cd folder        | Change to a directory                                  |
| cd ..            | Go up one level                                        |
| dir              | List files and folders                                 |
| dir /a           | Include hidden and system files                        |
| dir /s           | List files in current directory and all subdirectories |
| tree             | Visual representation of directory structure           |
| mkdir foldername | Create a new directory                                 |
| rmdir foldername | Delete an empty directory                              |

### Working with Files

|Command|Description|
|---|---|
|type file.txt|Display contents of a text file|
|more file.txt|View long text files page-by-page|
|copy source destination|Copy a file|
|move source destination|Move or rename a file|
|del file or erase file|Delete a file|

**Wildcard example:**  
copy *.md C:\Markdown → Copies all Markdown files to the specified folder.

### Managing Processes

| Command                              | Description                |
| ------------------------------------ | -------------------------- |
| tasklist                             | List all running processes |
| tasklist /FI "imagename eq sshd.exe" | Filter processes by name   |
| taskkill /PID 1234                   | Terminate a process by PID |

### Additional Useful Commands

| Command      | Description                    |
| ------------ | ------------------------------ |
| chkdsk       | Checks disk for errors         |
| driverquery  | Lists installed drivers        |
| sfc /scannow | Scans and repairs system files |

### Helpful Tips

- Most commands support /? for help:  
    ipconfig /? or tasklist /?
- Use | more to paginate long output.
- The Path environment variable determines where Windows looks for executables.

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Cyber%20Security%20101/Pasted%20image%20(9).png)

---

### Windows PowerShell

### What is PowerShell?

PowerShell is a cross-platform task automation solution made up of a command-line shell, a scripting language, and a configuration management framework built on the .NET framework.

Unlike older text-based command-line tools (like cmd.exe or bash), PowerShell is **object-oriented**, which means it can handle complex data types and interact with system components more effectively. Initially exclusive to Windows, PowerShell Core (released in 2016) expanded support to macOS and Linux.

### The Power in PowerShell (Objects vs. Text)

Traditional command shells process and output data as plain text. When a cmdlet is run in PowerShell, it returns **objects**.

An object represents an item that encapsulates:

- **Properties:** Data or characteristics (e.g., a file's name, size, or extension)
- **Methods:** Actions or functionality (e.g., copying the file or stopping a process)

Because PowerShell passes these objects directly between commands, users can manipulate data dynamically without needing to write complex text-parsing scripts.

### Basic Syntax and Core Cmdlets

PowerShell commands are called **cmdlets** (pronounced command-lets). They follow a strict, easy-to-understand **Verb-Noun** naming convention, where the Verb describes the action and the Noun specifies the target.

| **Cmdlet**    | **Purpose**                                         | **Example / Details**                            |
| ------------- | --------------------------------------------------- | ------------------------------------------------ |
| `Get-Command` | Lists all available cmdlets, functions, and aliases | `Get-Command -CommandType "Function"`            |
| `Get-Help`    | Provides detailed manual pages, usage, and examples | `Get-Help Get-Date -examples`                    |
| `Get-Alias`   | Lists alternative shortcut names for cmdlets        | Shows that `dir` is an alias for `Get-ChildItem` |

### File and Directory Management

PowerShell uses a unified set of cmdlets to handle the creation and management of both files and directories, replacing the need for separate traditional commands.

|**Cmdlet**|**Action Performed**|**Traditional Equivalent**|
|---|---|---|
|`Get-ChildItem`|Lists files and directories in a specific path|`dir` / `ls`|
|`Set-Location`|Changes the current working directory|`cd`|
|`New-Item`|Creates a new file or directory|`mkdir` / `touch`|
|`Remove-Item`|Deletes files or directories|`rmdir` / `del`|
|`Copy-Item` / `Move-Item`|Copies or moves items to a destination|`copy` / `move`|
|`Get-Content`|Reads and displays the contents of a file|`type` / `cat`|

## The Pipeline and Filtering

Piping (`|`) in PowerShell passes structured objects rather than raw text, allowing properties and methods to flow seamlessly from one command to the next.

|**Cmdlet**|**What it Does**|**Use Case**|
|---|---|---|
|`Sort-Object`|Sorts piped objects based on specified properties|Sorting a directory listing by file `Length`|
|`Where-Object`|Filters objects based on specific conditions|Finding files where the `Extension` is `-eq ".txt"`|
|`Select-Object`|Selects specific properties or limits object output|Showing only the `Name` and `Length` of the top 5 files|
|`Select-String`|Searches for text or regex patterns within files|Finding specific error codes in a log file (like `grep`)|

_PowerShell Comparison Operators:_ `-eq` (equal to), `-ne` (not equal), `-gt` (greater than), `-ge` (greater or equal), `-lt` (less than), `-le` (less or equal), `-like` (matches a pattern).

## System Enumeration and Monitoring

PowerShell provides comprehensive cmdlets for gathering system details and monitoring dynamic aspects of a machine, making it a critical tool for system administrators and security professionals.

|**Cmdlet**|**Information Retrieved**|**Cyber Security Value**|
|---|---|---|
|`Get-ComputerInfo`|OS information, hardware specs, BIOS details|Baseline system profiling|
|`Get-LocalUser`|All local user accounts and account status|Hunting for rogue or unauthorized admin accounts|
|`Get-NetIPConfiguration`|Interfaces, IP addresses, DNS, and Gateways|Mapping local network configurations|
|`Get-Process`|Running processes, CPU, and memory usage|Spotting anomalous or resource-heavy malicious tasks|
|`Get-Service`|Status of services (Running, Stopped, Paused)|Identifying unauthorized persistence mechanisms|
|`Get-NetTCPConnection`|Current TCP connections and remote endpoints|Uncovering backdoors and established remote access|
|`Get-FileHash`|File hashes (e.g., SHA256)|Verifying file integrity and identifying malware|

## Scripting and Remote Execution

Scripting involves writing a sequence of commands to automate tasks. In cybersecurity:

- **Blue Teams** use PowerShell scripts to automate log analysis, detect anomalies, and extract indicators of compromise (IOCs).
- **Red Teams** use scripts to automate system enumeration, bypass defenses, and establish persistence.

**Invoke-Command:**

This cmdlet is essential for executing commands on remote systems. It allows users to run scripts or raw command blocks (`-ScriptBlock { ... }`) across multiple machines simultaneously, making it highly valuable for centralized administration and remote payload execution.

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Cyber%20Security%20101/Pasted%20image%20(10).png)

---

### Linux Shells and Scripting

### What is a Linux Shell?

While most users interact with an Operating System via a Graphical User Interface (GUI), interacting through a Command-Line Interface (CLI) using a **Shell** is far more efficient, resource-friendly, and powerful. The shell is a program that takes commands from the keyboard and passes them to the operating system to perform.

**The Restaurant Analogy:**

- **OS (Operating System) = The Kitchen:** Where the actual work and processing happen.
    
- **GUI (Graphical User Interface) = Ordering from a Menu:** A waiter serves you based on limited, predefined visual options. It is easy but restricts your control.
    
- **CLI (Command-Line Interface) = Cooking it Yourself:** Going into the kitchen (the OS) and preparing the dish exactly how you want it. The shell provides the "recipes" (commands) giving you complete power and control over the task.
    

## Basic Shell Commands

Before scripting, you must understand fundamental Linux commands used to navigate and manipulate the system within the shell:

| **Command** | **Purpose**                                                     | **Example Usage**         |
| ----------- | --------------------------------------------------------------- | ------------------------- |
| `pwd`       | Print Working Directory (displays your current folder location) | `pwd` -> `/home/user`     |
| `cd`        | Change Directory (moves you to a specified folder)              | `cd Desktop`              |
| `ls`        | List (shows all files and folders in the current directory)     | `ls`                      |
| `cat`       | Concatenate (reads and displays the entire contents of a file)  | `cat filename.txt`        |
| `grep`      | Search (finds a specific word or string pattern inside a file)  | `grep THM dictionary.txt` |

## Exploring Linux Shells

Different Linux distributions come with different shells installed. You can interact with your system to find out which ones are available and switch between them:

- **Check current shell:** `echo $SHELL`
    
- **List available installed shells:** `cat /etc/shells`
    
- **Permanently change default shell:** `chsh -s /usr/bin/zsh` (replaces your default shell with Zsh)
    

### Major Linux Shells Comparison

| **Feature**             | **Bash (Bourne Again Shell)**                             | **Fish (Friendly Interactive Shell)**                         | **Zsh (Z Shell)**                                                     |
| ----------------------- | --------------------------------------------------------- | ------------------------------------------------------------- | --------------------------------------------------------------------- |
| **Default Usage**       | The default shell in most Linux distributions.            | Rarely the default; heavily focuses on beginner-friendliness. | Modern shell, increasingly popular (default on modern macOS).         |
| **Scripting**           | Widely compatible with extensive documentation.           | Limited scripting features compared to Bash/Zsh.              | Excellent scripting, combining Bash capabilities with extra features. |
| **Tab Completion**      | Basic tab completion (auto-completes file/command names). | Advanced, giving suggestions based on your command history.   | Highly extensible via third-party plugins.                            |
| **Customization**       | Basic level of customization.                             | Good customization via interactive web-based tools.           | Advanced customization (e.g., Oh-My-Zsh framework).                   |
| **Syntax Highlighting** | Not available built-in.                                   | Built-in out of the box (colors commands to spot errors).     | Available by installing external plugins.                             |

## Shell Scripting Fundamentals

A **shell script** is a plain text file containing a sequence of commands. Instead of typing repetitive commands one by one, you can automate tasks by executing the script once.

### Setting Up a Script

1. **Create the file:** Use a text editor to create a `.sh` file (e.g., `nano script.sh`).
    
2. **Add the Shebang:** The first line must be `#!/bin/bash`. This tells the OS which interpreter to use to run the script.
    
3. **Grant Execution Permissions:** Make the script runnable using `chmod +x script.sh`.
    
4. **Execute the Script:** Run it from the current directory using `./script.sh` (the `./` tells the system to look in the exact current folder, bypassing the global PATH variables).
    

### Core Scripting Components

|**Component**|**Description**|**Example Syntax**|
|---|---|---|
|**Variables**|Stores data (like names, paths, or URLs) so you can reuse them without re-typing.|`read name` (takes user input)<br><br>  <br><br>`echo "Welcome, $name"`|
|**Loops**|Repeats a specific block of code multiple times, iterating through lists or ranges automatically.|`for i in {1..10}; do echo $i; done`|
|**Conditional Statements**|Executes specific code _only_ if a certain condition is met (`if`, `elif`, `else`).|`if [ "$name" = "John" ]; then echo "Access Granted"; fi`|
|**Comments**|Notes added to explain what the code does. Ignored by the computer. Vital for readability.|`# This checks if the user is admin`|

### Practical Script Example: The Locker Authenticator

By combining these components, we can build functional automation. Here is a script combining variables, a loop, and conditional statements to authenticate a user:

```Bash
#!/bin/bash
# This script authenticates a user before opening a locker

username=""
companyname=""
pin=""

# Loop to ask 3 different questions sequentially
for i in {1..3}; do
        if [ "$i" -eq 1 ]; then
                echo "Enter your Username:"
                read username
        elif [ "$i" -eq 2 ]; then
                echo "Enter your Company name:"
                read companyname
        else
                echo "Enter your PIN:"
                read pin
        fi
done

# Conditional statement verifying all inputs match the secret credentials
if [ "$username" = "John" ] && [ "$companyname" = "Tryhackme" ] && [ "$pin" = "7385" ]; then
        echo "Authentication Successful. You can now access your locker, John."
else
        echo "Authentication Denied!!"
fi
```

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Cyber%20Security%20101/pasted%20file(11).png)

---

### Networking Concepts

### What is the OSI Model?

The OSI (Open Systems Interconnection) model is a conceptual framework developed by the ISO that describes how computer network communications should occur. It consists of seven layers that help explain and standardise network interactions.

**Mnemonic to remember (Bottom to Top):** Please Do Not Throw Spinach Pizza Away (Physical, Data Link, Network, Transport, Session, Presentation, Application).

### The 7 Layers of the OSI Model

| **Layer Name**            | **Main Function**                                                            | **Example Protocols & Standards**            |
| ------------------------- | ---------------------------------------------------------------------------- | -------------------------------------------- |
| **Layer 7: Application**  | Provides network services directly to end-user applications.                 | HTTP, FTP, DNS, POP3, SMTP                   |
| **Layer 6: Presentation** | Handles data encoding, compression, and encryption.                          | ASCII, Unicode, MIME, JPEG, PNG              |
| **Layer 5: Session**      | Establishes, maintains, and synchronizes communication sessions.             | NFS, RPC                                     |
| **Layer 4: Transport**    | Enables end-to-end communication and data segmentation.                      | TCP, UDP                                     |
| **Layer 3: Network**      | Handles logical addressing and routing between different networks.           | IP, ICMP, IPSec, VPNs                        |
| **Layer 2: Data Link**    | Enables data transfer between nodes on the same network using MAC addresses. | Ethernet (802.3), WiFi (802.11)              |
| **Layer 1: Physical**     | Deals with the physical connection and transmission of binary digits.        | Electrical cables, Optical fiber, WiFi radio |

### The TCP/IP Model

Developed in the 1970s by the Department of Defense (DoD), this is a practical, implemented networking model designed to adapt and function even if parts of the network go offline.

It groups the OSI model into 4 (or 5) layers:

- **Application Layer:** Combines OSI Layers 5, 6, and 7.
    
- **Transport Layer:** Maps directly to OSI Layer 4.
    
- **Internet Layer:** Maps to OSI Layer 3 (Network Layer).
    
- **Link Layer:** Maps to OSI Layer 2 (Data Link).
    
- _(Optional)_ **Physical Layer:** Sometimes separated from the Link Layer as Layer 1.

### IP Addresses & Routing

An IP Address is a unique identifier required for a host to communicate on a network, acting similarly to a home postal address.

- **IPv4:** Consists of 32 bits divided into four octets (e.g., `192.168.66.89`).
    
- **Network & Broadcast Addresses:** The lowest address (e.g., `.0`) is reserved for the network, and the highest (e.g., `.255`) is reserved for broadcasting to all hosts.
    
- **Subnet Masks:** A mask like `255.255.255.0` (or `/24`) indicates that the first 24 bits are the network address, and the remaining bits are for assigning individual hosts.
    

### Public vs. Private IP Addresses

Private IP addresses are used for internal local networks and cannot be reached directly from the Internet. They require a router with NAT (Network Address Translation) to communicate externally.

**The RFC 1918 private IP ranges are:**

- `10.0.0.0` to `10.255.255.255`
    
- `172.16.0.0` to `172.31.255.255`
    
- `192.168.0.0` to `192.168.255.255`
    

### Transport Protocols: TCP vs. UDP

To reach specific applications or processes on a host, transport protocols use Port Numbers (ranging from 1 to 65535).

| **Feature**          | **TCP (Transmission Control Protocol)**                      | **UDP (User Datagram Protocol)**                           |
| -------------------- | ------------------------------------------------------------ | ---------------------------------------------------------- |
| **Connection Style** | Connection-oriented (Requires a 3-way handshake)             | Connectionless (Sends data without establishing a session) |
| **Reliability**      | High (Guarantees delivery, orders packets, error correction) | Low (No delivery confirmation, "fire and forget")          |
| **Speed**            | Slower (Due to overhead and acknowledgments)                 | Faster (No overhead, no waiting for confirmations)         |
| **Use Cases**        | Web browsing (HTTP/S), Email, SSH, File Transfer             | Video streaming, DNS queries, Online gaming                |

### The TCP 3-Way Handshake

1. **SYN:** Client initiates connection with a Synchronize packet.
    
2. **SYN-ACK:** Server responds with a Synchronize-Acknowledgment packet.
    
3. **ACK:** Client sends a final Acknowledgment packet, establishing the connection.

### Encapsulation

Encapsulation is the process where each layer adds its own header (and sometimes a trailer) to the data before passing it down to the next layer.

1. **Application Data:** User creates data (e.g., an email).
    
2. **Segment / Datagram:** Transport layer adds a TCP/UDP header.
    
3. **Packet:** Network layer adds an IP header (Source/Destination IPs).
    
4. **Frame:** Data Link layer adds a MAC header and trailer.
    

_(Note: The process is reversed, known as decapsulation, when the data reaches the destination.)_

### Command Line Tools

- **Check IP Configuration:**
    
    - Windows: `ipconfig`
        
    - Linux/UNIX: `ifconfig` or `ip address show` (`ip a s`)
        
- **TELNET:** A protocol/tool used to connect to and communicate with remote systems over TCP ports.
    
    - Connect to an Echo Server: `telnet [IP] 7`
        
    - Connect to a Daytime Server: `telnet [IP] 13`
        
    - Connect to a Web Server: `telnet [IP] 80` (Requires manual HTTP requests like `GET / HTTP/1.1`)

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Cyber%20Security%20101/pasted%20file12.png)

---

