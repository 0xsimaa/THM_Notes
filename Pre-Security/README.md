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

### TCP/IP

- **TCP/IP Model – 4 Layers**
    
	- Application → HTTP, HTTPS, FTP, SMTP, DNS, etc.
    - Transport → TCP (reliable) or UDP (fast/unreliable) – reliability decided here
    - Internet → IP (IPv4/IPv6) – handles routing and logical addressing
    - Network Interface → Ethernet, Wi-Fi, physical hardware + MAC addresses

- **TCP is Connection-Oriented & Reliable**

	- Requires a connection to be established before any data is sent
    - Guarantees: delivery, correct order, no duplicates, and error detection

- **Three-Way Handshake (Connection Setup)**

	- Client → Server: SYN (sends random Initial Sequence Number – ISN)
    - Server → Client: SYN + ACK (sends own ISN + acknowledges client’s ISN)
    - Client → Server: ACK (acknowledges server’s ISN) → connection is now fully open

- **Key TCP Header Fields**

	- Source Port → random high-number (ephemeral) port chosen by the sender
    - Destination Port → well-known/fixed port of the service (e.g. 80=HTTP, 443=HTTPS, 22=SSH)
    - Sequence Number → tracks the position of each byte in the data stream
    - Acknowledgement Number → tells sender “I’ve received everything up to this number”
    - Checksum → mathematical value used to detect corrupted or damaged data
    - Flags → control bits (SYN, ACK, FIN, RST, PSH, URG…) that control connection behavior

- **Advantages of TCP**

	- Guarantees data arrives complete, in order, and without duplication
    - Built-in flow control prevents fast sender from overwhelming slow receiver
    - Automatically retransmits any lost or corrupted packets

- **Disadvantages of TCP**

	- Slower than UDP (due to extra headers, acknowledgements, and retransmissions)
    - Requires a stable connection – poor/unstable networks cause big delays
    - Uses more CPU and memory (tracks connection state, buffers, etc.)

- **Closing a TCP Connection**

	- Normally uses FIN packets in a polite 4-step (or combined) close sequence
    - FIN → “I have no more data to send” (Connection end)
    - RST → abrupt/harsh reset (used for errors, crashes, rejected connections, etc.)

- **Sequence & Acknowledgement Basics**

	- Both sides begin with a random Initial Sequence Number (ISN) for security and ordering
    - Every byte of data is assigned a sequence number
    - Receiver sends ACK to confirm receipt → data is reassembled in correct order even if packets arrive out of sequence

---

### The User Datagram Protocol (UDP)

The **User Datagram Protocol (UDP)** is a stateless transport-layer protocol used to send data between devices. Unlike TCP, UDP does **not** require a constant connection, a three-way handshake, or any synchronization between sender and receiver.

> UDP is preferred in scenarios where applications can tolerate packet loss (e.g., video streaming, voice chat, online gaming) or when a stable connection cannot be guaranteed.

### Comparison: TCP vs UDP (Quick Reference)

| Feature         | TCP                          | UDP                          |
| --------------- | ---------------------------- | ---------------------------- |
| Connection type | Connection-oriented          | Connectionless / Stateless   |
| Handshake       | Three-way handshake required | No handshake                 |
| Reliability     | Guarantees delivery & order  | No guarantee of delivery     |
| Speed           | Slower (due to overhead)     | Much faster                  |
| Use cases       | Web, email, file transfer    | Streaming, VoIP, DNS, gaming |

### Advantages and Disadvantages of UDP

| Advantages of UDP                                                         | Disadvantages of UDP                                      |
| ------------------------------------------------------------------------- | --------------------------------------------------------- |
| Much faster than TCP                                                      | No guarantee that data is received                        |
| Application controls packet sending rate (highly flexible for developers) | Unstable connections result in poor user experience       |
| Does not reserve a continuous connection                                  | No data integrity checks or retransmission                |
| Simpler packet structure (fewer headers)                                  | No safeguards like TCP (no acknowledgements, no ordering) |

### UDP Packet Headers

UDP packets are significantly simpler than TCP packets. The following headers are common to both protocols (and always present in UDP):

