** Module 1 **
---

# **Networking Today **

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

# **Basic Switch & End Device Configuration - Module 2**  

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

# **Protocols & Models - Module 3**  

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

---

# **Physical Layer - Module 4**  

## **1. Purpose of the Physical Layer**  
- Establishes a **wired or wireless** connection to a network.  
- **Network Interface Card (NIC):** Connects a device to the network.  
- **Transports bits** across the network media.  
- **Encapsulation Process:** Converts frames into signals for transmission.  

## **2. Physical Layer Characteristics**  
- **Governed by Standards:** ISO, ANSI, IEEE, ITU-T, EIA/TIA.  
- **Three Functional Areas:**  
  - **Physical Components:** Hardware (NICs, cables, connectors).  
  - **Encoding:** Converts bits into recognizable patterns (Manchester, 4B/5B, 8B/10B).  
  - **Signaling:** Represents bit values (`1` and `0`) using electrical, light, or radio signals.  

## **3. Bandwidth & Performance Metrics**  
- **Bandwidth:** Maximum data transfer rate (bps, Kbps, Mbps, Gbps, Tbps).  
- **Latency:** Delay in data transmission.  
- **Throughput:** Actual data transfer rate.  
- **Goodput:** Usable data transfer rate (Throughput minus overhead).  

## **4. Copper Cabling**  
- **Common, inexpensive, easy to install.**  
- **Limitations:**  
  - **Attenuation:** Signal weakens over distance.  
  - **Interference:** EMI, RFI, Crosstalk.  
- **Types of Copper Cabling:**  
  - **Unshielded Twisted Pair (UTP):** Most common, RJ-45 connectors.  
  - **Shielded Twisted Pair (STP):** Better noise protection, harder to install.  
  - **Coaxial Cable:** Used in cable internet and wireless installations.  

## **5. UTP Cabling Standards**  
- **TIA/EIA-568:** Defines cable types, lengths, connectors, termination.  
- **Categories:**  
  - **Cat 3:** Older, low-speed.  
  - **Cat 5/5e:** Common for Ethernet.  
  - **Cat 6:** Higher performance.  
- **Cable Types:**  
  - **Straight-through:** Host to network device.  
  - **Crossover:** Host-to-host, switch-to-switch (Legacy).  
  - **Rollover:** Cisco proprietary, connects to console ports.  

## **6. Fiber-Optic Cabling**  
- **Higher bandwidth, longer distances, immune to EMI/RFI.**  
- **Uses light pulses instead of electrical signals.**  
- **Types:**  
  - **Single-Mode Fiber (SMF):** Small core, long-distance, expensive lasers.  
  - **Multimode Fiber (MMF):** Larger core, shorter distance, cheaper LEDs.  
- **Fiber Connectors:** ST, SC, LC, Duplex LC.  

## **7. Wireless Media**  
- **Uses electromagnetic signals (radio/microwave).**  
- **Limitations:** Coverage area, interference, security, shared bandwidth.  
- **Wireless Standards:**  
  - **Wi-Fi (802.11):** Wireless LAN.  
  - **Bluetooth (802.15):** Short-range WPAN.  
  - **WiMAX (802.16):** Broadband wireless.  
  - **Zigbee (802.15.4):** IoT applications.  
- **Wireless LAN (WLAN) Components:**  
  - **Wireless Access Point (AP):** Connects wireless devices to network.  
  - **Wireless NIC Adapters:** Enable wireless communication.  

---

# **Number Systems - Module 5**  

## **1. Binary Number System**  
- **Base-2 system:** Uses only `0` and `1`.  
- **Used in networking:** IPv4 addresses, MAC addresses, and data transmission.  
- **IPv4 Address Structure:**  
  - **32-bit address** divided into **four octets** (8 bits each).  
  - Example: `11000000.10101000.00001010.00001010` → `192.168.10.10`.  
- **Binary Positional Notation:**  
  - Each position represents a power of **2** (128, 64, 32, 16, 8, 4, 2, 1).  
  - Example: `11000000` → `1×128 + 1×64 + 0×32 + 0×16 + 0×8 + 0×4 + 0×2 + 0×1 = 192`.  

## **2. Converting Binary to Decimal**  
- **Step-by-step method:**  
  - Multiply each binary digit by its positional value.  
  - Add the results to get the decimal equivalent.  
- **Example:** Convert `10101000` to decimal:  
  - `1×128 + 0×64 + 1×32 + 0×16 + 1×8 + 0×4 + 0×2 + 0×1 = 168`.  

## **3. Converting Decimal to Binary**  
- **Step-by-step method:**  
  - Start with the highest positional value (128).  
  - If the decimal number is **≥** positional value, subtract and write `1`.  
  - If **<**, write `0`.  
- **Example:** Convert `168` to binary:  
  - `168 - 128 = 40` → `1` in **128** position.  
  - `40 < 64` → `0` in **64** position.  
  - `40 - 32 = 8` → `1` in **32** position.  
  - `8 < 16` → `0` in **16** position.  
  - `8 - 8 = 0` → `1` in **8** position.  
  - Remaining positions are `0`.  
  - **Result:** `10101000`.  

## **4. Hexadecimal Number System**  
- **Base-16 system:** Uses digits `0-9` and letters `A-F`.  
- **Used in networking:** IPv6 addresses, MAC addresses.  
- **IPv6 Address Structure:**  
  - **128-bit address** divided into **eight hextets** (16 bits each).  
  - Example: `2001:0db8:85a3:0000:0000:8a2e:0370:7334`.  

## **5. Converting Decimal to Hexadecimal**  
- **Step-by-step method:**  
  - Convert decimal to **binary**.  
  - Group binary digits into **4-bit chunks**.  
  - Convert each **4-bit chunk** to hexadecimal.  
- **Example:** Convert `168` to hexadecimal:  
  - `168` in binary: `10101000`.  
  - Split into **4-bit groups**: `1010` and `1000`.  
  - `1010 = A`, `1000 = 8`.  
  - **Result:** `A8`.  

## **6. Converting Hexadecimal to Decimal**  
- **Step-by-step method:**  
  - Convert hexadecimal to **binary**.  
  - Convert binary to **decimal**.  
- **Example:** Convert `D2` to decimal:  
  - `D2` in binary: `1101 0010`.  
  - Convert binary to decimal: `1×128 + 1×64 + 0×32 + 1×16 + 0×8 + 0×4 + 1×2 + 0×1 = 210`.  
  - **Result:** `210`.  

## **7. Key Terms**  
- **Dotted Decimal Notation:** IPv4 format (`192.168.10.10`).  
- **Positional Notation:** Value depends on position in the number.  
- **Radix:** Base of a numbering system (Binary = 2, Decimal = 10, Hexadecimal = 16).  
- **Octet:** 8-bit section of an IPv4 address.  
- **Hextet:** 16-bit section of an IPv6 address.  

---

---

# **Data Link Layer - Module 6**  

## **1. Purpose of the Data Link Layer**  
- **Handles communication** between network interface cards (NICs).  
- **Encapsulates Layer 3 packets** (IPv4/IPv6) into Layer 2 frames.  
- **Performs error detection** and rejects corrupted frames.  

### **IEEE 802 LAN/MAN Data Link Sublayers**  
- **Logical Link Control (LLC):** Interfaces between networking software and hardware.  
- **Media Access Control (MAC):** Handles data encapsulation and media access control.  

### **Data Link Layer Functions**  
- **Accepts a frame** from the network medium.  
- **De-encapsulates** the frame to expose the packet.  
- **Re-encapsulates** the packet into a new frame.  
- **Forwards** the new frame to the next network segment.  

### **Data Link Layer Standards**  
- **IEEE (Institute of Electrical and Electronic Engineers)**  
- **ITU (International Telecommunications Union)**  
- **ISO (International Organization for Standardization)**  
- **ANSI (American National Standards Institute)**  

---

## **2. Network Topologies**  

