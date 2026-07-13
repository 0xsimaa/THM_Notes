### Introduction to Cyber Security

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

### What Happens When You Make a DNS Request (Step-by-Step)

1. **Local Cache Check** Your computer first checks its own DNS cache. If the result is recent, it is used immediately.
2. **Recursive DNS Server** If not found locally, the request goes to your **Recursive DNS Server** (usually provided by your ISP, or you can use public ones like Google/Cloudflare). This server also has a cache. If it has the answer, it returns it. Otherwise, it begins the full lookup.
3. **Root DNS Servers** The recursive server queries one of the Internet’s **root servers**. The root server redirects the query to the correct **Top-Level Domain (TLD) server** (e.g., the .com server).
4. **TLD Server** The TLD server tells the recursive server which **Authoritative Name Server** (nameserver) is responsible for the domain (e.g., kip.ns.cloudflare.com and uma.ns.cloudflare.com for TryHackMe).
5. **Authoritative DNS Server** The authoritative server holds the actual DNS records for the domain. It returns the requested record (A, MX, TXT, etc.) to the recursive server. The recursive server caches the result (using the record’s **TTL** – Time To Live value in seconds) and sends it back to your computer.

> **Why caching matters** Caching dramatically reduces the number of DNS queries and speeds up future requests.

**Room Complete:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%20(5).png)

---

### HTTP (HyperText Transfer Protocol)

**HTTP** is the protocol used to communicate with web servers and transfer webpage data (HTML, images, videos, etc.). It was developed by Tim Berners-Lee and his team between 1989–1991.

### HTTPS (HyperText Transfer Protocol Secure)

**HTTPS** is the encrypted and secure version of HTTP. It protects data from being read in transit and verifies that you are communicating with the legitimate server (not an impersonator).

### Uniform Resource Locator (URL)

A **URL** is an address that tells your browser exactly how and where to retrieve a resource on the Internet.

### URL Components

| Component        | Description                                            | Example             |
| ---------------- | ------------------------------------------------------ | ------------------- |
| **Scheme**       | Protocol to use                                        | https://            |
| **User**         | Optional username and password for authentication      | user:pass@          |
| **Host**         | Domain name or IP address of the server                | tryhackme.com       |
| **Port**         | Port number (default: 80 for HTTP, 443 for HTTPS)      | :8080               |
| **Path**         | Location of the specific file or page                  | /blog/post-1        |
| **Query String** | Extra parameters sent to the server                    | ?id=1&category=news |
| **Fragment**     | Reference to a specific part of the page (client-side) | #section-2          |

### Making an HTTP Request

A simple request can be as short as one line, but real requests include **headers** with extra information.

### Example Request

http

```
GET / HTTP/1.1
Host: tryhackme.com
User-Agent: Mozilla/5.0 Firefox/87.0
Referer: https://tryhackme.com/
```

**Breakdown:**

- Line 1: GET method + path (/) + HTTP version
- Host: Target domain
- User-Agent: Browser and version
- Referer: Where the request came from
- Blank line at the end signals the request is complete

### HTTP Response

After receiving a request, the server sends back a response.

### Example Response

http

```
HTTP/1.1 200 OK
Server: nginx/1.15.8
Date: Fri, 09 Apr 2021 13:34:03 GMT
Content-Type: text/html
Content-Length: 98

<html>
<head>
    <title>TryHackMe</title>
</head>
<body>
    Welcome To TryHackMe.com
</body>
</html>
```

**Breakdown:**

- Line 1: HTTP version + **Status Code** (200 OK = success)
- Server: Web server software and version
- Date: Current date/time on the server
- Content-Type: Type of data being sent (HTML, image, PDF, etc.)
- Content-Length: Size of the response body (in bytes)
- Blank line separates headers from the actual content

---

### HTTP Methods

HTTP methods tell the web server what action the client wants to perform.

| Method     | Description                                     | Common Use Case               |
| ---------- | ----------------------------------------------- | ----------------------------- |
| **GET**    | Retrieve data from the server                   | Loading a webpage             |
| **POST**   | Submit data to the server (creates new records) | Submitting forms, login, etc. |
| **PUT**    | Update existing data on the server              | Editing a profile or post     |
| **DELETE** | Delete data/records from the server             | Removing a user or blog post  |

> **Note** 
> The vast majority of your daily web activity uses only **GET** and **POST**.

### HTTP Status Codes

Every HTTP response starts with a **status code** that tells the client the result of the request.

### Status Code Ranges

| Range       | Category      | Meaning                                                                |
| ----------- | ------------- | ---------------------------------------------------------------------- |
| **100–199** | Informational | First part of request received; continue sending the rest (rare today) |
| **200–299** | Success       | Request completed successfully                                         |
| **300–399** | Redirection   | Client should go to a different URL                                    |
| **400–499** | Client Error  | Something wrong with the client’s request                              |
| **500–599** | Server Error  | Problem on the server side                                             |
### **Common HTTP Status Codes**

| Code    | Name                  | Meaning                                        |
| ------- | --------------------- | ---------------------------------------------- |
| **200** | OK                    | Request successful                             |
| **201** | Created               | New resource successfully created              |
| **301** | Moved Permanently     | Resource permanently moved to new URL          |
| **302** | Found                 | Temporary redirect                             |
| **400** | Bad Request           | Request is malformed or missing required data  |
| **401** | Unauthorized          | Authentication required (login needed)         |
| **403** | Forbidden             | You do not have permission (even if logged in) |
| **404** | Not Found             | Page or resource does not exist                |
| **405** | Method Not Allowed    | Wrong HTTP method used for this resource       |
| **500** | Internal Server Error | Server encountered an unexpected error         |
| **503** | Service Unavailable   | Server overloaded or down for maintenance      |