| Header                  | Description                                                                                          |
| ----------------------- | ---------------------------------------------------------------------------------------------------- |
| **Time to Live (TTL)**  | Sets an expiry timer for the packet so it does not loop endlessly in the network                     |
| **Source Address**      | IP address of the sending device                                                                     |
| **Destination Address** | IP address of the receiving device                                                                   |
| **Source Port**         | Randomly chosen port (0–65535) on the sender’s device                                                |
| **Destination Port**    | Fixed port on the receiver where the service/application is listening (e.g., port 80 for web server) |
| **Data**                | Actual payload (bytes of the file or message being transmitted)                                      |

### Connection Process (UDP)

- UDP is **stateless**, i.e. no connection is ever established.
- No three-way handshake occurs.
- No acknowledgements are sent back to the sender.
- The sender simply fires packets toward the destination port with zero regard for whether they arrive or not.
- Responsibility for handling lost packets, ordering, or retransmission is left entirely to the application layer.

---

### Network Ports

**Ports** act as the entry and exit points for data on a device. Just like a harbour has specific docks for different types of ships, networking devices use ports to enforce strict rules about which applications can send or receive data.

> **Harbour Analogy** A cruise liner cannot dock at a fishing vessel’s port and vice versa. Similarly, data must use the correct port number to reach the intended application or service.

- Ports are **numerical values** ranging from **0 to 65,535**.
- When a connection is established (as explained in the OSI Model room), all data sent or received travels through these ports.

Because there are 65,536 possible ports, standards were created so applications know exactly where to send/receive data. This ensures compatibility across all software (e.g., every web browser expects web traffic on the same port).

### Well-Known / Common Ports (0 – 1,024)

These are the **standard ports** reserved for widely used protocols. Applications expect these defaults unless otherwise specified.

|Protocol|Port Number|Description|
|---|---|---|
|**File Transfer Protocol (FTP)**|21|Used for uploading/downloading files in a client-server model|
|**Secure Shell (SSH)**|22|Secure text-based remote login and system management|
|**HyperText Transfer Protocol (HTTP)**|80|Powers the World Wide Web – used by browsers to load websites|
|**HyperText Transfer Protocol Secure (HTTPS)**|443|Same as HTTP but encrypted (secure web browsing)|
|**Server Message Block (SMB)**|445|File and printer sharing (more advanced than basic FTP)|
|**Remote Desktop Protocol (RDP)**|3389|Graphical remote desktop access (visual interface, unlike text-based SSH)|

> **Reference** For a complete list of all assigned ports, consult the **Service Name and Transport Protocol Port Number Registry** (IANA).

### Important Note on Non-Standard Ports

- These port numbers are **only standards** — not strict rules.
- You **can** run services on different ports (e.g., a web server on **8080** instead of **80**).
- When using a non-standard port, you must explicitly tell the application by adding a colon and the port number (e.g., http://example.com:8080).
- Most applications assume the standard port is being used unless you specify otherwise.

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%20(3).png)

---

### Port Forwarding

**Port forwarding** is the process of configuring a router to forward incoming traffic from the Internet to a specific device and port inside the private (local) network.

Without port forwarding, any service (e.g., a web server, game server, or remote desktop) is **only accessible from devices on the same local network** (intranet). It remains invisible to the outside world.

### Example: Local Network (Intranet)

Consider the following private network:

- A web server runs on internal IP: 192.168.1.10:80
- Only the other computers inside the same network can reach the website.
- Devices outside this network (on the Internet) have no way to access it.

### Making the Service Public

To allow users from the Internet to reach the web server, the network administrator must set up **port forwarding** on the router:

