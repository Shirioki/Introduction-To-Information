
---

# **Networking Today - Cheat Sheet**

## **1. Networks Affect Our Lives**
- Networks connect people globally, enabling communication and collaboration.
- Examples: Social media, online banking, remote work.

## **2. Network Components**
- **Hosts (End Devices):** Computers, phones, printers.
- **Servers:** Provide services (email, web, file storage).
- **Clients:** Request services from servers.
- **Peer-to-Peer Networks:** Devices act as both client and server (small networks).
- **Intermediary Devices:** Switches, routers, firewalls.
- **Network Media:** Copper (electrical), fiber-optic (light), wireless (radio waves).

## **3. Network Representations & Topologies**
- **Network Diagrams:** Show physical (hardware layout) and logical (data flow) topologies.
- **Important Terms:** NIC (Network Interface Card), Physical Port, Interface.

## **4. Common Types of Networks**
- **LAN (Local Area Network):** Small geographical area (home, office).
- **WAN (Wide Area Network):** Large geographical area (internet).
- **Internet:** Global network connecting LANs and WANs.
- **Intranet:** Private network within an organization.
- **Extranet:** Secure access for external users (partners, suppliers).

## **5. Internet Connections**
- **Home & Small Office:** Cable, DSL, Cellular, Satellite, Dial-up.
- **Business Connections:** Leased Lines, Metro Ethernet, Business DSL, Satellite.
- **Converged Networks:** Single infrastructure for data, voice, and video.

## **6. Reliable Networks**
- **Fault Tolerance:** Redundant paths prevent failures.
- **Scalability:** Expands without performance loss.
- **Quality of Service (QoS):** Prioritizes critical traffic (VoIP, video).
- **Security:** Protects data and devices.

## **7. Network Trends**
- **BYOD (Bring Your Own Device):** Employees use personal devices.
- **Online Collaboration:** Tools like Cisco WebEx.
- **Video Communication:** Video conferencing for remote work.
- **Cloud Computing:** Public, Private, Hybrid, Custom clouds.
- **Smart Home Tech:** IoT devices automate home functions.
- **Powerline Networking:** Uses electrical wiring for network access.
- **Wireless Broadband:** ISP connections via cellular or satellite.

## **8. Network Security**
- **Threats:** Viruses, malware, denial-of-service attacks, identity theft.
- **Solutions:** Firewalls, antivirus, access control lists (ACL), VPNs.

---

# **Basic Switch & End Device Configuration - Cheat Sheet**  

## **1. Cisco IOS Access**  
- **Operating System Components:**  
  - **Shell:** User interface (CLI or GUI).  
  - **Kernel:** Manages hardware resources.  
  - **Hardware:** Physical components.  
- **Access Methods:**  
  - **Console:** Direct physical access for initial setup.  
  - **SSH:** Secure remote access (recommended).  
  - **Telnet:** Insecure remote access (plaintext).  
- **Terminal Emulation Programs:** PuTTY, Tera Term, SecureCRT.  

## **2. IOS Navigation**  
- **Command Modes:**  
  - **User EXEC Mode:** Limited monitoring commands (`Switch>`).  
  - **Privileged EXEC Mode:** Full access (`Switch#`).  
  - **Global Configuration Mode:** Modify device settings (`Switch(config)#`).  
  - **Line Configuration Mode:** Configure console, SSH, Telnet (`Switch(config-line)#`).  
  - **Interface Configuration Mode:** Configure switch/router ports (`Switch(config-if)#`).  
- **Navigation Commands:**  
  - `enable` → Enter Privileged EXEC Mode.  
  - `configure terminal` → Enter Global Configuration Mode.  
  - `exit` → Move back one level.  
  - `end` or `Ctrl+Z` → Return to Privileged EXEC Mode.  

## **3. Command Structure**  
- **Syntax Format:**  
  - **Keyword:** Predefined command (`ping`).  
  - **Argument:** User-defined value (`ping 192.168.1.1`).  
- **Help Features:**  
  - `?` → Shows available commands.  
  - `Tab` → Auto-completes command.  
- **Hotkeys & Shortcuts:**  
  - `Ctrl+C` → Exit configuration mode.  
  - `Ctrl+Z` → Save and exit.  
  - `Up Arrow` → Recall previous commands.  

## **4. Basic Device Configuration**  
- **Set Device Name:**  
  ```bash
  Switch(config)# hostname Sw-Floor-1
  ```  
- **Set Passwords:**  
  - **Console Access:**  
    ```bash
    Switch(config)# line console 0  
    Switch(config-line)# password cisco  
    Switch(config-line)# login  
    ```  
  - **Privileged EXEC Mode:**  
    ```bash
    Switch(config)# enable secret class  
    ```  
  - **VTY (Remote Access):**  
    ```bash
    Switch(config)# line vty 0 15  
    Switch(config-line)# password cisco  
    Switch(config-line)# login  
    ```  
- **Encrypt Passwords:**  
  ```bash
  Switch(config)# service password-encryption
  ```  
- **Set Banner Message:**  
  ```bash
  Switch(config)# banner motd #Authorized Access Only!#
  ```  