> **Tip for Visual Learners** 
> Check out [http.cat](https://http.cat) for fun visual explanations of every status code.

---

### HTTP Headers

Headers are additional metadata sent with HTTP requests and responses. They are not strictly required, but without them most websites will not function correctly.

### Common Request Headers (Client → Server)

| Header              | Description                                                                              |
| ------------------- | ---------------------------------------------------------------------------------------- |
| **Host**            | Tells the server which website to serve (important when one server hosts multiple sites) |
| **User-Agent**      | Browser name and version (helps the server format the page correctly)                    |
| **Content-Length**  | Size of the data being sent (used with POST/PUT)                                         |
| **Accept-Encoding** | Compression methods the browser supports                                                 |
| **Cookie**          | Previously saved cookie data sent back to the server                                     |

### Common Response Headers (Server → Client)

| Header               | Description                                                   |
| -------------------- | ------------------------------------------------------------- |
| **Set-Cookie**       | Instructs the browser to save a cookie                        |
| **Cache-Control**    | How long the browser should cache the response                |
| **Content-Type**     | Type of data being returned (HTML, CSS, JS, image, PDF, etc.) |
| **Content-Encoding** | Compression method used on the response                       |

### Cookies

Cookies are small pieces of data stored in your browser. They are created when the server sends a ***Set-Cookie*** header and are automatically sent back by the browser on every future request to the same domain.

Because HTTP is **stateless**, cookies allow the server to remember who you are, your preferences, or your login session.

### Cookie Exchange Example

This below shows a typical cookie flow when a user submits a name form:

1. **GET /** → Browser requests the webpage
2. **Server responds** with HTML form asking for name
3. **POST /** → Browser submits the form (name=adam)
4. **Server responds** with Set-Cookie: name=adam
5. **Next GET /** → Browser automatically sends Cookie: name=adam
6. **Server responds** with personalized message (“Welcome back adam”) instead of the form

**Key Points:**

- Cookies are most commonly used for **authentication** (login sessions).
- The cookie value is usually a **token** (not plain-text password).
- Cookies are sent automatically with every request to the same domain.

### Viewing Cookies in Your Browser

1. Open Developer Tools (F12 or right-click → Inspect)
2. Go to the **Network** tab
3. Refresh the page or interact with the site
4. Click any request → switch to the **Cookies** tab

You will see exactly which cookies are being sent and received.

**Room Completion:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Screenshot%20from%202026-04-24%2020-17-41.png)

---

### How Websites Work

When you visit a website, your browser sends a request to a web server (a dedicated computer somewhere on the Internet). The server responds with data, and your browser renders the page you see.

### Two Major Components of a Website

| Component     | Side        | Description                                                                   |
| ------------- | ----------- | ----------------------------------------------------------------------------- |
| **Front End** | Client-Side | Everything your browser renders and displays (what you see and interact with) |
| **Back End**  | Server-Side | The server that processes your request and generates the response             |
### Core Web Technologies

Websites are primarily built using three languages:
- **HTML**; Defines the structure and content of the page
- **CSS**; Adds styling, colours, layout, and visual appearance
- **JavaScript**; Adds interactivity and dynamic behaviour

### HyperText Markup Language (HTML)

**HTML** is the standard language used to create the structure of web pages. It uses **elements** (also called tags) to tell the browser how to display content.

### Basic HTML Document Structure

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Page Title</title>
    </head>
    <body>
        <h1>Large Heading</h1>
        <p>This is a paragraph.</p>
    </body>
</html>
```

### Key HTML Components

| Element                                   | Purpose                                                          |
| ----------------------------------------- | ---------------------------------------------------------------- |
| `<!DOCTYPE html>`                         | Declares the document as HTML5                                   |
| `<html>`                                  | Root element — contains all other elements                       |
| `<head>`                                  | Contains meta information (title, links, etc.) — **not visible** |
| `<body>`                                  | Contains all visible content of the page                         |
| `<h1>` to `<h6>`                          | Headings (largest to smallest)                                   |
| `<p>`                                     | Paragraphs                                                       |
| `<button>`, `<img>`, `<ul>`, `<li>`, etc. | Other common elements                                            |
### HTML Attributes

Attributes provide extra information about an element.
- ***class***: Used for styling (multiple elements can share the same class)
- ***id***: Unique identifier for a single element (used for styling and JavaScript)
- ***src***: Used with <img> to specify image location

**Examples:**

```html
<p class="bold-text">This paragraph has a class</p>
<p id="example">This paragraph has a unique ID</p>
<img src="img/cat.jpg" alt="A cute cat">
```

> ***Tip***
> You can view the raw HTML of any website by right-clicking anywhere on the page and selecting View Page Source (Chrome) or Show Page Source (Safari).

### JavaScript (JS)

**JavaScript** is the programming language that adds **interactivity** to websites. While HTML provides structure and CSS provides styling, JavaScript makes pages dynamic and responsive in real time.

- Without JavaScript, websites would be completely static.
- JS can change content, styles, and behaviour based on user actions (clicks, hovers, form submissions, etc.).

### How JavaScript is Added to a Page

JavaScript can be included in two ways:

- **Inline** (inside the HTML):
```HTML
<script>
    document.getElementById("demo").innerHTML = "Hack the Planet";
</script>
```

- **External file**:
```HTML
<script src="/location/of/javascript_file.js"></script>
```

### JavaScript Events

Elements can trigger JavaScript when certain events occur (e.g., clicking a button).

**Example:**

```HTML
<button onclick='document.getElementById("demo").innerHTML = "Button Clicked";'>
    Click Me!
</button>
```

> Events can also be defined inside <script> tags instead of directly on HTML elements. </script>

### Sensitive Data Exposure

**Sensitive Data Exposure** occurs when a website accidentally leaks sensitive information in its **front-end source code** (HTML, JavaScript, or comments) that should never be visible to users.

#### Why It Happens

Developers sometimes leave behind:
- Login credentials
- API keys
- Hidden links to admin panels or private areas
- Temporary passwords or debug information
- Comments containing sensitive data

### Real-World Impact
- An attacker can simply **right-click → View Page Source** and discover exposed credentials.
- These credentials may grant access to other parts of the application or even backend systems.

> ***Security Tip***
>  One of the first steps when assessing any web application is to **review the page source** (right-click -> View Page Source). Look for comments, hidden fields, or JavaScript variables that may contain credentials or sensitive paths.

### HTML Injection

**HTML Injection** is a vulnerability that occurs when a website fails to properly **sanitize** (filter) user input before displaying it on the page.

If user-supplied data is inserted directly into the page without filtering, an attacker can inject arbitrary **HTML** (and sometimes JavaScript) code that the browser will render as real content.

### How It Works

- A user submits input through a form or field.
- The website passes this input directly into the page (often via JavaScript).
- The browser interprets the input as legitimate HTML.

**Example Scenario**
- A form asks “What’s your name?”
- The input is passed to a JavaScript function (sayHi()).
- Whatever the user types is output directly onto the page.
- Entering <h1>Hacked!</h1> or other HTML/JS will be rendered as actual HTML.

### Why It’s Dangerous

- Attacker can change the appearance and behaviour of the page.
- Can be used to deface the site, create fake login forms, or prepare for more advanced attacks (e.g., XSS).

### Prevention

> **Golden Rule**: Never trust user input.

Developers must **sanitize** all user input before using it on the page. Common fix:

- Strip or escape HTML tags (<, >, &, etc.).
- Use proper output encoding.

> **Note** HTML Injection is a **client-side** vulnerability. It is different from database/server-side injections (covered in later rooms).

**Room Completion:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%20(6).png)

---

### Putting It All Together

When you request a webpage, several systems work together behind the scenes:

- Your computer uses **DNS** to resolve the domain name to an IP address.
- It then communicates with the web server using the **HTTP/HTTPS** protocol.
- The server responds with **HTML**, **CSS**, **JavaScript**, images, and other assets.
- Your browser renders everything into the final webpage you see.

### Additional Components That Power Modern Websites

| Component                          | Purpose                                                                  | Key Features                                                                                                                                                                                                                                          |
| ---------------------------------- | ------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Load Balancer**                  | Distributes incoming traffic across multiple web servers                 | - Handles high traffic - Provides failover (if one server fails, traffic is routed elsewhere) - Uses algorithms such as **round-robin** (cycles through servers) or **weighted** (sends to least busy server) - Performs **health checks** on servers |
| **CDN (Content Delivery Network)** | Delivers static files (JS, CSS, images, videos) faster                   | - Hosts files on thousands of servers worldwide - Automatically serves content from the server physically closest to the user - Dramatically reduces load on the origin web server                                                                    |
| **Database**                       | Stores and retrieves dynamic data (user accounts, posts, settings, etc.) | - Common types: MySQL, PostgreSQL, MongoDB, MSSQL - Ranges from simple files to complex clustered systems                                                                                                                                             |
| **WAF (Web Application Firewall)** | Protects the web server from attacks                                     | - Sits between the user and the server - Blocks common attack patterns - Detects bots vs real browsers - Uses **rate limiting** to prevent abuse (e.g., too many requests from one IP)                                                                |

> ***Summary***
> Load balancers and CDNs improve performance and reliability.
> Databases handle data storage.
> WAFs provide an extra layer of security against hacking attempts.


### How Web Servers Work

A **web server** is software that listens for incoming HTTP/HTTPS connections and delivers web content (HTML, images, CSS, JS, etc.) to clients.

**Common Web Servers:**

- **Apache**
- **Nginx**
- **IIS** (Internet Information Services – Microsoft)
- **NodeJS**

Web servers serve files from a **root directory** (also called document root):

| Web Server     | Default Root Directory (Linux) | Default Root Directory (Windows) |
| -------------- | ------------------------------ | -------------------------------- |
| Apache / Nginx | `/var/www/html`                | —                                |
| IIS            | —                              | `C:\inetpub\wwwroot`             |
Example: Requesting http://www.example.com/picture.jpg serves the file /var/www/html/picture.jpg from the server’s hard drive.

### Virtual Hosts

Web servers can host **multiple websites** on a single machine using **virtual hosts**.

- The server reads the Host header from the HTTP request.
- It matches the requested domain name to the correct virtual host configuration.
- Each virtual host can have its own root directory.

**Example:**

- one.com → /var/www/website_one
- two.com → /var/www/website_two

There is no limit to the number of virtual hosts you can configure.

### Static vs Dynamic Content

| Type        | Description                                     | Examples                                       | Changes per Request? |
| ----------- | ----------------------------------------------- | ---------------------------------------------- | -------------------- |
| **Static**  | Files served exactly as they are stored on disk | Images, CSS, JS, plain HTML                    | No                   |
| **Dynamic** | Content generated on-the-fly by the server      | Blog homepage, search results, user dashboards | Yes                  |
Dynamic content is processed in the **backend** using scripting languages. The user only sees the final result in the browser (**frontend**).

### Scripting & Backend Languages

Backend languages allow websites to become interactive and dynamic. They can:

- Interact with databases
- Process user input
- Call external APIs
- Generate custom responses

**Common Backend Languages:** PHP, Python, Ruby, NodeJS, Perl, etc.

**PHP Example:**

Request: http://example.com/index.php?name=adam

```php
<html><body>Hello <?php echo $_GET["name"]; ?></body></html>
```

**Output sent to the client:**

```HTML
<html><body>Hello adam</body></html>
```

> **Important Note** The client never sees the actual PHP code — it runs entirely on the server (backend). This powerful interactivity also introduces many security risks if the application is not built securely.

**Room Completed:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Screenshot%20from%202026-05-17%2001-55-49.png)

---

### Computer Fundamentals: Core Components & Boot Process

Every computer system consists of the same fundamental building blocks that work together to function.

> **Analogy**: The human body; each component has a specific role, just like organs in our body.

### Core Components of a Computer System

### The Boot Process

When you press the power button, a computer goes through a structured sequence before loading the Operating System.

|Step|Name|Description|
|---|---|---|
|**1**|Press the Power Button|Signal sent to the Power Supply Unit (PSU) to start providing power to all components.|
|**2**|Firmware Starts|UEFI (Unified Extensible Firmware Interface) initializes hardware components. **Note**: BIOS is the older equivalent, mostly replaced by UEFI.|
|**3**|Power-On Self Test (POST)|Firmware checks if all critical components are present, correctly configured, and functioning properly.|
|**4**|Select Boot Device|UEFI checks its boot order list and selects the device (SSD, HDD, USB, etc.) that contains the Operating System.|
|**5**|Initiate Bootloader|Bootloader loads the Operating System from the boot device into RAM. Once loaded, control is handed over from UEFI to the OS.|

> ***Key Takeaway***
> Understanding the boot process is crucial in cybersecurity, as it is often targeted by malware, bootkits, and rootkits.

**Room Complete:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Screenshot%20from%202026-05-26%2016-00-56.png)

---

### Computer Types

Computers come in many forms. Each type is designed with specific trade-offs between portability, performance, reliability, and purpose.

### Computers You Sit in Front Of

|Computer Type|Screen & Keyboard|Main Purpose|
|---|---|---|
|**Laptop**|Yes|Portable everyday computing|
|**Desktop**|Yes|Sustained performance at a fixed location|
|**Workstation**|Yes|Precision and reliability for professional tasks|
|**Server**|No|Providing services to many users over a network|

**Key Differences:**

- **Laptops** prioritize portability and battery life.
- **Desktops** offer better cooling and consistent performance using wall power.
- **Workstations** are optimized for accuracy and heavy professional workloads (e.g., 3D rendering, simulations).
- **Servers** run 24/7, have no direct user interface, and are built to handle requests from many users simultaneously.

### Portable and Everyday Devices

|Type|Description|Examples|
|---|---|---|
|**Smartphone**|Pocket-sized computer optimized for battery life and connectivity|iPhone, Android phones|
|**Tablet**|Touch-first computer with a larger screen|iPad, drawing tablets|

### IoT and Embedded Systems

| Type                  | Description                                                              | Examples                                                       |
| --------------------- | ------------------------------------------------------------------------ | -------------------------------------------------------------- |
| **IoT Device**        | Network-connected device built for a single purpose                      | Smart thermostat, doorbell, fitness tracker                    |
| **Embedded Computer** | Computer built into another device (may or may not connect to a network) | Controller in a coffee machine, automatic door sensor, car ECU |

> ***IoT vs Embedded***
>  Both are usually small and single-purpose. The main difference is connectivity: IoT devices communicate over a network, while embedded computers often operate silently inside a device without network access.

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%20(7).png)

---

### Client-Server Model

Most computer systems operate using the **client-server model**.

- **Client**: The device or program that initiates a request (e.g., a web browser).
- **Server**: The system that receives the request, processes it, and sends back a response.
- The client always starts the communication.

### Key Concepts

|Concept|Description|
|---|---|
|**Request**|Message sent by the client asking for a resource or action|
|**Response**|Message sent back by the server containing the result or data|
|**Protocol**|Set of rules defining how clients and servers communicate (commands, structure, syntax, responses)|
|**Port**|Number used to identify a specific service on a server (each service listens on its own port)|
|**DNS**|Resolves human-readable domain names (e.g., `www.example.com`) into IP addresses|

### HyperText Transfer Protocol (HTTP/HTTPS)

**HTTP** is the most common protocol used on the World Wide Web. **HTTPS** is the secure, encrypted version of HTTP.

- HTTP is **stateless**: Each request is independent; the server does not remember previous requests.
- Modern web applications use cookies or tokens to maintain session state (e.g., keeping you logged in).

### HTTP Methods

HTTP defines several methods (also called verbs). The most commonly used are:

- **GET** – Retrieve data from the server
- **POST** – Send data to the server (e.g., form submission)
- **PUT** – Update data
- **DELETE** – Delete data

(Other methods include PATCH, HEAD, OPTIONS, CONNECT, and TRACE)

### GET Method in Practice

The **GET** method is used to request a resource from a web server.

**Example:**

- GET https://tryhackme.com/index.php

When you type a URL into a browser:

1. The browser (client) constructs a GET request.
2. The server responds with a **status code** and the requested content.

### Inspecting a GET Request (Practical)

To view real HTTP requests and responses:

1. Open Firefox (or any browser)
2. Press **F12** or right-click → **Inspect**
3. Go to the **Network** tab
4. Reload the page (Ctrl + R)
5. Click on any request to see details:
    - **Scheme**: http or https
    - **Host**: Domain name of the server
    - **Filename**: Requested file/path (e.g., / usually means index.html)
    - **Address**: IP address of the server
    - **Status**: Response code (e.g., 200 OK = success)

The response contains:

- **Headers** (metadata)
- **Body** (actual content — usually HTML)

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%20(8).png)

---

### Virtualization

### Traditional Approach: One Server = One Application

Before virtualization, the standard practice was to run one application per physical server. This approach created several problems:

- **High cost** — Multiple physical servers meant high expenses for hardware, power, cooling, and maintenance.
- **Low utilization** — Most servers ran at only 5–20% capacity, wasting resources.
- **Slow deployment** — Setting up new physical servers could take days or weeks.
- **Difficult to scale** — Adding more resources often required purchasing additional hardware.

### What is Virtualization?

Virtualization allows **multiple operating systems and applications** to run on a single physical server by creating isolated virtual environments.

**Building Analogy**:
- The **building** = Physical server
- The **apartments** = Virtual Machines (VMs)
- The **tenants** = Operating systems / Applications
- The **building manager** = Hypervisor

Just like multiple apartments share the building’s infrastructure (electricity, water, elevators) while remaining private and independent, multiple VMs share the physical server’s hardware while staying isolated.

### Hypervisor

A **hypervisor** is the software layer that creates, manages, and isolates virtual machines on a physical host.

It performs the following tasks:

- Divides physical resources (CPU, RAM, storage) among VMs
- Keeps VMs isolated from each other
- Manages VM lifecycle (start, stop, pause, clone, delete)

#### Types of Hypervisors

| Hypervisor Type | Runs On              | Best For                         | Examples                       |
| --------------- | -------------------- | -------------------------------- | ------------------------------ |
| **Type 1**      | Directly on hardware | Production servers, data centers | VMware ESXi, Hyper-V, KVM      |
| **Type 2**      | Inside a host OS     | Testing, learning, development   | VirtualBox, VMware Workstation |

**Recommended Use Cases**:

| Use Case                     | Preferred Hypervisor    |
| ---------------------------- | ----------------------- |
| Production / Database Server | Type 1                  |
| Data Center                  | Type 1                  |
| Software Testing             | Type 2                  |
| Kali Linux / Learning        | Type 2                  |
| Testing Malicious Files      | Type 2 (with isolation) |

> **Security Note:** When testing malicious files in a VM, use a different operating system for the guest than the host, and keep the VM isolated from the host network.

### Virtual Machines (Lab Machines / VMs)

A **Virtual Machine (VM)** is a complete virtual computer created by the hypervisor.

Characteristics:

- Has its own virtual CPU, RAM, storage, and network
- Can run any operating system (Windows, Linux, etc.)
- Fully isolated from other VMs
- If one VM crashes or gets compromised, others remain unaffected

Common Type 2 hypervisors for personal use:

- Oracle VirtualBox
- VMware Workstation

### Containers

A **container** is a lightweight, isolated environment that packages an application and all its dependencies.

Key differences from VMs:

|Feature|Virtual Machine|Container|
|---|---|---|
|Includes full OS|Yes|No (shares host kernel)|
|Resource usage|Higher|Very low|
|Startup time|Minutes|Seconds|
|Isolation|Strong (separate OS)|Good (process-level)|
|Best for|Running different OSes|Running multiple instances of apps|

**Docker** is the most popular platform for building, shipping, and running containers.

> ***Summary***
> VMs provide strong isolation and flexibility (like full apartments). Containers provide speed and efficiency for running applications (like rooms inside an apartment).

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%20(9).png)

---

### Cloud Computing

### Evolution of Servers to Cloud

Before cloud computing, organizations followed the **“one server = one application”** model. Each physical server was dedicated to a single purpose.

This approach created several problems:
- High hardware, power, cooling, and maintenance costs
- Low resource utilization (often only 5–20%)
- Slow deployment times
- Difficult and expensive to scale

Cloud computing evolved to solve these issues by allowing multiple applications to share computing resources over the internet in a flexible, on-demand way.

### Cloud Benefits and Characteristics

Cloud computing offers several key advantages:

|Benefit|Description|
|---|---|
|**Scalability**|Easily increase or decrease resources as needed|
|**On-demand self-service**|Provision or remove servers and storage instantly|
|**Pay-as-you-go**|Pay only for the resources you actually use|
|**Security**|Cloud providers maintain strong infrastructure security|
|**High availability**|Systems remain operational even if parts fail|
|**Global access**|Applications can be accessed from anywhere in the world|

### Types of Cloud Deployment

| Type              | Description                                                                      | Best For                                                          |
| ----------------- | -------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| **Public Cloud**  | Resources owned and managed by a third-party provider and shared with many users | Startups, websites, most general use cases                        |
| **Private Cloud** | Dedicated infrastructure for a single organization                               | Banks, healthcare, government (sensitive data)                    |
| **Hybrid Cloud**  | Combination of public and private clouds                                         | Companies needing both control and scalability (e.g., e-commerce) |

### Cloud Service Models

Cloud services are offered in different layers of responsibility:

| Model    | Full Form                   | What You Manage                      | What Provider Manages                     | Analogy                       |
| -------- | --------------------------- | ------------------------------------ | ----------------------------------------- | ----------------------------- |
| **IaaS** | Infrastructure as a Service | Operating System, Applications, Data | Physical hardware, virtualization         | Renting an empty apartment    |
| **PaaS** | Platform as a Service       | Applications and data                | OS, runtime, servers, storage             | Renting a furnished apartment |
| **SaaS** | Software as a Service       | Only your data and usage             | Everything (application + infrastructure) | Renting a hotel room          |
**Examples**:

- **IaaS**: Amazon EC2, DigitalOcean Droplets
- **PaaS**: Heroku, Google App Engine
- **SaaS**: Gmail, Zoom, Netflix, Microsoft 365

### Major Cloud Providers

| Provider               | Strengths                                 | Notable For              |
| ---------------------- | ----------------------------------------- | ------------------------ |
| **AWS**                | Largest market share, most services       | Industry leader          |
| **Microsoft Azure**    | Strong enterprise & hybrid cloud support  | Business integration     |
| **Google Cloud (GCP)** | Powerful data analytics, AI, and ML tools | Data & AI workloads      |
| **Alibaba Cloud**      | Strong presence in Asia                   | Global expansion in Asia |
| **IBM Cloud**          | Hybrid cloud and AI solutions             | Enterprise AI            |
| **Oracle Cloud**       | Enterprise applications and databases     | Database-heavy workloads |

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%20(10).png)

---

### Operating Systems

### What is an Operating System?

An **Operating System (OS)** is the core software that manages all hardware and software on a computer. It acts as the central coordinator between the user, applications, and physical hardware.

**Airport Analogy**:

- **Hardware** (CPU, RAM, storage, devices) = Runways, airplanes, radar, and physical infrastructure
- **Applications** = Airlines and passengers requesting services
- **Operating System** = Air traffic control system that schedules, manages traffic, resolves conflicts, and ensures everything runs safely and efficiently

### Why We Need an Operating System

Without an OS, every application would need direct access to hardware (CPU, memory, files, devices). This would lead to conflicts, crashes, and security issues. The OS acts as the central manager that:

- Coordinates hardware and software
- Prevents applications from interfering with each other
- Provides a stable and secure environment for users and programs

### System Privilege Layers

Modern operating systems separate operations into two privilege levels:

| Layer            | Description                                                                  | Access Level                       |
| ---------------- | ---------------------------------------------------------------------------- | ---------------------------------- |
| **Kernel Space** | The core of the OS. Manages hardware and system resources directly           | Highest (unrestricted)             |
| **User Space**   | Where regular applications run. Applications cannot access hardware directly | Restricted (must use system calls) |

**System Calls**: When an application needs to access hardware (e.g., save a file, play sound, connect to Wi-Fi), it sends a request to the kernel through a **system call**. The kernel then performs the action on behalf of the application.

This separation ensures:

- One faulty or malicious app cannot crash the entire system
- Better security and stability

### Core Responsibilities of an Operating System

| Responsibility             | What the OS Does                                                                                  | Example                                                                     |
| -------------------------- | ------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| **Process Management**     | Creates, schedules, prioritizes, and terminates running programs                                  | Running browser, music player, and chat app simultaneously without freezing |
| **Memory Management**      | Allocates RAM to processes, protects memory between apps, and uses virtual memory when RAM is low | Opening multiple apps while keeping them isolated                           |
| **File System Management** | Organizes files and folders, handles permissions, naming, and metadata                            | Creating folders, saving files, setting read-only permissions               |
| **User Management**        | Manages user accounts, authentication, and access permissions                                     | Logging in with a password and keeping files private from other users       |
| **Device Management**      | Loads drivers and provides a universal interface for hardware                                     | Plugging in a mouse, printer, or USB drive and having it work immediately   |

### Operating System Security

The OS provides fundamental security even before any antivirus or firewall is installed:

- **Authentication**: Verifies user identity (passwords, biometrics, PIN)
- **Permissions**: Controls what each user and application can read, write, or execute
- **Isolation**: Keeps processes in separate protected memory spaces
- **System Protection**: Prevents unauthorized changes to critical system files and settings

### OS Interfaces

Users interact with an operating system through two main interfaces:

### Graphical User Interface (GUI)

- Visual, icon-based interface (windows, menus, icons)
- User-friendly and intuitive
- Best for everyday tasks and general users
- Requires more system resources

### Command-Line Interface (CLI)

- Text-based interface where commands are typed
- Offers greater precision, speed, and control
- Ideal for automation, scripting, and advanced system administration
- Requires knowledge of commands and syntax

| Feature           | GUI                                   | CLI                                      |
| ----------------- | ------------------------------------- | ---------------------------------------- |
| Interaction Style | Visual (icons, windows, menus)        | Text-based commands                      |
| Ease of Use       | High (beginner-friendly)              | Steeper learning curve                   |
| Speed & Precision | Slower for complex/repetitive tasks   | Much faster and more precise             |
| Resource Usage    | Higher                                | Very low                                 |
| Best For          | Everyday use, file browsing, settings | Scripting, automation, server management |

> Both ***GUI*** and ***CLI*** can perform the same tasks. The CLI is simply more direct and powerful for advanced users.

### Operating System Landscape

Different devices and use cases require different types of operating systems.

### Types of Operating Systems

| OS Type           | Primary Use Case                          | Key Characteristics                              |
| ----------------- | ----------------------------------------- | ------------------------------------------------ |
| **Desktop**       | Personal computers, work, gaming          | Rich GUI, multitasking, user-focused             |
| **Server**        | Web hosting, databases, cloud services    | Headless (no GUI), high uptime, multi-user       |
| **Mobile**        | Smartphones and tablets                   | Touch interface, power efficient, app sandboxing |
| **Embedded**      | Appliances, cars, IoT, routers, smart TVs | Very small footprint, specialized purpose        |
| **Virtual/Cloud** | VMs, containers, cloud instances          | Lightweight, scalable, fast deployment           |

### Major Operating System Families

#### Desktop Operating Systems

- **Windows**: Most widely used desktop OS 
	- Windows 10, Windows 11
- **macOS**: Apple’s desktop OS (known for polished GUI and ecosystem integration) 
	- Sonoma, Sequoia, Tahoe
- **Linux:** Family of open-source distributions
	- Ubuntu, Debian, Fedora

#### Server Operating Systems

- **Windows Server**: Used in corporate networks and data centers 
	- Server 2016, 2019, 2022, 2025
- **Linux**: Dominant in web servers and cloud infrastructure 
	- Ubuntu Server, Debian, CentOS, Red Hat
- **Unix**: Used in large enterprises, finance, and government 
	- IBM AIX, Oracle Solaris

#### Mobile Operating Systems

- **Android**: Most widely used mobile OS 
	- Android 14–16 (and manufacturer versions)
- **iOS**: Apple’s mobile OS for iPhone and iPad 
	- iOS 17, 18, 26

#### Embedded & IoT Operating Systems

- **Embedded Linux:** Lightweight Linux for specialized devices
	- OpenWrt, Ubuntu Core, Yocto Project
- **Real-Time Operating Systems (RTOS):** For systems requiring guaranteed response times
	- FreeRTOS, VxWorks, QNX

#### Virtual & Cloud Operating Systems

- **Cloud / VM OS:** Used in data centers and virtual machines
	- Ubuntu LTS, Amazon Linux, Rocky Linux
- **Container-optimized OS:** Lightweight systems designed for containers
	- Alpine Linux, Bottlerocket, Flatcar Linux

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%20(11).png)

---

### Windows Operating System

### User Accounts and Authentication

Before accessing the Windows Desktop, users must authenticate. Windows uses different account types with varying permission levels:

| Account Type      | Permissions                                                                               | Best For              |
| ----------------- | ----------------------------------------------------------------------------------------- | --------------------- |
| **Guest**         | Very limited access; cannot change system settings                                        | Temporary users       |
| **Standard**      | Can run applications and change personal settings, but cannot modify system-wide settings | Everyday users        |
| **Administrator** | Full control over the system (install software, change settings, manage users)            | System administration |

Windows verifies identity using passwords, PINs, or other methods during login.

### The Windows Desktop

After logging in, users are presented with the **Desktop**, which serves as the main workspace.

**Core Components of the Windows Desktop:**

1. **Desktop Icons** — Shortcuts to files, folders, and applications (fully customizable)
2. **Start Menu** — Primary access point for applications, settings, and power options
3. **Search** — Quickly find apps, files, folders, and settings
4. **Task View** — View and switch between all open windows
5. **Pinned Apps & Folders** — Quick access to frequently used items
6. **Network & Audio Settings** — Quick access to connectivity and sound options
7. **Date & Time** — Displays current date/time and opens a calendar
8. **Notifications** — Shows system and application notifications

**Taskbar**: The horizontal bar at the bottom that provides access to the Start Menu, pinned applications, and system tray.

### Start Menu

The **Start Menu** (accessed by clicking the Windows icon) acts as a central hub. It provides quick access to:

- Installed applications
- Settings
- Power options (Shut down, Restart, Sleep)
- Recently used files and folders

### Built-in Tools and Applications

Windows includes several useful built-in tools:

- **File Explorer** — Navigate and manage files and folders
- **Notepad** — Simple text editing
- **Settings** — Configure system options and view system information
- **Task Manager** — Monitor running processes and performance
- **Control Panel** — Advanced system configuration (legacy)

### File Explorer and File Management

Windows uses a **hierarchical folder structure** to organize files and folders.

**Key Locations:**

- Desktop
- Documents
- Downloads
- Pictures
- Music
- Videos

**File Explorer Features:**

- Navigate through folders using the address bar (shows full path, e.g., C:\Users\Administrator\Desktop)
- Search for files and folders within the current location
- View, copy, move, delete, and share files
- Change view modes (Details, Icons, List, etc.)

> **Tip**: The full path in File Explorer helps you understand exactly where a file or folder is located in the system.

### Windows Applications & Security

### Updating Applications

Keeping Windows and applications updated is essential for security and stability.

**Windows Update**

- Built-in tool that updates the operating system, security features, and some native apps.
- Can install updates automatically.
- Accessed via **Settings → Windows Update**.

**Application Updates**

- Built-in apps often update automatically.
- Third-party apps may have their own update mechanisms or prompt users on launch.
- Some require manual download and installation of new versions.

### Installing Applications

Windows supports multiple installation methods:

| Method                | Description                                           | File Type        | Notes                                       |
| --------------------- | ----------------------------------------------------- | ---------------- | ------------------------------------------- |
| **Microsoft Store**   | Curated and safe source for apps                      | Store apps       | Not available by default on Windows Server  |
| **From the Internet** | Download installer directly from the vendor’s website | `.exe` or `.msi` | Most common method for third-party software |

### Uninstalling Applications

Windows offers several ways to remove installed programs:

- Microsoft Store (for Store apps)
- **Settings → Apps → Installed apps**
- **Control Panel → Programs and Features**
- Application’s own built-in uninstaller

### Windows Settings vs Control Panel

| Tool                 | Description                                            | Best For                            |
| -------------------- | ------------------------------------------------------ | ----------------------------------- |
| **Windows Settings** | Modern, centralized interface for system configuration | Most everyday and advanced settings |
| **Control Panel**    | Legacy interface with older administrative tools       | Specific legacy or advanced tasks   |

Both tools allow users to manage display, audio, user accounts, apps, network, accessibility, and security settings.

### Task Manager

**Task Manager** provides real-time monitoring of system performance and running processes.

It contains five main tabs:

| Tab             | Purpose                                                            |
| --------------- | ------------------------------------------------------------------ |
| **Processes**   | View running apps and background processes with resource usage     |
| **Performance** | Graphs and statistics for CPU, memory, disk, and network           |
| **Users**       | Shows currently logged-in users and their resource consumption     |
| **Details**     | Technical view of processes with Process IDs (PIDs)                |
| **Services**    | View Windows services and their current status (Running / Stopped) |

### Native Windows Security

Windows includes built-in security tools that are enabled by default.

#### Windows Security

Central dashboard for system protection with four main sections:

| Section                           | Purpose                                            |
| --------------------------------- | -------------------------------------------------- |
| **Virus & threat protection**     | Real-time malware detection and customizable scans |
| **Firewall & network protection** | Controls inbound and outbound network traffic      |
| **App & browser control**         | Protects against unsafe apps, files, and websites  |
| **Device security**               | Hardware-based security features                   |
#### Windows Defender Firewall

Built-in firewall that monitors network connections and applies rules.

It uses three network profiles:

- **Domain** — Connected to an organization’s domain
- **Private** — Trusted networks (home or lab)
- **Public** — Untrusted networks (public Wi-Fi)

Advanced settings allow users to view and create inbound/outbound rules.

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%20(12).png)

---

### Linux Terminal Basics

The **terminal** (also called CLI) is a text-based interface used to control a Linux system. It is faster, more powerful, and often required for security tools and automation.

### Core Navigation Commands

|Command|Description|Example|
|---|---|---|
|pwd|Print Working Directory — shows your current location|pwd → /home/ubuntu|
|ls|List files and folders in the current directory|ls|
|ls -l|List with details (permissions, size, date, owner)|ls -l|
|ls -al|List **all** files including **hidden** ones (files starting with .)|ls -al|
|cd|Change Directory|cd Documents|
|cd ..|Go up one directory level|cd ..|
|find|Search for files and directories|find ~ -name mission_brief.txt|
|cat|Display the contents of a file|cat mission_brief.txt|

### Command Breakdown

**pwd** — Print Working Directory Shows the full path of the folder you are currently in.

**ls** — List Directory Contents

- ls → Simple list
- ls -l → Detailed view (permissions, size, modification date, owner)
- ls -al → Shows **hidden files** (files starting with a dot .)

**cd** — Change Directory

- cd foldername → Enter a folder
- cd .. → Go back to the parent folder
- cd ~ → Go to your home directory

**find** — Search for Files Used to locate files by name across the filesystem.

**Example:**

```Bash
find ~ -name mission_brief.txt
```

**cat** — View File Contents Displays the full content of a text file in the terminal.

**Example:**

```Bash
cat mission_brief.txt
```

### Quick Reference

|Goal|Command Example|
|---|---|
|See where you are|pwd|
|See what’s in the current folder|ls or ls -l|
|See hidden files too|ls -al|
|Go into a folder|cd Documents|
|Go back one level|cd ..|
|Find a specific file|find ~ -name filename.txt|
|Read the contents of a file|cat filename.txt|
### Linux System Information

### Gathering Basic System Information

When working in Linux, it is important to quickly understand the environment you are operating in. The following commands help you collect essential system details.

### Key Commands

|Command|Purpose|Example Output / Use Case|
|---|---|---|
|whoami|Shows the username you are currently logged in as|ubuntu|
|uname -a|Displays full system information (kernel, hostname, architecture)|Linux tryhackme ... x86_64 GNU/Linux|
|uname|Shows just the kernel name|Linux|
|df -h|Shows disk space usage in human-readable format|Lists mounted filesystems with size, used, available space|
|cat /etc/os-release|Displays detailed information about the Linux distribution|Shows distribution name, version, codename, etc.|

### Command Breakdown

**whoami** Prints the current logged-in username.

**uname -a** Provides detailed system information including:

- Kernel name
- Hostname
- Kernel version
- Architecture (x86_64)
- Operating system type (GNU/Linux)

**df -h** (Disk Free) Shows disk usage for all mounted filesystems in a human-readable format (-h = human readable). Useful for checking available storage before running tools or saving large files.

**/etc/os-release** A standard file that contains detailed information about the Linux distribution (name, version, codename, support URLs, etc.). This is often clearer than the output of uname.

**Example:**

```Bash
cat /etc/os-release
```

### Quick Reference Table

| Information Needed         | Command             |
| -------------------------- | ------------------- |
| Current username           | whoami              |
| Kernel & system details    | uname -a            |
| Disk space usage           | df -h               |
| Linux distribution details | cat /etc/os-release |
| Just the kernel name       | uname               |

**ROOM COMPLETE**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%20(13).png)