### **Physical vs. Logical Topologies**  
- **Physical Topology:** Shows actual device connections.  
- **Logical Topology:** Shows virtual connections (IP addressing, interfaces).  

### **Common WAN Topologies**  
- **Point-to-Point:** Direct link between two endpoints.  
- **Hub and Spoke:** Central site connects branch sites via point-to-point links.  
- **Mesh:** High availability, but costly (each device connects to every other device).  

### **Common LAN Topologies**  
- **Star:** Devices connect to a central switch (most common).  
- **Extended Star:** Multiple star networks interconnected.  
- **Bus:** Devices connected in a single chain (legacy).  
- **Ring:** Devices connected in a circular fashion (legacy).  

### **Half vs. Full Duplex Communication**  
- **Half-Duplex:** Devices take turns sending/receiving (used in WLANs, legacy Ethernet hubs).  
- **Full-Duplex:** Devices send and receive simultaneously (Ethernet switches).  

### **Media Access Control Methods**  
- **Contention-Based Access:**  
  - **CSMA/CD (Carrier Sense Multiple Access with Collision Detection):** Used in legacy Ethernet LANs.  
  - **CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance):** Used in WLANs.  
- **Controlled Access:**  
  - **Deterministic access:** Each node gets a turn (used in Token Ring, ARCNET).  

---

## **3. Data Link Frame**  

### **Frame Structure**  
- **Header:** Contains addressing and control information.  
- **Data:** Encapsulated Layer 3 packet.  
- **Trailer:** Includes error detection (Cyclic Redundancy Check - CRC).  

### **Frame Fields**  
| **Field**       | **Description** |
|----------------|---------------|
| **Frame Start & Stop** | Identifies beginning and end of frame |
| **Addressing** | Source and destination MAC addresses |
| **Type** | Identifies encapsulated Layer 3 protocol |
| **Control** | Flow control services |
| **Data** | Contains the frame payload |
| **Error Detection** | Ensures data integrity (CRC) |

### **Layer 2 Addresses (MAC Addresses)**  
- **Also called physical addresses.**  
- **Used for local delivery** of frames on the same network segment.  
- **Updated by each device** that forwards the frame.  

### **Common Data Link Layer Protocols**  
- **Ethernet (IEEE 802.3)**  
- **Wi-Fi (IEEE 802.11)**  
- **Point-to-Point Protocol (PPP)**  
- **High-Level Data Link Control (HDLC)**  
- **Frame Relay**  

---

---

# **Ethernet Switching - Module 7**  

## **1. Ethernet Frames**  
- **Operates at Layer 2 (Data Link) and Layer 1 (Physical).**  
- **Defined by IEEE 802.2 (LLC) and IEEE 802.3 (MAC).**  
- **Frame Size:**  
  - **Minimum:** 64 bytes  
  - **Maximum:** 1518 bytes  
  - **Jumbo Frames:** Larger than 1500 bytes (supported by Gigabit Ethernet).  
- **Frame Fields:**  
  | **Field** | **Description** |
  |-----------|---------------|
  | **Preamble & SFD** | Synchronization for frame transmission |
  | **Destination MAC** | Identifies recipient device |
  | **Source MAC** | Identifies sender device |
  | **Type/Length** | Specifies upper-layer protocol |
  | **Data** | Encapsulated Layer 3 packet |
  | **FCS (Frame Check Sequence)** | Error detection (CRC) |

---

## **2. Ethernet MAC Address**  
- **48-bit binary value (6 bytes), expressed in hexadecimal.**  
- **Formats:**  
  - **Dashes:** `00-60-2F-3A-07-BC`  
  - **Colons:** `00:60:2F:3A:07:BC`  
  - **Periods:** `0060.2F3A.07BC`  
- **MAC Address Components:**  
  - **Organizationally Unique Identifier (OUI):** First 3 bytes (assigned by IEEE).  
  - **Vendor Assigned:** Last 3 bytes (unique per device).  
- **Types of MAC Addresses:**  
  - **Unicast:** One-to-one communication.  
  - **Broadcast:** Sent to all devices (`FF-FF-FF-FF-FF-FF`).  
  - **Multicast:** Sent to a group (`01-00-5E` for IPv4, `33-33` for IPv6).  

---

## **3. MAC Address Table & Switch Learning**  
- **Layer 2 Ethernet switches use MAC addresses for forwarding decisions.**  
- **Switch Learning Process:**  
  1. **Examines Source MAC Address:** Adds new entries to MAC table.  
  2. **Finds Destination MAC Address:**  
     - If **found**, forwards frame to correct port.  
     - If **not found**, floods frame to all ports (except incoming).  
- **MAC Address Table (CAM Table):** Stores learned MAC addresses and associated ports.  

---

## **4. Switch Forwarding Methods**  
- **Store-and-Forward Switching:**  
  - Receives entire frame, checks for errors (CRC).  
  - Ensures data integrity before forwarding.  
  - Required for **QoS (Quality of Service)** in VoIP and video traffic.  
- **Cut-Through Switching:**  
  - Forwards frame before fully receiving it.  
  - **Fast-Forward Switching:** Lowest latency, forwards immediately.  
  - **Fragment-Free Switching:** Checks first 64 bytes for errors before forwarding.  

---

## **5. Memory Buffering on Switches**  
- **Port-Based Memory:** Frames stored in queues linked to specific ports.  
- **Shared Memory:** Frames stored in a common buffer, dynamically allocated to ports.  

---

## **6. Duplex & Speed Settings**  
- **Full-Duplex:** Devices send and receive simultaneously (recommended).  
- **Half-Duplex:** Devices take turns sending/receiving (causes collisions).  
- **Autonegotiation:** Automatically selects best speed and duplex settings.  
- **Gigabit Ethernet:** Always operates in full-duplex mode.  
- **Duplex Mismatch:** Occurs when one device is full-duplex and the other is half-duplex, causing performance issues.  

---

## **7. Auto-MDIX (Automatic Medium-Dependent Interface Crossover)**  
- **Automatically detects cable type (straight-through or crossover).**  
- **Enabled by default on Cisco switches (IOS 12.2(18)SE or later).**  
- **Command to enable manually:**  
  ```bash
  Switch(config-if)# mdix auto
  ```  

---

**Module 8: Network Layer** 🚀  

---

# **Network Layer **  

## **1. Network Layer Characteristics**  
- **Provides services** for end devices to exchange data.  
- **Uses IPv4 and IPv6** as primary communication protocols.  
- **Performs four key functions:**  
  - **Addressing:** Assigns unique IP addresses to devices.  
  - **Encapsulation:** Wraps transport layer segments into IP packets.  
  - **Routing:** Determines best path for packet delivery.  
  - **De-encapsulation:** Extracts transport layer data at the destination.  

### **IP Characteristics**  
- **Connectionless:** No prior connection is established before sending packets.  
- **Best Effort:** No guarantee of delivery (no acknowledgments or retransmissions).  
- **Media Independent:** Works over copper, fiber, wireless, etc.  

### **Maximum Transmission Unit (MTU)**  
- **Determined by the data link layer.**  
- **Fragmentation:** IPv4 splits packets if they exceed MTU (causes latency).  
- **IPv6 does not fragment packets.**  

---

## **2. IPv4 Packet Structure**  
- **IPv4 Header Fields:**  
  | **Field** | **Description** |
  |-----------|---------------|
  | **Version** | Identifies IPv4 (binary `0100`). |
  | **Differentiated Services (DSCP)** | Used for Quality of Service (QoS). |
  | **Header Checksum** | Detects corruption in the header. |
  | **Time-to-Live (TTL)** | Limits packet lifespan (decreases per hop). |
  | **Protocol** | Identifies next-layer protocol (TCP, UDP, ICMP). |
  | **Source IP Address** | 32-bit address of sender. |
  | **Destination IP Address** | 32-bit address of receiver. |

---

## **3. IPv6 Packet Structure**  
- **IPv6 Improvements Over IPv4:**  
  - **128-bit addressing** (vastly more addresses).  
  - **Simplified header** (fewer fields, better performance).  
  - **Eliminates NAT** (direct end-to-end connectivity).  

