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