---

### Windows Command Prompt Basics

The **Command Prompt** (CLI) is a text-based interface for interacting with Windows. It is faster and more powerful than the GUI for many tasks, especially in cybersecurity and system administration.

### Navigating the Filesystem

| Command  | Description                                      | Example                 |
| -------- | ------------------------------------------------ | ----------------------- |
| `cd`     | Shows current directory or changes directory     | `cd Documents`          |
| `dir`    | Lists files and folders in the current directory | `dir`                   |
| `dir /a` | Lists **all** files, including **hidden** ones   | `dir /a`                |
| `dir /s` | Searches recursively through subfolders          | `dir /s task_brief.txt` |
| `cd ..`  | Moves up one directory level                     | `cd ..`                 |

### Finding and Reading Files

|Command|Description|Example|
|---|---|---|
|dir /s filename|Searches for a file in the current directory and all subdirectories|dir /s task_brief.txt|
|type filename|Displays the contents of a text file|type task_brief.txt|

### Gathering System Information

|Command|Purpose|Useful Information Provided|
|---|---|---|
|whoami|Shows the current logged-in username|Username|
|hostname|Shows the computer’s name|Computer name|
|systeminfo|Displays detailed system information|OS Name, Version, System Type (32/64-bit)|
|ipconfig|Shows network configuration|IPv4 Address, Default Gateway|

