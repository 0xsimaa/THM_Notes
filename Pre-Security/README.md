## Introduction to Cyber Security

### **Gobuster**

A directory and page enumeration tool that takes a wordlist of potential file or directory names and attempts to access them on a target website. If a page or path exists, Gobuster reports it back to you.

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%2020260206160633.png)
---

### **Security Operations Center (SOC)**

Security Operations Center (SOC): A dedicated team of IT security professionals responsible for **monitoring**, **preventing**, **detecting**, **investigating**, and **responding** to threats across a company's network and systems.

> If a patch for a known vulnerability is unavailable, organizations must implement alternative compensating controls to protect the system and reduce the risk of exploitation.

---

### **Threat Intelligence**

Threat Intelligence: The process of collecting and analyzing information about actual and potential adversaries to better understand and anticipate threats.

---

### **Digital Forensics**

Digital Forensics: The application of scientific methods to investigate cybercrimes and establish facts from digital evidence.

Key areas of focus include:

- **File System Analysis**: Capturing disk images for offline examination.
- **Memory Forensics**: Taking snapshots of system RAM to uncover volatile data.
- **Network Logs**: Reviewing captured network traffic for suspicious activity.
- **System Logs**: Examining OS and application logs — often the most critical evidence source.

---

### **Incident Response**

Incident Response: A structured methodology for handling cybersecurity incidents in an organized and effective manner.

The four core phases are:

1. **Preparation**: Establishing policies, tools, and teams before an incident occurs.
2. **Detection and Analysis**: Identifying and investigating potential incidents.
3. **Containment, Eradication, and Recovery**: Limiting damage, removing the threat, and restoring normal operations.
4. **Post-Incident Activity**: Reviewing what happened and improving defenses going forward.

---

### **Malware Analysis**

Malware Analysis: The process of studying malicious software to understand its behavior, origin, and impact.

Common types of malware include:

- **Virus**: Self-replicating code that attaches to legitimate programs.
- **Trojan Horse**: Malware disguised as legitimate software.
- **Ransomware**: Encrypts victim data and demands payment for decryption.

Primary analysis techniques:

- **Static Analysis**: Examining the malware without executing it (e.g., reading code, checking file hashes).
- **Dynamic Analysis**: Running the malware in a controlled environment (sandbox) to observe its behavior.

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%2020260206161040.png)

---

### Careers in Cyber Security

- **SOC Analyst**: Monitors security alerts and responds to incidents in real time to protect an organization's infrastructure.

- **Penetration Tester (Ethical Hacker)**: Simulates attacks on systems and networks to find vulnerabilities before malicious actors do.

- **Digital Forensics Investigator**: Collects and analyzes digital evidence from devices and networks to support cybercrime investigations.

- **Malware Analyst**: Examines malicious software to understand how it works, what damage it causes, and how to defend against it.

- **Threat Intelligence Analyst**: Researches and tracks threat actors, attack patterns, and emerging risks to help organizations stay ahead of threats.

- **Security Engineer**: Designs and builds secure systems, networks, and tools to protect organizational infrastructure.

- **Incident Responder**: Leads the containment and recovery process when a security breach or cyberattack occurs.

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%2020260206182127.png)

---

### Network Fundamentals

#### What is Networking?

A foundational overview of core networking concepts:

- **Network**: A collection of interconnected devices that share resources and communicate.

    - **Public Network**: Accessible to anyone (e.g., the Internet).
    - **Private Network**: Restricted to authorized users (e.g., a corporate LAN).

- **IP Address**: A unique logical identifier assigned to each device on a network.

    - **IPv4**: 32-bit address format (e.g., `192.168.1.1`).
    - **IPv6**: 128-bit address format designed to replace IPv4 due to address exhaustion.

- **MAC Address**: A hardware-level identifier permanently assigned to a network interface card (NIC).

- **MAC Spoofing**: Changing a device's MAC address to impersonate another device or bypass MAC-based filtering.

- **Ping**: A utility used to test connectivity between two devices by sending ICMP echo requests.

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%2020260206155940.png)

bash

```bash
ping 10.10.10.10
```

---

### Intro to LAN

#### LAN (Local Area Network)

A network covering a small geographic area, such as a home, office, or building.

---

### Network Topologies