## **5. Save Configurations**  
- **Startup vs. Running Config:**  
  - **Startup-config:** Saved in **NVRAM** (persistent).  
  - **Running-config:** Stored in **RAM** (temporary).  
- **Save Running Config:**  
  ```bash
  Switch# copy running-config startup-config
  ```  
- **Erase Configuration:**  
  ```bash
  Switch# erase startup-config  
  Switch# reload  
  ```  

## **6. Ports & Addresses**  
- **IPv4 Address Format:** `192.168.1.10` (Dotted Decimal).  
- **Subnet Mask:** Defines network portion (`255.255.255.0`).  
- **Default Gateway:** Router IP for external communication (`192.168.1.1`).  
- **IPv6 Address Format:** `2001:db8:acad:10::10` (Hexadecimal).  

## **7. Configure IP Addressing**  
- **Manual IP Configuration (Windows):**  
  - **Control Panel** → **Network Sharing Center** → **Change Adapter Settings** → **Properties** → **IPv4 Settings**.  
- **Automatic IP Configuration (DHCP):**  
  - Select **"Obtain an IP address automatically"** in IPv4 settings.  
- **Configure Switch Virtual Interface (SVI):**  
  ```bash
  Switch(config)# interface vlan 1  
  Switch(config-if)# ip address 192.168.1.20 255.255.255.0  
  Switch(config-if)# no shutdown  
  ```  

---

# **Protocols & Models - Cheat Sheet**  

## **1. The Rules of Communication**  
- **Three elements of communication:**  
  - **Source (Sender)** → Origin of the message.  
  - **Destination (Receiver)** → Intended recipient.  
  - **Channel (Media)** → Path for communication.  
- **Protocols govern communication:**  
  - Define rules for message encoding, formatting, timing, and delivery.  
  - Ensure sender and receiver understand each other.  

## **2. Network Protocol Requirements**  
- **Message Encoding:** Converts data into a transmittable format.  
- **Message Formatting & Encapsulation:** Defines structure for transmission.  
- **Message Size:** Must match the transmission medium.  
- **Message Timing:** Includes flow control, response timeout, and access methods.  
- **Message Delivery Options:**  
  - **Unicast:** One-to-one communication.  
  - **Multicast:** One-to-many (selected recipients).  
  - **Broadcast:** One-to-all (IPv4 only).  

## **3. Network Protocols**  
- **Protocols define rules for communication:**  
  - Implemented in **software, hardware, or both**.  
  - Each protocol has a **specific function** (e.g., addressing, error detection).  
- **Common Protocols:**  
  - **HTTP:** Web communication.  
  - **TCP:** Reliable data transmission.  
  - **IP:** Global message delivery.  
  - **Ethernet:** Local network communication.  

## **4. Protocol Suites**  
- **Protocol Suite:** A group of interrelated protocols working together.  
- **Common Protocol Suites:**  
  - **TCP/IP (Internet Protocol Suite):** Most widely used.  
  - **OSI Model:** Standardized networking framework.  
  - **AppleTalk & Novell NetWare:** Proprietary suites.  
- **TCP/IP Layers:**  
  - **Application Layer:** HTTP, DNS, FTP.  
  - **Transport Layer:** TCP, UDP.  
  - **Internet Layer:** IPv4, IPv6, ICMP.  
  - **Network Access Layer:** Ethernet, WLAN.  

## **5. Standards Organizations**  
- **Open standards ensure interoperability and innovation.**  
- **Key organizations:**  
  - **IEEE:** Defines networking standards (Ethernet, Wi-Fi).  
  - **IETF:** Develops internet protocols (TCP/IP).  
  - **ICANN & IANA:** Manage IP addresses and domain names.  
  - **ITU-T:** Telecommunications standards (DSL, IPTV).  

## **6. Reference Models**  
- **OSI Model (7 Layers):**  
  1. **Application:** User interaction (HTTP, FTP).  
  2. **Presentation:** Data formatting (encryption, compression).  
  3. **Session:** Manages communication sessions.  
  4. **Transport:** Reliable data transfer (TCP, UDP).  
  5. **Network:** Routing and addressing (IP).  
  6. **Data Link:** MAC addressing, frame transmission.  
  7. **Physical:** Hardware transmission (cables, signals).  
- **TCP/IP Model (4 Layers):**  
  - **Application:** User interaction.  
  - **Transport:** Reliable communication.  
  - **Internet:** Routing and addressing.  
  - **Network Access:** Physical transmission.  

## **7. Data Encapsulation**  
- **Encapsulation:** Wrapping data with protocol headers before transmission.  
- **Encapsulation Process:**  
  1. **Data (Application Layer)**  
  2. **Segment (Transport Layer)**  
  3. **Packet (Network Layer)**  
  4. **Frame (Data Link Layer)**  
  5. **Bits (Physical Layer)**  

## **8. Data Access & Addressing**  
- **Layer 3 (Network Layer):** Uses **IP addresses** for global communication.  
- **Layer 2 (Data Link Layer):** Uses **MAC addresses** for local communication.  
- **Default Gateway:** Router interface that connects local networks to external networks.  
- **Addressing Differences:**  
  - **Same Network:** Uses MAC addresses for direct communication.  
  - **Different Network:** Uses IP addresses and routers for forwarding.  

---