### Quick Reference

| Goal                                       | Command         |
| ------------------------------------------ | --------------- |
| Check current location                     | cd              |
| List files and folders                     | dir             |
| Show hidden files too                      | dir /a          |
| Search for a file recursively              | dir /s filename |
| Read a text file                           | type filename   |
| See who you are logged in as               | whoami          |
| Get computer name                          | hostname        |
| Get detailed Windows version & system info | systeminfo      |
| View network configuration                 | ipconfig        |

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%20(14).png)

---

### Operating System Security

### What is an Operating System?

An **Operating System (OS)** is the core software that sits between the computer **hardware** and the **applications** you use.

- **Hardware**: Physical components you can touch (CPU, RAM, storage, keyboard, screen, etc.).
- **Applications**: Programs like web browsers, messaging apps, games, etc.
- **Operating System**: Acts as the manager that controls hardware access for applications according to defined rules.

Without an OS, applications cannot directly and safely use the hardware.

### Types of Operating Systems

|Type|Examples|Primary Use Case|
|---|---|---|
|**Desktop**|Windows, macOS, Linux|Personal computers, work, gaming|
|**Mobile**|Android, iOS|Smartphones and tablets|
|**Server**|Windows Server, Linux distributions, Unix (AIX, Solaris)|Web hosting, databases, cloud services|
|**Embedded**|Specialized systems|IoT devices, cars, appliances|