- **Star Topology**: All devices connect to a central switch or hub. Easy to manage; single point of failure at the center.
- **Bus Topology**: All devices share a single communication line. Simple but prone to collisions and difficult to troubleshoot.
- **Ring Topology**: Devices are connected in a circular loop. Data travels in one direction around the ring.

---

### Key Network Devices

- **Switch**: Connects devices within a LAN and forwards data only to the intended recipient using MAC addresses.
- **Router**: Connects different networks together and directs traffic between them using IP addresses.

---

### Subnetting

Subnetting: The process of dividing a larger network into smaller, more manageable sub-networks (subnets).

Used for:

- **Security**: Isolating sensitive systems from the rest of the network.
- **Management**: Reducing broadcast traffic and improving network organization.

---

### ARP (Address Resolution Protocol)

ARP: A protocol used to map a known IP address to its corresponding MAC address on a local network. (Not for global Network)

**How ARP works:**

1. A device broadcasts an **ARP Request** asking: _"Who owns this IP address? What is your MAC address?"_
2. The device that owns that IP responds with an **ARP Reply**, providing its MAC address.
3. The requesting device stores this IP-to-MAC mapping in its **ARP Cache** for future use, avoiding repeated broadcasts.

ARP signal types:

- **ARP Request**: Broadcast message sent to all devices on the network.
- **ARP Reply**: Unicast response sent back from the device that owns the IP.

---

### DHCP (Dynamic Host Configuration Protocol)

DHCP: A protocol that automatically assigns IP addresses and other network configuration settings to devices when they join a network.

IP addresses can be assigned either:

- **Manually (Static)**: Configured directly on the device.
- **Automatically (Dynamic)**: Assigned by a DHCP server.

**DHCP four-step handshake (DORA):**

1. **DHCP Discover**: The client broadcasts a request looking for a DHCP server.
2. **DHCP Offer**: The server responds with an available IP address offer.
3. **DHCP Request**: The client formally requests the offered IP address.
4. **DHCP ACK (Acknowledgement)**: The server confirms the assignment; the client can now use the IP.

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%2020260206210225.png)

---

### OSI Model (Open Systems Interconnection Model)

The **OSI Model** is a conceptual framework that standardizes how networked devices communicate. It defines how data is sent, received, and interpreted across networks so that devices from different vendors can interoperate.

#### Key Benefit

Devices with different hardware/software designs can still communicate reliably because everyone follows the same layered rules.

#### Structure

- 7 layers, numbered from **Layer 7** (top --> closest to user) to **Layer 1** (bottom --> physical hardware)
- Data flows **down** the stack when sending → **encapsulation** (headers added at each layer)
- Data flows **up** the stack when receiving → **decapsulation** (headers removed)

text

```
Layer 7 – Application
Layer 6 – Presentation
Layer 5 – Session
Layer 4 – Transport
Layer 3 – Network
Layer 2 – Data Link
Layer 1 – Physical
```

### Layer 1: Physical Layer

Handles the **raw transmission of bits** (1s and 0s) over the physical medium.

- Deals with: cables, connectors, voltages, signal timing, hubs, repeaters, NIC ports
- Example: Ethernet cables carrying electrical signals
- Pure hardware: no intelligence, just sending and receiving electrical/optical signals

### Layer 2: Data Link Layer

Responsible for **node-to-node delivery** on the same local network using **physical (MAC) addresses**.

- Takes packets from Layer 3 and adds the destination **MAC address**
- MAC addresses are burned into the NIC by the manufacturer (can be spoofed, but not permanently changed)
- Formats data into **frames** suitable for the physical medium
- Error detection (but not correction) usually happens here
- Devices: **switches**, bridges (work with MAC addresses)

### Layer 3: Network Layer

Handles **end-to-end delivery** across multiple networks using **logical (IP) addresses**.

- Main job: **routing** i.e. finding the best path for packets
- Uses **IP addresses** (e.g. 192.168.1.100)
- Routing decisions based on:
    - Shortest path (fewest hops)
    - Most reliable (least historical packet loss)
    - Fastest link (fiber > copper)
- Common routing protocols (just know names for now): **OSPF**, **RIP**
- Devices: **routers** → called **Layer 3 devices**

### Layer 4: Transport Layer