- **IPv6 Header Fields:**  
  | **Field** | **Description** |
  |-----------|---------------|
  | **Version** | Identifies IPv6 (binary `0110`). |
  | **Traffic Class** | Equivalent to DSCP for QoS. |
  | **Flow Label** | Ensures consistent handling of packets in a flow. |
  | **Payload Length** | Specifies data size in the packet. |
  | **Next Header** | Identifies next-layer protocol (TCP, UDP, ICMPv6). |
  | **Hop Limit** | Replaces TTL (limits packet lifespan). |
  | **Source IP Address** | 128-bit sender address. |
  | **Destination IP Address** | 128-bit receiver address. |

- **IPv6 Extension Headers:**  
  - Optional headers placed between IPv6 header and payload.  
  - Used for fragmentation, security, mobility support.  

---

## **4. Host Routing Decisions**  
- **Hosts determine if a destination is:**  
  - **Itself:** Uses `127.0.0.1` (IPv4) or `::1` (IPv6).  
  - **Local Host:** Destination is on the same LAN.  
  - **Remote Host:** Destination is outside the LAN.  

### **Default Gateway (DGW)**  
- **Router or Layer 3 switch** that forwards packets outside the LAN.  
- **Must have an IP address in the same subnet as the LAN.**  
- **Without a default gateway, remote communication is impossible.**  

### **Host Routing Table Commands:**  
- **Windows:**  
  ```bash
  netstat -r
  route print
  ```  
- **Linux/macOS:**  
  ```bash
  ip route show
  ```  

---

## **5. Router Routing Tables**  
- **Routers use routing tables to forward packets.**  
- **Three types of routes:**  
  - **Directly Connected:** Automatically added when an interface is active.  
  - **Remote Routes:** Learned via static configuration or dynamic routing protocols.  
  - **Default Route:** Used when no specific match is found.  

### **Router Routing Table Commands:**  
- **Cisco IOS:**  
  ```bash
  show ip route
  ```  
- **Route Sources in `show ip route`:**  
  | **Code** | **Meaning** |
  |---------|------------|
  | **L** | Local interface IP address |
  | **C** | Directly connected network |
  | **S** | Static route (manually configured) |
  | **O** | OSPF (dynamic routing protocol) |
  | **D** | EIGRP (dynamic routing protocol) |

---

## **6. Static vs. Dynamic Routing**  
### **Static Routing**  
- **Manually configured by an administrator.**  
- **Does not adjust automatically if topology changes.**  
- **Best for small, stable networks.**  
- **Example:**  
  ```bash
  R1(config)# ip route 10.1.1.0 255.255.255.0 209.165.200.226
  ```  

### **Dynamic Routing**  
- **Automatically discovers remote networks.**  
- **Updates routing tables dynamically.**  
- **Chooses best path based on metrics.**  
- **Example (OSPF):**  
  ```bash
  R1(config)# router ospf 1
  R1(config-router)# network 192.168.10.0 0.0.0.255 area 0
  ```  

---

**Module 9: Address Resolution** 

---

# **Address Resolution **  

## **1. MAC and IP Addresses**  
- **Devices have two primary addresses:**  
  - **MAC Address (Layer 2):** Physical address used for NIC-to-NIC communication on the same network.  
  - **IP Address (Layer 3):** Logical address used to send packets across networks.  
- **Same Network Communication:**  
  - Destination MAC address = MAC of the destination device.  
- **Remote Network Communication:**  
  - Destination MAC address = MAC of the default gateway (router).  

---

## **2. Address Resolution Protocol (ARP) - IPv4**  
- **Purpose:** Resolves IPv4 addresses to MAC addresses.  
- **Functions:**  
  - **Finds MAC address** of a device when only the IPv4 address is known.  
  - **Maintains an ARP table** (IPv4-to-MAC mappings).  
- **ARP Process:**  
  1. Device checks ARP table for destination MAC address.  
  2. If found, it uses the MAC address.  
  3. If not found, it sends an **ARP Request** (broadcast).  
  4. Destination device replies with an **ARP Reply** (unicast).  
  5. Sender updates its ARP table with the new MAC address.  

### **ARP Table Management**  
- **Entries are temporary** and removed when the ARP cache timer expires.  
- **Commands to view ARP table:**  
  - **Cisco Router:**  
    ```bash
    show ip arp
    ```  
  - **Windows PC:**  
    ```bash
    arp -a
    ```  
- **ARP Issues:**  
  - **Broadcast Overhead:** Excessive ARP requests reduce network performance.  
  - **ARP Spoofing (Poisoning):** Attackers send fake ARP replies to intercept traffic.  
  - **Mitigation:** Enterprise switches use security features to prevent ARP attacks.  

---

## **3. IPv6 Neighbor Discovery (ND)**  
- **IPv6 does NOT use ARP.**  
- **Uses ICMPv6 Neighbor Discovery (ND) protocol for address resolution.**  
- **Functions:**  
  - **Address resolution** (similar to ARP).  
  - **Router discovery** (finds default gateway).  
  - **Redirection services** (optimizes routing).  

### **ICMPv6 ND Messages**  
| **Message Type** | **Purpose** |
|-----------------|------------|
| **Neighbor Solicitation (NS)** | Requests MAC address of a known IPv6 address. |
| **Neighbor Advertisement (NA)** | Responds with MAC address of requested IPv6 address. |
| **Router Solicitation (RS)** | Requests information from routers. |
| **Router Advertisement (RA)** | Routers provide configuration details to hosts. |
| **Redirect Message** | Helps devices choose better next-hop routers. |

### **IPv6 Address Resolution Process**  
1. Device sends **ICMPv6 Neighbor Solicitation** (multicast).  
2. Target device replies with **ICMPv6 Neighbor Advertisement** (unicast).  
3. Sender updates its ND table with the MAC address.  

---

## **4. Key Commands & Terms**  
- **Address Resolution Protocol (ARP)**  
- **ARP Table**  
- **show ip arp** (Cisco router command)  
- **arp -a** (Windows command)  
- **ICMPv6 Neighbor Discovery (ND)**  
- **ICMPv6 Neighbor Solicitation (NS) message**  
- **ICMPv6 Neighbor Advertisement (NA) message**  
- **ICMPv6 Router Solicitation (RS) message**  
- **ICMPv6 Router Advertisement (RA) message**  
- **ICMPv6 Redirect Message**  

---

**Module 10: Basic Router Configuration**  

---

# **Basic Router Configuration **  

## **1. Initial Router Configuration**  
### **Basic Setup Steps:**  
1. **Set the hostname:**  
   ```bash
   Router(config)# hostname R1
   ```  
2. **Secure privileged EXEC mode:**  
   ```bash
   Router(config)# enable secret class
   ```  
3. **Secure console access:**  
   ```bash
   Router(config)# line console 0  
   Router(config-line)# password cisco  
   Router(config-line)# login  
   ```  
4. **Secure remote access (Telnet/SSH):**  
   ```bash
   Router(config)# line vty 0 4  
   Router(config-line)# password cisco  
   Router(config-line)# login  
   Router(config-line)# transport input ssh telnet  
   ```  
5. **Encrypt all plaintext passwords:**  
   ```bash
   Router(config)# service password-encryption
   ```  
6. **Set a legal notification banner:**  
   ```bash
   Router(config)# banner motd # WARNING: Unauthorized access prohibited! #
   ```  
7. **Save the configuration:**  
   ```bash
   Router# copy running-config startup-config
   ```  

---

## **2. Configuring Router Interfaces**  
### **Steps to Activate an Interface:**  
1. **Enter interface configuration mode:**  
   ```bash
   Router(config)# interface gigabitEthernet 0/0/0
   ```  
2. **Add a description:**  
   ```bash
   Router(config-if)# description Link to LAN
   ```  
3. **Assign an IPv4 address:**  
   ```bash
   Router(config-if)# ip address 192.168.10.1 255.255.255.0
   ```  