### Security Principles (CIA Triad)

Security aims to protect three core principles:

|Principle|Goal|Example of Failure|
|---|---|---|
|**Confidentiality**|Ensure data is only accessible to authorized users|Unauthorized access to private files|
|**Integrity**|Ensure data is not tampered with|Files being modified without permission|
|**Availability**|Ensure systems and data are accessible when needed|Ransomware encrypting files|

### Common Weaknesses in Operating Systems

#### 1. Authentication and Weak Passwords

**Authentication** verifies a user’s identity. Common methods include:

- Something you **know** (password, PIN)
- Something you **are** (fingerprint, face ID)
- Something you **have** (phone for SMS)

Passwords remain the most common (and most attacked) method. Many users choose weak or reused passwords.

**Top 20 Most Common Passwords** (NCSC):

|Rank|Password|Rank|Password|
|---|---|---|---|
|1|123456|11|1234567890|
|2|123456789|12|123123|
|3|qwerty|13|000000|
|4|password|14|iloveyou|
|5|111111|15|1234|
|6|12345678|16|1q2w3e4r5t|
|7|abc123|17|qwertyuiop|
|8|1234567|18|123|
|9|password1|19|monkey|
|10|12345|20|dragon|

**Key Lesson**: Use strong, unique passwords for different accounts.