Provides **end-to-end communication** services between hosts.

Two main protocols:

#### TCP (Transmission Control Protocol) – Reliable, connection-oriented

- 3-way handshake to establish connection
- Guarantees delivery, correct order, error checking & retransmission
- Flow control (prevents overwhelming receiver)

|Advantages|Disadvantages|
|---|---|
|Guarantees data arrives complete|Slower due to overhead|
|Reassembles packets in order|Requires stable connection|
|Flow control|One lost packet delays entire stream|
|Used for: web browsing, email, file transfer|Connection reservation can bottleneck slow links|

#### UDP (User Datagram Protocol) – Fast, connectionless

- No handshake, no guarantees, fire-and-forget
- Much lower overhead

|Advantages|Disadvantages|
|---|---|
|Very fast|No delivery guarantee|
|No connection setup|Lost packets are gone|
|Flexible for developers|Poor experience on unstable networks|
|Used for: video streaming, DNS, gaming, VoIP|Not suitable when accuracy is critical|
### Layer 5: Session Layer

Manages **"dialogue"** (sessions) between applications.

- Establishes, maintains, and terminates sessions
- Handles reconnection & checkpoints (only resend data since last checkpoint)
- Keeps data within its specific session (no cross-session mixing)
- Examples: checkpointing in long file transfers, session recovery

### Layer 6: Presentation Layer

Acts as a **translator** and formatter so different systems can understand the data.

- Converts data formats (e.g. ASCII ↔ EBCDIC, JPEG compression)
- Handles encryption & decryption (**SSL/TLS**, HTTPS happens here)
- Data compression/decompression
- Ensures the receiving application sees data in a usable format

### Layer 7: Application Layer

The layer **closest to the user**, i.e. where applications access network services.

- Provides network services to end-user applications
- Protocols: **HTTP/HTTPS**, **FTP**, **SMTP**, **DNS**, **POP3/IMAP**, **Telnet**, etc.
- User-facing software lives here: browsers, email clients, FileZilla, etc.
- DNS resolves domain names → IP addresses

### OSI Dungeon Escape:

(This is the dungeon escape room of THM OSI Model)

![image](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image.png)

**"Room Completed"**

![image](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%20(2).png)

---

### Packets vs Frames

- #### **Packet**
    - Operates at **Layer 3 (Network Layer)**
    - Contains: IP header + actual data (payload)
    - Uses **IP addresses** (source & destination)
- ##### **Frame**
    - Operates at **Layer 2 (Data Link Layer)**
    - Wraps the entire packet inside it
    - Adds **MAC addresses** (source & destination) for local network delivery

- **Analogy**: Packet = the letter itself, Frame = the envelope that gets it across one local hop

### Why We Use Small Packets

- Sending huge files in one piece → causes major congestion, long delays, and easy failure
- Instead: break data into small packets → each travels independently (different paths possible) → much lower risk of blocking the whole network → receiver reassembles them in correct order
- Everyday example: A single photo or video is chopped into dozens/hundreds of packets

### Encapsulation:

1. Application creates the data
2. Layer 3 adds IP header → becomes a **Packet**
3. Layer 2 takes the packet, adds its own header & trailer (MAC addresses, error checking) → becomes a **Frame**
4. Frame is sent over the physical medium (cable, Wi-Fi, etc.)
5. At next device: Frame is opened → Packet is extracted → and so on

### Key IP Packet Headers (with purpose)

- **Time to Live (TTL)** Starts at 64 or 128 → decreases by 1 per router If it reaches 0 → packet is dropped (prevents infinite loops)
- **Checksum** Quick math check on the header (sometimes whole packet) If changed/corrupted → packet is discarded
- **Source IP Address** Sender’s IP → allows replies to come back
- **Destination IP Address** Final target → routers use this to forward packet

---

### TCP/IP Model:

- **TCP/IP Model – 4 Layers**
    - Application → (HTTP, FTP, SMTP, etc.)
    - Transport → (TCP or UDP – reliability decided here)
    - Internet → (IP – routing & addressing)
    - Network Interface → (Ethernet, Wi-Fi, physical hardware + MAC)

- **TCP is Connection-Oriented & Reliable**
    - Must perform handshake before sending any data
    - Guarantees delivery, correct order, no duplication, and error checking