4. **Assign an IPv6 address:**  
   ```bash
   Router(config-if)# ipv6 address 2001:db8:acad:10::1/64
   ```  
5. **Enable the interface:**  
   ```bash
   Router(config-if)# no shutdown
   ```  
6. **Exit interface configuration:**  
   ```bash
   Router(config-if)# exit
   ```  

### **Example Interface Configuration:**  
```bash
R1(config)# interface gigabitEthernet 0/0/1  
R1(config-if)# description Link to R2  
R1(config-if)# ip address 209.165.200.225 255.255.255.252  
R1(config-if)# ipv6 address 2001:db8:feed:224::1/64  
R1(config-if)# no shutdown  
R1(config-if)# exit  
```  

---

## **3. Verifying Interface Configuration**  
### **Useful Commands:**  
| **Command** | **Description** |
|------------|---------------|
| `show ip interface brief` | Displays all interfaces, IP addresses, and status. |
| `show ipv6 interface brief` | Displays IPv6 addresses and interface status. |
| `show ip route` | Displays the IPv4 routing table. |
| `show ipv6 route` | Displays the IPv6 routing table. |
| `show interfaces` | Displays detailed statistics for all interfaces. |
| `show ip interface` | Displays IPv4 statistics for all interfaces. |
| `show ipv6 interface` | Displays IPv6 statistics for all interfaces. |

### **Example Output:**  
```bash
R1# show ip interface brief  
Interface              IP-Address      OK? Method Status  Protocol  
GigabitEthernet0/0/0   192.168.10.1    YES manual up      up  
GigabitEthernet0/0/1   209.165.200.225 YES manual up      up  
Vlan1                 unassigned      YES unset  down    down  
```  

---

## **4. Configuring the Default Gateway**  
### **On a Host:**  
- The **default gateway** is the router interface that connects the local network to external networks.  
- Example:  
  - **PC1 IP:** `192.168.10.10`  
  - **Router Interface (Default Gateway):** `192.168.10.1`  

### **On a Switch:**  
- A switch needs a default gateway for remote management.  
- **Command to configure default gateway:**  
  ```bash
  Switch(config)# ip default-gateway 192.168.10.1
  ```  
- **Example Configuration:**  
  ```bash
  S1(config)# ip default-gateway 192.168.10.1
  ```  

---

## **5. Summary of Key Concepts**  
- **Routers must be configured with a hostname, passwords, and security settings.**  
- **Interfaces must be assigned IP addresses and activated using `no shutdown`.**  
- **Verification commands (`show ip interface brief`, `show ipv6 route`) help check configurations.**  
- **A default gateway must be set for devices to communicate outside their local network.**  

---

**Module 11: IPv4 Addressing**

---

# **IPv4 Addressing **  

## **1. IPv4 Address Structure**  
- **IPv4 is a 32-bit hierarchical address** divided into:  
  - **Network Portion:** Identifies the network.  
  - **Host Portion:** Identifies the specific device.  
- **Subnet Mask:** Determines network and host portions.  
- **Prefix Length:** Represents subnet mask in slash notation (`/8`, `/16`, `/24`).  

### **Common Subnet Masks & Prefix Lengths**  
| **Subnet Mask** | **Binary Representation** | **Prefix Length** |
|---------------|-------------------------|----------------|
| 255.0.0.0 | `11111111.00000000.00000000.00000000` | `/8` |
| 255.255.0.0 | `11111111.11111111.00000000.00000000` | `/16` |
| 255.255.255.0 | `11111111.11111111.11111111.00000000` | `/24` |
| 255.255.255.128 | `11111111.11111111.11111111.10000000` | `/25` |
| 255.255.255.192 | `11111111.11111111.11111111.11000000` | `/26` |

### **Logical AND Operation**  
- Used to determine the **network address** by comparing the IPv4 address and subnet mask bit by bit.  
- **Example:**  
  ```bash
  IPv4 Address:  192.168.10.10 → 11000000.10101000.00001010.00001010  
  Subnet Mask:   255.255.255.0 → 11111111.11111111.11111111.00000000  
  Network Address: 192.168.10.0 → 11000000.10101000.00001010.00000000  
  ```

---

## **2. IPv4 Address Types**  
### **Unicast, Broadcast, and Multicast**  
- **Unicast:** One-to-one communication (e.g., PC to printer).  
- **Broadcast:** One-to-all communication (`255.255.255.255`).  
- **Multicast:** One-to-group communication (`224.0.0.0 - 239.255.255.255`).  

### **Public vs. Private IPv4 Addresses**  
- **Public:** Globally routable over the internet.  
- **Private (RFC 1918):** Used internally, not routable on the internet.  
  | **Private Address Range** | **Subnet Mask** |
  |--------------------------|---------------|
  | `10.0.0.0 - 10.255.255.255` | `/8` |
  | `172.16.0.0 - 172.31.255.255` | `/12` |
  | `192.168.0.0 - 192.168.255.255` | `/16` |

### **Special Use IPv4 Addresses**  
- **Loopback:** `127.0.0.1` (tests TCP/IP stack).  
- **Link-Local (APIPA):** `169.254.0.0/16` (self-assigned when DHCP fails).  

### **Network Address Translation (NAT)**  
- **Translates private IPs to public IPs** for internet access.  
- **Enabled on edge routers** connecting to ISPs.  

---

## **3. Network Segmentation & Subnetting**  
### **Broadcast Domains**  
- **Routers stop broadcasts**, creating separate broadcast domains.  
- **Subnetting reduces broadcast traffic** and improves performance.  

### **Subnetting Basics**  
- **Divides a large network into smaller subnets.**  
- **Subnetting a /24 network:**  
  | **Prefix Length** | **Subnet Mask** | **# of Subnets** | **# of Hosts** |
  |-----------------|---------------|------------|------------|
  | `/25` | `255.255.255.128` | 2 | 126 |
  | `/26` | `255.255.255.192` | 4 | 62 |
  | `/27` | `255.255.255.224` | 8 | 30 |
  | `/28` | `255.255.255.240` | 16 | 14 |
  | `/29` | `255.255.255.248` | 32 | 6 |
  | `/30` | `255.255.255.252` | 64 | 2 |

### **Subnetting a /16 and /8 Network**  
- **Used for large enterprises and ISPs.**  
- **Example:**  
  - `/17` → 2 subnets, 32,766 hosts each.  
  - `/18` → 4 subnets, 16,382 hosts each.  
  - `/19` → 8 subnets, 8,190 hosts each.  

---

## **4. Variable Length Subnet Masking (VLSM)**  
- **Allows subnetting within subnets** to optimize address usage.  
- **Example:**  
  - **LANs:** `/27` (30 hosts).  
  - **WAN Links:** `/30` (2 hosts).  
- **Reduces wasted addresses** compared to traditional subnetting.  

### **VLSM Example**  
| **Subnet** | **Subnet Mask** | **Hosts** |
|-----------|---------------|--------|
| Building A | `/27` | 25 |
| Building B | `/27` | 20 |
| Building C | `/27` | 15 |
| Building D | `/27` | 28 |
| WAN Links | `/30` | 2 |

---

## **5. Structured IPv4 Addressing Design**  
### **Planning Considerations:**  
- **Determine number of subnets and hosts per subnet.**  
- **Assign static IPs to servers and network devices.**  
- **Use DHCP for client devices.**  
- **Separate internal, DMZ, and external networks.**  

### **Device Address Assignment:**  
| **Device Type** | **Addressing Method** |
|---------------|----------------|
| **End User Clients** | DHCP (IPv4 or SLAAC for IPv6) |
| **Servers & Peripherals** | Static IPs |
| **Internet-Facing Servers** | Public IPs (via NAT) |
| **Routers & Firewalls** | Gateway addresses |

---