#### 2. Weak File Permissions

The **principle of least privilege** states that users and applications should only have access to what they need.

Weak file permissions can lead to:

- **Confidentiality** breaches (unauthorized reading of files)
- **Integrity** breaches (unauthorized modification of files)

#### 3. Malicious Programs

Malicious software can attack all three security principles:

|Type of Malware|Impact|Example|
|---|---|---|
|**Trojan Horse**|Gives attacker remote access|Backdoors|
|**Ransomware**|Encrypts files and demands payment|CryptoLocker, WannaCry|
|**Spyware**|Steals sensitive information|Keyloggers|

### Practical Example: Exploiting Weak Passwords

In real-world attacks, attackers often:

1. Discover usernames (sometimes left on sticky notes or through other means).
2. Try common or leaked passwords (e.g., dragon).
3. Attempt to log in via services like SSH.
4. Escalate privileges to root (Linux/macOS) or Administrator (Windows) for full control.

**Example Attack Flow (Linux)**:

- Use ssh username@target to attempt login.
- If successful, use commands like whoami, ls, and cat to explore the system.
- Weak passwords like dragon are still surprisingly effective due to poor user habits.

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%20(15).png)

---

### Data Representation
#### Representing Colors in Computers

Computers represent colors using the **RGB** model (Red, Green, Blue).