- The router’s **public IP** (e.g., 82.62.51.70) is used by external devices.
- The router is told: “Any traffic arriving on port 80 from the Internet should be forwarded to internal IP 192.168.1.10 on port 80.”
- Result: Anyone on the Internet can now access the server using the public IP (e.g., http://82.62.51.70).

### Port Forwarding vs Firewall (Important Distinction)

|Concept|Role|
|---|---|
|**Port Forwarding**|**Opens** a specific port on the router and directs traffic to the correct internal device and port|
|**Firewall**|**Decides** whether the traffic is allowed or blocked (even if the port is forwarded)|

> Port forwarding only creates the path. The firewall still acts as the security gatekeeper that can permit or deny the actual packets.

### Configuration Note

- Port forwarding rules are always configured on the **router** (not on the server itself).
- Common use cases: hosting websites, game servers, remote access (RDP/SSH), CCTV cameras, etc.

---

### Firewalls

A **firewall** is a network security device (or software) that acts as **border security** for a network. It inspects all incoming and outgoing traffic and decides whether to **permit** or **deny** it based on predefined rules.

Firewalls perform **packet inspection** to evaluate traffic using several key factors:

- Source of the traffic (which network or IP it came from)
- Destination of the traffic (where it is trying to go)
- Port number the traffic is using
- Protocol being used (TCP, UDP, etc.)

> Without a firewall, even if ports are forwarded, unwanted traffic can still reach your devices. Port forwarding **opens** the door — the firewall **guards** it.

### Firewall Types and Categories

Firewalls exist in many forms:

- Dedicated hardware appliances (used in large enterprise networks)
- Built into residential routers (your home router)
- Software solutions (e.g., **Snort**)

They can be categorised into 2 to 5 types depending on the classification system. The two **primary categories** are:

### Stateful vs Stateless Firewalls

|Firewall Type|Description|Key Characteristics|
|---|---|---|
|**Stateful**|Tracks the entire connection/context, not just individual packets.|- Dynamic decision-making - Remembers previous packets in a session - Blocks entire device if connection is malicious - Higher resource usage - More intelligent|
|**Stateless**|Uses a fixed set of rules to inspect each packet in isolation.|- Static rules only - Very low resource usage - Faster for high traffic (e.g., DDoS mitigation) - “Dumber” — only as good as the rules defined - Does not track connection state|

> **Example**: A stateful firewall might allow the first two steps of a TCP handshake but block the third if it looks suspicious. A stateless firewall would evaluate every packet independently.

(Firewall operates at 3rd & 4th layer of OSI Model)

---

### Virtual Private Networks (VPN)

A **Virtual Private Network (VPN)** creates a secure, encrypted **tunnel** between devices on separate networks over the Internet. Once connected, these devices behave as if they are on the **same private network**, even if they are thousands of miles apart.

### How a VPN Works – Example

Imagine three separate networks:

1. **Network #1** – Office #1
2. **Network #2** – Office #2
3. **Network #3** – Devices connected via VPN

The devices in Network #3 are still part of their original offices (Network #1 and #2), but they also form an isolated private network that **only** VPN-connected devices can communicate over.

> **Key Point** Without a VPN, devices can only talk directly if they are on the **same local network**. A VPN bridges distant networks securely.

### Benefits of Using a VPN

|Benefit|Description|
|---|---|
|**Geographical Connectivity**|Connects offices or networks in different locations so they can share servers, files, and resources as if they were in the same building|
|**Privacy**|Encrypts all traffic so it can only be read by the intended sender and receiver. Protects against sniffing, especially on public Wi-Fi|
|**Anonymity**|Hides your real IP and activity from your ISP and intermediaries. Useful for journalists, activists, and anyone in restricted environments|

> **Note on Anonymity** The level of anonymity depends on the VPN provider. A VPN that logs your activity is no better than not using one at all.

### Why TryHackMe Uses a VPN

TryHackMe connects you to vulnerable machines through their VPN so that:

- You can securely interact with the machines
- Your ISP does not see you attacking or accessing external systems (avoiding ToS violations)
- Vulnerable machines stay hidden from the public Internet

### Common VPN Technologies

| VPN Technology                               | Description                                                                                                                                                           |
| -------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **PPP** (Point-to-Point Protocol)            | Used for authentication and encryption. Requires matching private key + public certificate. Not routable by itself (needs another protocol to leave the network)      |
| **PPTP** (Point-to-Point Tunneling Protocol) | Allows PPP traffic to travel across the Internet. Very easy and quick to set up. Supported on almost all devices. **Weak encryption** compared to modern alternatives |
| **IPSec** (Internet Protocol Security)       | Encrypts data using the existing IP framework. Strong encryption and widely supported. More difficult to configure than PPTP                                          |

---

### Routers

A **router** is a dedicated networking device whose primary job is to **connect different networks** and forward data between them.

It operates at **Layer 3** of the OSI model and uses **routing** to create optimal paths for data to travel across networks.

### Key Functions of a Router

- Determines the best path for packets to reach their destination
- Configurable via a web interface or console (allows setting port forwarding, firewall rules, etc.)
- Routes traffic when multiple paths exist

### Routing Decision Factors

When multiple paths are available, routers choose the best one based on:

- Shortest path
- Most reliable path
- Fastest medium (e.g., fibre vs copper)

> **Routers vs Switches** Routers connect **different networks** together. Switches only connect **devices within the same network**.

### Switches

A **switch** is a dedicated networking device that connects multiple devices (typically 3–63) together using Ethernet cables. It forwards data efficiently within a single network.

Switches can operate at **Layer 2** or **Layer 3** of the OSI model (but never both at the same time on the same device).

### Layer 2 Switch

- Forwards **frames** using **MAC addresses**
- Works only within the same network
- Encapsulates original IP packets inside frames
- Fast and simple — no routing capability

### Layer 3 Switch

- Combines Layer 2 functionality with **some** router capabilities
- Forwards frames using MAC addresses **and** routes packets using **IP addresses**
- Can handle traffic between different subnets/VLANs

|Feature|Layer 2 Switch|Layer 3 Switch|
|---|---|---|
|OSI Layer|Layer 2 only|Layer 2 + Layer 3|
|Addressing|MAC addresses only|MAC addresses + IP addresses|
|Routing Capability|None|Can route between subnets/VLANs|
|Use Case|Connecting devices in one network|Larger networks needing inter-VLAN routing|

### Virtual Local Area Networks (VLANs)

**VLANs** allow a single physical switch to logically divide devices into separate virtual networks.

- Devices in different VLANs can share the same Internet connection
- But they **cannot** communicate with each other unless routing is explicitly allowed
- Provides strong **security** through network segmentation

**Example** On the same physical switch:

- Sales Department (VLAN 10)
- Accounting Department (VLAN 20) Both departments can access the Internet, but **cannot** talk to each other.

#### **Room Complete:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%20(4).png)

---

### Domain Name System (DNS)

The **Domain Name System (DNS)** translates human-readable domain names (e.g., tryhackme.com) into machine-readable **IP addresses** (e.g., 104.26.10.229).

Every device on the Internet has a unique IP address, but remembering long strings of numbers is impractical. DNS acts as the Internet’s phonebook, allowing us to use friendly names instead.

> **Analogy** Just as every house has a unique postal address, every server has a unique IP address. DNS lets us use the “house name” instead of the full address.

### Domain Name Structure

A domain name is read from **right to left** and consists of three main parts:

| Part                       | Position             | Example (admin.tryhackme.com) | Description                                                                                                                                                     |
| -------------------------- | -------------------- | ----------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Top-Level Domain (TLD)** | Rightmost            | .com                          | Highest level. Two types: • **gTLD** (Generic) – .com, .org, .net, .online, etc. • **ccTLD** (Country Code) – .ca, .uk, .pk, etc.                               |
| **Second-Level Domain**    | Left of TLD          | tryhackme                     | The main name you register. Limited to 63 characters (a-z, 0-9, hyphens only; cannot start/end with hyphen or have consecutive hyphens)                         |
| **Subdomain**              | Left of Second-Level | admin                         | Optional. Can be nested (e.g., jupiter.servers.tryhackme.com). Same 63-character rules. Total domain length ≤ 253 characters. No limit on number of subdomains. |

### Common DNS Record Types

DNS stores different types of records for various purposes. The most frequently used ones are:

|Record Type|Purpose|Example Value|Notes|
|---|---|---|---|
|**A**|Maps a domain to an IPv4 address|104.26.10.229|Most common for websites|
|**AAAA**|Maps a domain to an IPv6 address|2606:4700:20::681a:be5|IPv6 equivalent of A record|
|**CNAME**|Creates an alias (points to another domain)|store.tryhackme.com → shops.shopify.com|Requires a second lookup|
|**MX**|Specifies mail servers for the domain|alt1.aspmx.l.google.com (with priority)|Includes priority value for failover|
|**TXT**|Stores arbitrary text information|v=spf1 ip4:192.0.2.0/24 ~all|Used for SPF, DMARC, domain verification, etc.|

---