## **6. Key Terms & Commands**  
### **Important Concepts:**  
- **Prefix Length (`/24`, `/16`, `/8`).**  
- **Logical AND (used for network identification).**  
- **Network, Host, and Broadcast Addresses.**  
- **Unicast, Broadcast, and Multicast transmissions.**  
- **Private vs. Public IPv4 Addresses.**  
- **NAT (Network Address Translation).**  
- **Loopback & APIPA Addresses.**  
- **Classful Addressing (A, B, C, D, E).**  
- **Subnetting & VLSM.**  

### **Useful Commands:**  
| **Command** | **Description** |
|------------|---------------|
| `ipconfig` | Displays IP configuration (Windows). |
| `ifconfig` | Displays IP configuration (Linux/macOS). |
| `show ip interface brief` | Displays router interface status. |
| `show ip route` | Displays routing table. |
| `ping <IP>` | Tests connectivity. |
| `tracert <IP>` | Traces packet route (Windows). |
| `traceroute <IP>` | Traces packet route (Linux/macOS). |

---

**Module 12: IPv6 Addressing** 

---

# **IPv6 Addressing **  

## **1. IPv4 Issues & Need for IPv6**  
- **IPv4 exhaustion:** Limited address space due to increasing internet population and IoT.  
- **IPv6 provides:**  
  - **128-bit address space** (vastly more addresses).  
  - **Eliminates NAT** (direct end-to-end connectivity).  
  - **Improved security and efficiency.**  

### **IPv4 & IPv6 Coexistence**  
- **Dual Stack:** Devices run both IPv4 and IPv6 simultaneously.  
- **Tunneling:** Encapsulates IPv6 packets inside IPv4 packets for transport.  
- **Translation (NAT64):** Allows IPv6 devices to communicate with IPv4 devices.  

---

## **2. IPv6 Address Representation**  
- **128-bit addresses written in hexadecimal.**  
- **Preferred format:** `x:x:x:x:x:x:x:x` (each "x" is a 16-bit hextet).  
- **Not case-sensitive (uppercase or lowercase allowed).**  

### **IPv6 Address Shortening Rules**  
1. **Omit leading zeros:**  
   - `01ab → 1ab`, `09f0 → 9f0`, `00ab → ab`.  
2. **Use double colon (::) for consecutive zeros:**  
   - `2001:db8:0:0:0:0:0:1 → 2001:db8::1`.  
   - **Can only be used once in an address.**  

---

## **3. IPv6 Address Types**  
### **Unicast, Multicast, Anycast**  
- **Unicast:** One-to-one communication.  
- **Multicast:** One-to-many communication (`ff00::/8`).  
- **Anycast:** One-to-nearest communication (same address assigned to multiple devices).  
- **No Broadcast in IPv6!**  

### **IPv6 Prefix Length**  
- **Indicates network portion of an IPv6 address.**  
- **Common prefix length:** `/64` (recommended for most networks).  

### **IPv6 Unicast Address Types**  
| **Type** | **Description** |
|---------|---------------|
| **Global Unicast (GUA)** | Public, internet-routable (`2000::/3`). |
| **Link-Local (LLA)** | Required for every IPv6 device, used for local communication (`fe80::/10`). |
| **Unique Local (ULA)** | Private IPv6 addresses (`fc00::/7`). |
| **Loopback** | `::1/128` (tests TCP/IP stack). |
| **Unspecified** | `::/128` (used when no address is assigned). |

---

## **4. Configuring IPv6 Addresses**  
### **Static Configuration on a Router**  
```bash
Router(config)# interface gigabitEthernet 0/0/0  
Router(config-if)# ipv6 address 2001:db8:acad:1::1/64  
Router(config-if)# no shutdown  
Router(config-if)# exit  
```  

### **Static Configuration on a Windows Host**  
- **Manually set IPv6 address in network settings.**  
- **Use router’s LLA as the default gateway.**  

### **Configuring Link-Local Addresses (LLA)**  
```bash
Router(config)# interface gigabitEthernet 0/0/0  
Router(config-if)# ipv6 address fe80::1:1 link-local  
Router(config-if)# no shutdown  
Router(config-if)# exit  
```  

---

## **5. Dynamic IPv6 Addressing**  
### **Router Solicitation (RS) & Router Advertisement (RA) Messages**  
- **RS:** Sent by hosts to request IPv6 configuration.  
- **RA:** Sent by routers to provide IPv6 addressing options.  

### **IPv6 Address Assignment Methods**  
| **Method** | **Description** |
|-----------|---------------|
| **SLAAC (Stateless Address Autoconfiguration)** | Device configures itself using RA messages. |
| **SLAAC + Stateless DHCPv6** | SLAAC for IP, DHCPv6 for DNS & domain name. |
| **Stateful DHCPv6** | DHCPv6 assigns full configuration (like IPv4 DHCP). |

### **EUI-64 vs. Random Interface ID Generation**  
- **EUI-64:** Uses MAC address to generate interface ID.  
- **Random:** Windows and newer OS versions use random 64-bit numbers.  

---

## **6. IPv6 Multicast Addresses**  
- **Prefix:** `ff00::/8`.  
- **Two types:**  
  - **Well-Known Multicast:** Predefined groups (`ff02::1` for all nodes, `ff02::2` for all routers).  
  - **Solicited-Node Multicast:** Used for address resolution (similar to ARP).  

---

## **7. IPv6 Subnetting**  
### **Subnet ID Field**  
- **IPv6 subnetting uses a dedicated 16-bit subnet ID.**  
- **Example:**  
  - `2001:db8:acad::/48` → Allows **65,536 /64 subnets**.  
  - Subnets:  
    - `2001:db8:acad:0001::/64`  
    - `2001:db8:acad:0002::/64`  
    - `2001:db8:acad:0003::/64`  

### **Router Configuration with IPv6 Subnets**  
```bash
Router(config)# interface gigabitEthernet 0/0/0  
Router(config-if)# ipv6 address 2001:db8:acad:1::1/64  
Router(config-if)# no shutdown  
Router(config-if)# exit  

Router(config)# interface gigabitEthernet 0/0/1  
Router(config-if)# ipv6 address 2001:db8:acad:2::1/64  
Router(config-if)# no shutdown  
Router(config-if)# exit  
```  

---

## **8. Key Terms & Commands**  
### **Important Concepts:**  
- **IPv6 Address Shortening (`::`).**  
- **Global Unicast, Link-Local, Unique Local Addresses.**  
- **SLAAC, Stateful DHCPv6, Stateless DHCPv6.**  
- **EUI-64 vs. Random Interface ID.**  
- **IPv6 Subnetting using Subnet ID.**  

### **Useful Commands:**  
| **Command** | **Description** |
|------------|---------------|
| `show ipv6 interface brief` | Displays IPv6 addresses and interface status. |
| `show ipv6 route` | Displays IPv6 routing table. |
| `show ipv6 neighbors` | Displays IPv6 neighbor cache (similar to ARP). |
| `ping <IPv6>` | Tests IPv6 connectivity. |
| `traceroute <IPv6>` | Traces IPv6 packet route. |

---

**Module 13: ICMP**

---

# **ICMP **  

## **1. ICMP Overview**  
- **Internet Control Message Protocol (ICMP)** provides feedback about issues related to IP packet processing.  
- **ICMPv4** is used for IPv4, while **ICMPv6** is used for IPv6 (includes additional functionality).  
- **Common ICMP messages:**  
  - **Host Reachability:** Checks if a device is online.  
  - **Destination or Service Unreachable:** Indicates packet delivery failure.  
  - **Time Exceeded:** Sent when TTL (IPv4) or Hop Limit (IPv6) reaches zero.  

---

## **2. ICMP Messages**  
### **Host Reachability**  
- **ICMP Echo Request & Echo Reply** messages test connectivity.  
- **Example:**  
  - Host **H1** sends an **Echo Request** to **H2**.  
  - If **H2** is reachable, it responds with an **Echo Reply**.  

### **Destination or Service Unreachable**  
- **Sent when a packet cannot be delivered.**  
- **ICMPv4 Codes:**  
  - `0` - Network unreachable  
  - `1` - Host unreachable  
  - `2` - Protocol unreachable  
  - `3` - Port unreachable  