### From 8 Colors to 16 Million Colors

|Color Depth|Bits per Channel|Total Bits|Total Colors|Description|
|---|---|---|---|---|
|**8 colors**|1 bit|3 bits|8|Each color channel is either **on** or **off**|
|**16+ million colors**|8 bits|24 bits|16,777,216|Each color channel has 256 levels (0–255)|

**Example of 8-color representation:**

|Binary|Meaning|Color|
|---|---|---|
|000|All off|Black|
|001|Blue only|Blue|
|010|Green only|Green|
|100|Red only|Red|
|011|Green + Blue|Cyan|
|101|Red + Blue|Magenta|
|110|Red + Green|Yellow|
|111|All on|White|

A group of **8 bits** is called a **byte** (or octet). A 24-bit color = **3 bytes** (one byte each for Red, Green, and Blue).

### Hexadecimal Representation of Colors

Hexadecimal (base-16) is used because it is much more compact and readable than binary.

- Every **4 bits** = 1 hexadecimal digit
- One byte (8 bits) = **2 hexadecimal digits**

**Hexadecimal Digits:**

|Decimal|Hex|Binary|Decimal|Hex|Binary|
|---|---|---|---|---|---|
|0|0|0000|8|8|1000|
|1|1|0001|9|9|1001|
|2|2|0010|10|A|1010|
|3|3|0011|11|B|1011|
|4|4|0100|12|C|1100|
|5|5|0101|13|D|1101|
|6|6|0110|14|E|1110|
|7|7|0111|15|F|1111|

**Example:**

- Binary color: 10100011 11101010 00101010
- Hexadecimal: A3EA2A

This is the standard way colors are written in web design and graphics software (e.g., #A3EA2A).

### Binary Numbers

Computers use the **binary (base-2)** system. Each digit is either **0** or **1**, and each position represents a power of 2.

### Binary to Decimal Conversion

**Example:** Convert 1101 to decimal

11012=1×23+1×22+0×21+1×20=8+4+0+1=13101101_2 = 1 \times 2^3 + 1 \times 2^2 + 0 \times 2^1 + 1 \times 2^0 = 8 + 4 + 0 + 1 = 13_{10}11012​=1×23+1×22+0×21+1×20=8+4+0+1=1310​

**Quick Reference:**

|Binary|Decimal|Binary|Decimal|
|---|---|---|---|
|0000|0|1000|8|
|0001|1|1001|9|
|0010|2|1010|10|
|0011|3|1011|11|
|0100|4|1100|12|
|0101|5|1101|13|
|0110|6|1110|14|
|0111|7|1111|15|

### Hexadecimal Numbers

**Hexadecimal (base-16)** is widely used in computing because it is a compact way to represent binary data.

- Each hex digit represents exactly **4 bits**
- One byte = **2 hex digits**

### Hexadecimal to Decimal Conversion (Optional)

**Example:** Convert 9BDF to decimal

9BDF16=9×163+11×162+13×161+15×1609BDF_{16} = 9 \times 16^3 + 11 \times 16^2 + 13 \times 16^1 + 15 \times 16^09BDF16​=9×163+11×162+13×161+15×160

=9×4096+11×256+13×16+15×1=39,903= 9 \times 4096 + 11 \times 256 + 13 \times 16 + 15 \times 1 = 39,903=9×4096+11×256+13×16+15×1=39,903

### Optional: Octal Numbers

**Octal (base-8)** uses digits from 0 to 7. Each octal digit represents **3 bits**.

|Decimal|Octal|Binary|
|---|---|---|
|0|0|000|
|1|1|001|
|2|2|010|
|3|3|011|
|4|4|100|
|5|5|101|
|6|6|110|
|7|7|111|

Octal is rarely used today compared to hexadecimal.

**ROOM COMPLETE**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%20(16).png)

---
### Character Encoding

Computers store everything as numbers (bits). **Character encoding** is the agreed mapping between numbers and characters (letters, digits, punctuation, emojis, etc.).

- **Representation**: Data stored as bits and numbers in memory.
- **Encoding**: The standard that defines which number corresponds to which character.

If two systems use different encodings, text appears as **gibberish**.

### ASCII (American Standard Code for Information Interchange)

One of the earliest standards (1963). Uses **7 bits** (128 characters).

- English letters (A–Z, a–z)
- Digits (0–9)
- Punctuation and control characters

**Examples** (selected):

|Decimal|Hex|Binary|Character|
|---|---|---|---|
|48|30|00110000|0|
|65|41|01000001|A|
|97|61|01100001|a|
|127|7F|01111111|DEL|

**"TryHackMe" in ASCII** (hex): 54 72 79 48 61 63 6B 4D 65

### Limitations of ASCII & ISO-8859

ASCII only supports English. To support European languages, extensions like **ISO-8859** were created (8 bits = 256 characters).

Examples:

- **ISO-8859-1 (Latin-1)**: Western European (é, ç, ñ, ü, ß)
- **ISO-8859-2 (Latin-2)**: Central/Eastern European (č, ř, ł, ș, ț)

If a file saved in one encoding is opened with another, special characters appear incorrectly.

### Unicode & UTF Encodings

**Unicode** is the universal standard that assigns a unique number (code point) to every character in every language, plus emojis and symbols.

**UTF** (Unicode Transformation Format) defines how these code points are stored as bytes:

|Encoding|Bits per Character|Description|Common Use|
|---|---|---|---|
|**UTF-8**|1–4 bytes|Most efficient and widely used. Backward compatible with ASCII|Web, files, Linux, modern systems|
|**UTF-16**|2 or 4 bytes|Common characters use 2 bytes; rare ones use 4 bytes|Windows, Java|
|**UTF-32**|4 bytes (fixed)|Simplest but wastes space|Rare (internal use)|