- **ICMPv6 Codes:**  
  - `0` - No route to destination  
  - `1` - Communication prohibited (e.g., firewall)  
  - `2` - Beyond scope of source address  
  - `3` - Address unreachable  
  - `4` - Port unreachable  

### **Time Exceeded**  
- **Occurs when TTL (IPv4) or Hop Limit (IPv6) reaches zero.**  
- **Used by traceroute to map network paths.**  

---

## **3. ICMPv6 Enhancements**  
- **ICMPv6 includes Neighbor Discovery Protocol (NDP).**  
- **New ICMPv6 messages:**  
  - **Router Solicitation (RS):** Sent by hosts to request IPv6 configuration.  
  - **Router Advertisement (RA):** Sent by routers every 200 seconds to provide IPv6 addressing details.  
  - **Neighbor Solicitation (NS):** Used for address resolution and duplicate address detection (DAD).  
  - **Neighbor Advertisement (NA):** Response to NS, providing MAC address information.  

### **IPv6 Address Configuration via RA Messages**  
- **RA messages include:**  
  - IPv6 prefix  
  - Prefix length  
  - DNS address  
  - Domain name  
- **Hosts using SLAAC set their default gateway to the router’s link-local address.**  

---

## **4. Ping & Traceroute**  
### **Ping - Test Connectivity**  
- **Uses ICMP Echo Request & Echo Reply messages.**  
- **Command Examples:**  
  - **IPv4:**  
    ```bash
    ping 192.168.20.2
    ```  
  - **IPv6:**  
    ```bash
    ping 2001:db8:acad:1::2
    ```  
- **Ping the loopback address to test local TCP/IP stack:**  
  - **IPv4:** `ping 127.0.0.1`  
  - **IPv6:** `ping ::1`  

### **Ping the Default Gateway**  
- **Tests local network connectivity.**  
- **Successful ping confirms host-router communication.**  

### **Ping a Remote Host**  
- **Tests internetwork connectivity.**  
- **No response may indicate security restrictions (firewall blocking ICMP).**  

### **Traceroute - Test the Path**  
- **Displays the route packets take to a destination.**  
- **Uses TTL (IPv4) or Hop Limit (IPv6) to incrementally map the path.**  
- **Command Examples:**  
  - **Windows:**  
    ```bash
    tracert 192.168.40.2
    ```  
  - **Linux/macOS:**  
    ```bash
    traceroute 192.168.40.2
    ```  

---

## **5. Key Terms & Commands**  
### **Important Concepts:**  
- **ICMPv4 & ICMPv6**  
- **Echo Request & Echo Reply**  
- **Destination Unreachable Codes**  
- **Time Exceeded Messages**  
- **Neighbor Discovery Protocol (NDP)**  
- **Router Solicitation (RS) & Router Advertisement (RA)**  
- **Neighbor Solicitation (NS) & Neighbor Advertisement (NA)**  
- **Ping & Traceroute**  

### **Useful Commands:**  
| **Command** | **Description** |
|------------|---------------|
| `ping <IP>` | Tests connectivity. |
| `ping ::1` | Tests IPv6 loopback. |
| `tracert <IP>` | Traces packet route (Windows). |
| `traceroute <IP>` | Traces packet route (Linux/macOS). |

---

**Module 14: Transport Layer**  

---

# **Transport Layer **  

## **1. Purpose of the Transport Layer**  
- **Manages end-to-end communication** between applications on different hosts.  
- **Links the application layer** to the lower layers responsible for network transmission.  
- **Key responsibilities:**  
  - **Tracking individual conversations** (multiple applications can communicate simultaneously).  
  - **Segmenting and reassembling data** for efficient transport.  
  - **Adding header information** for identification and reliability.  
  - **Multiplexing conversations** to allow multiple applications to share the network.  

---

## **2. Transport Layer Protocols: TCP vs. UDP**  
### **Transmission Control Protocol (TCP)**  
- **Reliable, connection-oriented protocol.**  
- **Features:**  
  - **Session establishment** (Three-Way Handshake).  
  - **Ensures reliable delivery** (acknowledges received data).  
  - **Same-order delivery** (reorders out-of-sequence packets).  
  - **Flow control** (adjusts data transmission rate).  
- **Used by:**  
  - **Web browsing (HTTP/HTTPS)**  
  - **Email (SMTP, IMAP, POP3)**  
  - **File transfers (FTP, SSH)**  

### **User Datagram Protocol (UDP)**  
- **Fast, connectionless protocol with minimal overhead.**  
- **Features:**  
  - **No session establishment** (sends data without prior connection).  
  - **No acknowledgments or retransmissions** (best-effort delivery).  
  - **Data is reconstructed in the order received** (no reordering).  
- **Used by:**  
  - **VoIP (IP telephony)**  
  - **DNS (Domain Name Resolution)**  
  - **DHCP (Dynamic Host Configuration Protocol)**  
  - **Live video streaming**  

---

## **3. Port Numbers & Sockets**  
- **Port numbers identify specific applications** running on a device.  
- **Source Port:** Assigned dynamically by the client.  
- **Destination Port:** Well-known or registered port assigned to the server.  
- **Socket Pair:** Combination of source IP, source port, destination IP, and destination port.  

### **Port Number Groups**  
| **Port Group** | **Range** | **Description** |
|--------------|---------|----------------|
| **Well-Known Ports** | `0 - 1023` | Reserved for common services (HTTP, FTP, SMTP). |
| **Registered Ports** | `1024 - 49151` | Assigned to specific applications (Cisco RADIUS uses 1812). |
| **Dynamic/Private Ports** | `49152 - 65535` | Assigned dynamically by the OS for temporary connections. |

### **Common Well-Known Ports**  
| **Port** | **Protocol** | **Application** |
|--------|-----------|--------------|
| `20` | TCP | FTP (Data) |
| `21` | TCP | FTP (Control) |
| `22` | TCP | SSH |
| `23` | TCP | Telnet |
| `25` | TCP | SMTP (Email) |
| `53` | UDP/TCP | DNS |
| `67` | UDP | DHCP (Server) |
| `68` | UDP | DHCP (Client) |
| `69` | UDP | TFTP |
| `80` | TCP | HTTP |
| `110` | TCP | POP3 (Email) |
| `143` | TCP | IMAP (Email) |
| `161` | UDP | SNMP |
| `443` | TCP | HTTPS |

### **Checking Active Connections**  
- **Windows:**  
  ```bash
  netstat -an
  ```  
- **Linux/macOS:**  
  ```bash
  netstat -tulnp
  ```  

---

## **4. TCP Communication Process**  
### **Three-Way Handshake (Session Establishment)**  
1. **Client sends SYN** (synchronization request).  
2. **Server responds with SYN-ACK** (acknowledgment).  
3. **Client sends ACK** (connection established).  

### **Session Termination**  
1. **Client sends FIN** (finish request).  
2. **Server acknowledges with ACK.**  
3. **Server sends FIN to close its side.**  
4. **Client acknowledges with ACK.**  

### **TCP Control Flags**  
| **Flag** | **Description** |
|--------|---------------|
| **URG** | Urgent data |
| **ACK** | Acknowledgment |
| **PSH** | Push function |
| **RST** | Reset connection |
| **SYN** | Synchronize sequence numbers |
| **FIN** | No more data (session termination) |

---

## **5. TCP Reliability & Flow Control**  
### **Reliable Delivery**  
- **Sequence numbers** ensure correct order.  
- **Acknowledgments (ACKs)** confirm receipt.  
- **Retransmissions** occur if data is lost.  

### **Selective Acknowledgment (SACK)**  
- **Allows receiver to acknowledge received segments** while requesting retransmission of missing ones.  

### **Flow Control (Sliding Window Protocol)**  
- **Window Size:** Defines how much data can be sent before requiring an acknowledgment.  
- **Adjusts transmission rate** based on network conditions.  

### **Maximum Segment Size (MSS)**  
- **Determines the largest chunk of data a device can receive.**  
- **Typical MSS:** `1460 bytes` (IPv4 MTU = 1500 bytes minus headers).  

### **Congestion Avoidance**  
- **Reduces transmission rate** when packet loss occurs.  
- **Uses timers and algorithms** to manage congestion.  

---

## **6. UDP Communication**  
### **Low Overhead vs. Reliability**  
- **No connection establishment** (faster than TCP).  
- **No sequence numbers or retransmissions.**  
- **Used for real-time applications** where speed is more important than reliability.  

### **UDP Datagram Reassembly**  
- **Datagrams may arrive out of order** (not reordered).  
- **Lost datagrams are not resent.**  

### **UDP Server & Client Processes**  
- **Servers listen on well-known ports** (e.g., DNS on `53`).  
- **Clients dynamically select source ports.**  

---

## **7. Key Terms & Commands**  
### **Important Concepts:**  
- **Conversation Multiplexing**  
- **Segments vs. Datagrams**  
- **Connection-Oriented vs. Connectionless Protocols**  
- **Flow Control & Same-Order Delivery**  
- **Socket Pairs & Port Numbers**  
- **Three-Way Handshake (SYN, ACK, FIN)**  
- **Selective Acknowledgment (SACK)**  
- **Sliding Window & MSS**  
- **Congestion Avoidance**  

### **Useful Commands:**  
| **Command** | **Description** |
|------------|---------------|
| `netstat -an` | Displays active connections (Windows). |
| `netstat -tulnp` | Displays active connections (Linux/macOS). |
| `ping <IP>` | Tests connectivity. |
| `tracert <IP>` | Traces packet route (Windows). |
| `traceroute <IP>` | Traces packet route (Linux/macOS). |

---

**Module 16: Network Security Fundamentals**  

---

# **Network Security Fundamentals **  

## **1. Security Threats and Vulnerabilities**  
### **Types of Threats**  
- **Threat actors** exploit vulnerabilities to gain unauthorized access.  
- **Common threats:**  
  - **Information Theft:** Stealing sensitive data.  
  - **Data Loss & Manipulation:** Altering or deleting data.  
  - **Identity Theft:** Impersonating users.  
  - **Disruption of Service:** Preventing legitimate access.  

### **Types of Vulnerabilities**  
- **Technological Vulnerabilities:**  
  - Weaknesses in TCP/IP protocols, OS flaws, network equipment issues.  
- **Configuration Vulnerabilities:**  
  - Weak passwords, misconfigured services, default settings.  
- **Security Policy Vulnerabilities:**  
  - Lack of security policies, poor access controls, no disaster recovery plan.  

### **Physical Security Threats**  
- **Hardware Threats:** Damage to routers, switches, servers.  
- **Environmental Threats:** Extreme temperature/humidity.  
- **Electrical Threats:** Power surges, outages.  
- **Maintenance Threats:** Poor handling of equipment, lack of spare parts.  

---

## **2. Network Attacks**  
### **Types of Malware**  
- **Viruses:** Attach to files and spread when executed.  
- **Worms:** Self-replicating, spread without user interaction.  
- **Trojan Horses:** Disguised as legitimate software, require user action to spread.  

### **Types of Network Attacks**  
- **Reconnaissance Attacks:**  
  - Scanning networks for vulnerabilities using tools like `nslookup` and `whois`.  
- **Access Attacks:**  
  - **Password Attacks:** Brute force, Trojan horses, packet sniffers.  
  - **Trust Exploitation:** Using unauthorized privileges.  
  - **Port Redirection:** Using compromised systems to attack others.  
  - **Man-in-the-Middle:** Intercepting communication between two parties.  
- **Denial of Service (DoS) Attacks:**  
  - Overloading network resources to disrupt service.  
  - **Distributed DoS (DDoS):** Uses botnets (infected hosts) to amplify attacks.  

---

## **3. Network Attack Mitigation**  
### **Defense-in-Depth Approach**  
- **Layered security strategy using multiple devices and services:**  
  - **VPN:** Secure remote access.  
  - **ASA Firewall:** Blocks unauthorized traffic.  
  - **IPS (Intrusion Prevention System):** Detects and prevents attacks.  
  - **ESA/WSA:** Email and web security appliances.  
  - **AAA Server:** Manages authentication, authorization, and accounting.  

### **Backup Strategies**  
- **Regular backups** prevent data loss.  
- **Store backups offsite** for disaster recovery.  
- **Validate backups** to ensure integrity.  

### **Upgrade, Update, and Patch**  
- **Keep antivirus software updated.**  
- **Apply security patches to OS and applications.**  
- **Enable automatic updates for critical systems.**  

### **Authentication, Authorization, and Accounting (AAA)**  
- **Authentication:** Verifies user identity.  
- **Authorization:** Defines user permissions.  
- **Accounting:** Logs user activities.  

### **Firewalls**  
- **Control traffic between networks, prevent unauthorized access.**  
- **Types of firewalls:**  
  - **Packet Filtering:** Blocks traffic based on IP/MAC addresses.  
  - **Application Filtering:** Blocks traffic based on application type.  
  - **URL Filtering:** Blocks access to specific websites.  
  - **Stateful Packet Inspection (SPI):** Blocks unsolicited packets.  

### **Endpoint Security**  
- **Securing individual devices (laptops, desktops, smartphones).**  
- **Use antivirus software, host intrusion prevention, and network access control.**  

---

## **4. Device Security**  
### **Cisco AutoSecure**  
- **Automates security configurations on Cisco routers.**  
- **Best practices:**  
  - Change default usernames/passwords.  
  - Restrict access to system resources.  
  - Disable unnecessary services.  
  - Apply security patches before deployment.  

### **Strong Password Guidelines**  
- **Use at least 8-10 characters.**  
- **Include uppercase, lowercase, numbers, symbols.**  
- **Avoid common words, names, birthdates.**  
- **Use passphrases (e.g., `Secure!MyNetwork2023`).**  
- **Change passwords regularly.**  

### **Additional Password Security**  
- **Encrypt passwords:**  
  ```bash
  Router(config)# service password-encryption
  ```  
- **Set minimum password length:**  
  ```bash
  Router(config)# security passwords min-length 8
  ```  
- **Block brute-force attacks:**  
  ```bash
  Router(config)# login block-for 120 attempts 3 within 60
  ```  
- **Set session timeout:**  
  ```bash
  Router(config-line)# exec-timeout 5 30
  ```  

---

## **5. Secure Remote Access**  
### **Telnet vs. SSH**  
- **Telnet (TCP port 23):** Unsecure, transmits credentials in plaintext.  
- **SSH (TCP port 22):** Secure, encrypts authentication and data.  

### **Configuring SSH on Cisco Devices**  
1. **Set hostname:**  
   ```bash
   Router(config)# hostname R1
   ```  
2. **Set domain name:**  
   ```bash
   Router(config)# ip domain-name example.com
   ```  
3. **Generate RSA keys:**  
   ```bash
   Router(config)# crypto key generate rsa modulus 1024
   ```  
4. **Create local user:**  
   ```bash
   Router(config)# username admin secret strongpassword
   ```  
5. **Enable SSH on vty lines:**  
   ```bash
   Router(config-line)# line vty 0 4
   Router(config-line)# transport input ssh
   Router(config-line)# login local
   ```  
6. **Enable SSH version 2:**  
   ```bash
   Router(config)# ip ssh version 2
   ```  

---

## **6. Disable Unused Services**  
- **Unused services consume resources and create security risks.**  
- **Check open ports:**  
  ```bash
  Router# show ip ports all
  ```  
- **Disable unnecessary services:**  
  ```bash
  Router(config)# no ip http server
  Router(config)# no ip bootp server
  ```  

---

## **7. Key Terms & Commands**  
### **Important Concepts:**  
- **Threat Actor**  
- **Malware (Viruses, Worms, Trojans)**  
- **Reconnaissance, Access, and Denial-of-Service Attacks**  
- **Defense-in-Depth Security Strategy**  
- **AAA (Authentication, Authorization, Accounting)**  
- **Firewalls (Packet Filtering, SPI, URL Filtering)**  
- **Cisco AutoSecure**  
- **Passphrase vs. Password**  