**UTF-8** is the most popular encoding today because it balances efficiency and compatibility.

**Examples** (Unicode code points):

|Character|Unicode|UTF-8 (hex)|Notes|
|---|---|---|---|
|A|U+0041|41|ASCII compatible|
|🔥|U+1F525|F0 9F 94 A5|Emoji|
|龍|U+9F8D|E9 BE 8D|Chinese|
|😊|U+1F60A|F0 9F 98 8A|Emoji|
|ツ|U+30C4|E3 83 84|Japanese|
|ت|U+062A|D8 AA|Arabic|

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%20(17).png)

---

### Guess the Number Game (Python)

This simple game demonstrates core programming concepts:

- Random number generation
- User input and type conversion
- Conditional logic (if/elif/else)
- Loops (while)
- Variable tracking

### Version 1 – Basic Setup

```python
import random

secret = random.randint(1, 20)  # pick secret number
tries = 0
guess = 0                       # start outside valid range

print("I'm thinking of a number between 1 and 20")

text = input("Take a guess: ")  # input() returns text
guess = int(text)               # convert to integer

tries = tries + 1
```

### Version 2 – Adding Feedback

```Python
# ... (same setup as Version 1)

if guess < 1 or guess > 20:
    print("That number is out of range. Try again.")
elif guess < secret:
    print("Too low, try again.")
elif guess > secret:
    print("Too high, try again.")
else:
    print("You got it in", tries, "tries!")
```

### Version 3 – Full Game with Loop

```Python
import random

secret = random.randint(1, 20)
tries = 0
guess = 0

print("I'm thinking of a number between 1 and 20")

while guess != secret:               # repeat until correct
    text = input("Take a guess: ")
    guess = int(text)
    
    tries = tries + 1
    
    if guess < 1 or guess > 20:
        print("That number is out of range. Try again.")
    elif guess < secret:
        print("Too low, try again.")
    elif guess > secret:
        print("Too high, try again.")
    else:
        print("You got it in", tries, "tries!")
```

### Key Concepts Demonstrated

|Concept|How It’s Used in the Game|
|---|---|
|**Variables**|secret, guess, tries|
|**Input**|input() + int() conversion|
|**Loop**|while guess != secret|
|**Conditionals**|if / elif / else for feedback|
|**Random**|random.randint(1, 20)|

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%20(18).png)

---

### Guess the Number Game (JavaScript)

This simple program demonstrates core JavaScript concepts:

- Variables and constants
- User input with readline
- Random number generation
- Conditional logic (if / else if / else)
- Loops (while)
- Type conversion (parseInt)

### Version 1 – Basic Setup

```JavaScript
import * as readline from "node:readline/promises";
import { stdin as input, stdout as output } from "node:process";

const rl = readline.createInterface({ input, output });

try {
    const secret = Math.floor(Math.random() * 20) + 1; // 1 <= secret <= 20
    let tries = 0;
    let guess = 0;

    console.log("I'm thinking of a number between 1 and 20");

    const text = await rl.question("Take a guess: ");
    guess = parseInt(text, 10);
    tries = tries + 1;

} finally {
    rl.close();
}
```

### Version 2 – Adding Feedback

```JavaScript
// ... (same setup as Version 1)

    // Give a hint using if / else if / else.
    if (guess < 1 || guess > 20) {
        console.log("That number is out of range. Try again.");
    } else if (guess < secret) {
        console.log("Too low, try again.");
    } else if (guess > secret) {
        console.log("Too high, try again.");
    } else {
        console.log("You got it in", tries, "tries!");
    }
```

### Version 3 – Full Game with Loop

```JavaScript
// ... (same setup as Version 1)

    // Repeat until the user guesses the secret number.
    while (guess !== secret) {
        const text = await rl.question("Take a guess: ");
        guess = parseInt(text, 10);

        tries = tries + 1;

        // Give a hint using if / else if / else.
        if (guess < 1 || guess > 20) {
            console.log("That number is out of range. Try again.");
        } else if (guess < secret) {
            console.log("Too low, try again.");
        } else if (guess > secret) {
            console.log("Too high, try again.");
        } else {
            console.log("You got it in", tries, "tries!");
        }
    }
```

### Key Concepts Demonstrated

|Concept|How It’s Used in the Game|
|---|---|
|**Constants**|const secret (value never changes)|
|**Variables**|let tries, let guess|
|**User Input**|rl.question() + parseInt() conversion|
|**Loop**|while (guess !== secret)|
|**Conditional Logic**|if / else if / else for feedback|
|**Random Number**|Math.floor(Math.random() * 20) + 1|

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%20(19).png)

---

### Databases & SQL Basics

### What is a Database?

A **database** is an organized way for a computer to store and manage information. It allows fast searching, sorting, and filtering even with large amounts of data.

Think of it as a digital notebook that never runs out of pages.

### Tables, Columns, and Rows

|Component|Description|Café Example|
|---|---|---|
|**Table**|A collection of related records|Orders or Menu|
|**Column**|A specific type of information|drink, price, time|
|**Row**|One complete record|One customer order|

- One **row** = one complete record
- One **column** = one type of data

### SQL (Structured Query Language)

SQL is the language used to ask questions (queries) to a database.

|Clause|Purpose|Example|
|---|---|---|
|**SELECT**|Choose which columns to show|SELECT * or SELECT drink, price|
|**FROM**|Specify which table to use|FROM Orders|
|**WHERE**|Filter rows based on a condition|WHERE drink = 'Coffee'|
|**ORDER BY**|Sort results (add DESC for descending order)|ORDER BY price DESC|

### Common SQL Queries

**1. Show everything in a table**

```SQL
SELECT * FROM Orders;
```

**2. Show specific columns**

```SQL
SELECT drink, price FROM Orders;
```

**3. Filter results**

```SQL
SELECT * FROM Orders WHERE drink = 'Coffee';
```

**4. Sort results**

```SQL
SELECT * FROM Orders ORDER BY price;           -- ascending
SELECT * FROM Orders ORDER BY price DESC;      -- descending
```

**5. Combine filtering and sorting**

```SQL
SELECT * FROM Orders 
WHERE drink = 'Coffee' 
ORDER BY price DESC;
```

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%20(20).png)

---

### CIA Triad in Cybersecurity

The **CIA Triad** represents the three core principles of cybersecurity. Almost every security concept revolves around protecting or attacking one or more of these pillars.

|Principle|Goal|Example of Failure|
|---|---|---|
|**Confidentiality**|Ensure data is only accessible to authorized users|Unauthorized person reads private files|
|**Integrity**|Ensure data is not tampered with or altered|Unauthorized changes to records|
|**Availability**|Ensure data and services are accessible when needed|System or data becomes unreachable|

### Confidentiality

Protects sensitive data from unauthorized access.

**Real-world examples where confidentiality is achieved:**

- Internal company documents accessible only to authorized employees
- Private messages visible only to intended recipients

**Real-world examples where confidentiality is broken:**

- Credentials written on sticky notes
- Personal documents leaked online

### Integrity

Ensures data remains accurate and unaltered by unauthorized parties.

**Real-world examples where integrity is achieved:**

- Data changes only through authorized approval processes

**Real-world examples where integrity is broken:**

- Student attendance records changed after submission
- Order price modified before checkout

### Availability

Ensures authorized users can access data and services when needed.

**Real-world examples where availability is achieved:**

- All systems accessible to employees during working hours

**Real-world examples where availability is broken:**

- Critical services disrupted by software installation
- Company website offline during business hours

**ROOM COMPLETE:**

![](https://github.com/0xsimaa/THM_Notes/blob/main/Pre-Security/Pasted%20image%20(21).png)

---