### **Useful Commands:**  
| **Command** | **Description** |
|------------|---------------|
| `service password-encryption` | Encrypts plaintext passwords. |
| `security passwords min-length 8` | Sets minimum password length. |
| `login block-for 120 attempts 3 within 60` | Blocks brute-force login attempts. |
| `exec-timeout 5 30` | Sets session timeout. |
| `crypto key generate rsa modulus 1024` | Generates RSA keys for SSH. |
| `transport input ssh` | Enables SSH access. |
| `show ip ports all` | Displays open ports. |

---

**Module 17: Build a Small Network**   

---

# **Build a Small Network **  

## **1. Devices in a Small Network**  
### **Small Network Topologies**  
- **Small businesses often use simple network designs.**  
- **Typically have a single WAN connection** (DSL, cable, or Ethernet).  
- **Managed by local IT technicians** or contracted professionals.  

### **Device Selection Considerations**  
- **Cost:** Budget constraints.  
- **Speed & Interfaces:** Ensure compatibility with network requirements.  
- **Expandability:** Ability to scale as the business grows.  
- **Operating System Features:** Security, management, and automation capabilities.  

### **IP Addressing in Small Networks**  
- **Plan and document an IP addressing scheme.**  
- **Assign unique addresses to:**  
  - End-user devices (wired/wireless).  
  - Servers and peripherals (printers, cameras).  
  - Intermediary devices (switches, access points).  

### **Redundancy in Small Networks**  
- **Eliminates single points of failure.**  
- **Redundant components:**  
  - Backup servers.  
  - Alternate network links.  
  - Spare switches and routers.  

### **Traffic Management & QoS**  
- **Prioritize real-time traffic (voice, video).**  
- **Quality of Service (QoS) ensures efficient bandwidth usage.**  
- **Priority queuing:**  
  - **High Priority:** Voice traffic.  
  - **Medium Priority:** Email (SMTP).  
  - **Normal Priority:** Instant messaging.  
  - **Low Priority:** FTP transfers.  

---

## **2. Small Network Applications & Protocols**  
### **Common Applications**  
- **Network Applications:** Directly interact with network protocols.  
- **Application Layer Services:** Prepare data for network transmission.  

### **Common Protocols**  
| **Protocol** | **Purpose** |
|------------|------------|
| **HTTP/HTTPS** | Web browsing |
| **SMTP, POP3, IMAP** | Email communication |
| **FTP/SFTP** | File transfers |
| **DHCP** | Automatic IP configuration |
| **DNS** | Resolves domain names to IP addresses |
| **Telnet/SSH** | Remote device access |

### **Voice & Video Applications**  
- **VoIP:** Cost-effective but lower quality.  
- **IP Telephony:** Uses dedicated servers for call control.  
- **Real-Time Transport Protocol (RTP) & RTCP:** Support real-time applications.  

---

## **3. Scaling a Small Network**  
### **Network Growth Considerations**  
- **Network Documentation:** Physical and logical topology.  
- **Device Inventory:** List of all network devices.  
- **Budget Planning:** IT expenses and future upgrades.  
- **Traffic Analysis:** Identifies bandwidth requirements.  

### **Protocol Analysis**  
- **Capture traffic during peak hours** to analyze network usage.  
- **Use protocol analyzers** to evaluate traffic patterns.  

### **Employee Network Utilization**  
- **Monitor system performance:**  
  - OS version, CPU/RAM usage, drive utilization.  
  - Network and non-network applications.  

---

## **4. Verifying Connectivity**  
### **Ping Command**  
- **Tests Layer 3 connectivity using ICMP Echo Requests.**  
- **Windows:**  
  ```bash
  ping 192.168.1.1
  ```  
- **Cisco IOS:**  
  ```bash
  ping 192.168.1.1
  ```  
- **Ping Indicators:**  
  - `!` → Successful reply.  
  - `.` → Timeout (connectivity issue).  
  - `U` → Destination unreachable.  

### **Traceroute Command**  
- **Identifies network path and problem areas.**  
- **Windows:**  
  ```bash
  tracert 192.168.1.1
  ```  
- **Cisco IOS:**  
  ```bash
  traceroute 192.168.1.1
  ```  
- **Timeouts (`*`) indicate network issues.**  

### **Extended Ping & Traceroute**  
- **Cisco IOS allows advanced ping/traceroute customization.**  
- **Example:**  
  ```bash
  R1# ping  
  Target IP address: 192.168.1.1  
  Repeat count [5]: 10  
  Timeout in seconds [2]: 3  
  ```  

---

## **5. Host & IOS Commands**  
### **IP Configuration Commands**  
| **Command** | **Description** |
|------------|---------------|
| `ipconfig` | Displays IP settings (Windows). |
| `ifconfig` | Displays IP settings (Linux/macOS). |
| `ip address show` | Displays IP addresses (Linux). |
| `networksetup -getinfo Wi-Fi` | Displays IP settings (macOS). |

### **ARP Commands**  
| **Command** | **Description** |
|------------|---------------|
| `arp -a` | Displays ARP cache. |
| `netsh interface ip delete arpcache` | Clears ARP cache (Windows). |

### **Common Cisco IOS Commands**  
| **Command** | **Description** |
|------------|---------------|
| `show running-config` | Displays current configuration. |
| `show interfaces` | Displays interface status. |
| `show ip interface brief` | Summarizes interface details. |
| `show ip route` | Displays routing table. |
| `show arp` | Displays ARP table. |
| `show cdp neighbors` | Displays connected Cisco devices. |

---

## **6. Troubleshooting Methodologies**  
### **Basic Troubleshooting Steps**  
1. **Identify the Problem:** Gather user feedback and symptoms.  
2. **Establish a Theory:** Determine possible causes.  
3. **Test the Theory:** Apply fixes and verify results.  
4. **Implement a Solution:** Apply corrective actions.  
5. **Verify & Prevent:** Ensure functionality and prevent recurrence.  
6. **Document Findings:** Record troubleshooting steps for future reference.  

### **Resolve or Escalate?**  
- **Escalate issues requiring:**  
  - Manager approval.  
  - Specialized expertise.  
  - Higher network access privileges.  

### **Debugging Commands**  
- **Displays real-time system messages.**  
- **Enable debugging:**  
  ```bash
  debug ip icmp
  ```  
- **Disable debugging:**  
  ```bash
  no debug ip icmp
  undebug all
  ```  

### **Terminal Monitor Command**  
- **Displays log messages on remote sessions.**  
- **Enable:**  
  ```bash
  terminal monitor
  ```  
- **Disable:**  
  ```bash
  terminal no monitor
  ```  

---

## **7. Troubleshooting Scenarios**  
### **Common Issues & Solutions**  
| **Issue** | **Solution** |
|----------|------------|
| **Duplex Mismatch** | Ensure both devices use full-duplex. |
| **Incorrect IP Address** | Verify with `show ip interface brief`. |
| **APIPA Address (169.254.x.x)** | Check DHCP server availability. |
| **Default Gateway Issues** | Verify with `ipconfig` or `show ip route`. |
| **DNS Issues** | Use `nslookup` to test DNS resolution. |

---

## **8. Key Terms & Commands**  
### **Important Concepts:**  
- **Network Applications vs. Application Layer Services**  
- **Extended Ping & Traceroute**  
- **Network Baseline**  
- **Debugging & Terminal Monitor**  
- **Scientific Troubleshooting Method**  

### **Useful Commands:**  
| **Command** | **Description** |
|------------|---------------|
| `ping <IP>` | Tests connectivity. |
| `tracert <IP>` | Traces packet route (Windows). |
| `traceroute <IP>` | Traces packet route (Linux/macOS). |
| `show ip interface brief` | Displays interface summary. |
| `show ip route` | Displays routing table. |

---
