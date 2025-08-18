---
date: 2025-08-17
course: CSM 478 - Computer Networks
tags:
  - personal
  - study
  - CSM478
---
## **The OSI Model**

The **OSI (Open Systems Interconnection) Model** is a conceptual framework that describes how network hardware and software work together. It helps different systems communicate by breaking down the complex process into smaller, manageable layers. This makes it easier to understand, design, and troubleshoot networks.

Here's a quick look at each layer, from bottom to top:

- **Layer 1: Physical Layer**: This is the very bottom layer, dealing with the physical connection. It's all about transmitting raw bits of data over cables (like twisted pair, coaxial, fiber optic) or wireless signals. Devices here include hubs and repeaters.
    
- **Layer 2: Data Link Layer**: This layer handles frames of data and ensures error-free transmission between directly connected devices. It uses MAC addresses for addressing and manages access to the physical medium. Switches and bridges operate at this layer. Protocols include Ethernet, Wi-Fi, PPP, and Frame Relay.
    
- **Layer 3: Network Layer**: This is where routing happens! It deals with logical addressing (IP addresses) and determines the best path for data packets across different networks. Routers and Layer 3 switches work here. Key protocols are IP, ICMP (for error messages), and ARP (for resolving IP to MAC addresses).
    
- **Layer 4: Transport Layer**: This layer provides end-to-end communication between applications. It segments data into smaller pieces for transmission and reassembles them at the destination. It also handles flow control and error recovery. The two main protocols here are TCP (reliable, connection-oriented) and UDP (unreliable, connectionless).
    
- **Layer 5: Session Layer**: This layer establishes, manages, and terminates communication sessions between applications. Think of it as setting up a conversation, keeping it going, and then ending it politely.
    
- **Layer 6: Presentation Layer**: This layer is responsible for data format conversion, encryption, and compression. It ensures that data is presented in a format that the application layer can understand.
    
- **Layer 7: Application Layer**: This is the top layer, closest to the end-user. It provides network services directly to applications. Examples of protocols at this layer include HTTP (for web browsing), FTP (for file transfer), SMTP (for email), and DNS (for translating domain names to IP addresses).


A popular way to remember the order of the seven layers, from top to bottom, is with a sentence where each word starts with the first letter of a layer.

Here's a common one:

==**A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing==

Let's break down what each word stands for:

- **A**pplication Layer
- **P**resentation Layer
- **S**ession Layer
- **T**ransport Layer
- **N**etwork Layer
- **D**ata Link Layer
- **P**hysical Layer


## **TCP/IP Protocol Suite**

The **TCP/IP Protocol Suite** is a collection of communication protocols used for internetworking. It's often seen as a more practical, four-layer model, though it maps closely to the OSI model.

Let's look at some key protocols within this suite:

- **HTTP (Hypertext Transfer Protocol)** and **HTTPS (HTTP Secure)**: These are used for web browsing. HTTP uses port 80, while HTTPS, which is secure, uses port 443. They define how web servers and browsers communicate, including methods like GET (to request data) and POST (to send data).
    
- **DNS (Domain Name System)**: This is like the internet's phonebook. It translates human-friendly domain names (like 'google.com') into numerical IP addresses that computers understand. DNS typically uses port 53 (UDP for queries, TCP for zone transfers). It has different record types, such as 'A' for IPv4 addresses and 'AAAA' for IPv6 addresses.
    
- **DHCP (Dynamic Host Configuration Protocol)**: Imagine having to manually set an IP address for every new device on a network – that would be a lot of work! DHCP automates this process, dynamically assigning IP addresses, subnet masks, default gateways, and DNS server information to devices. DHCP servers use port 67, and clients use port 68.
    
- **FTP (File Transfer Protocol)**: This protocol is used for transferring files between computers on a network. It uses two ports: port 21 for control commands (like logging in) and port 20 for data transfer. FTP can operate in active or passive modes.
    
- **ARP (Address Resolution Protocol)**: This protocol works at the network layer to resolve IP addresses to MAC addresses. When a device knows the IP address of another device but needs its MAC address to send a frame on the local network, it sends an ARP Request (a broadcast message). The target device then sends an ARP Reply (a unicast message) with its MAC address. Devices store these mappings in an ARP table.
    
- **ICMP (Internet Control Message Protocol)**: This protocol is used for error reporting and network diagnostics. For example, when you use the 'ping' command to check connectivity, it sends ICMP Echo Request messages and expects ICMP Echo Reply messages back. Other ICMP messages include 'Destination Unreachable' and 'Time Exceeded'.

## **Data Flow (Transmission Modes)***

This describes the direction in which data can travel between two devices:

- **Simplex**: Data flows in only one direction, like a one-way street. Think of a traditional radio broadcast or a keyboard sending input to a computer. The receiver cannot send a reply.
    
- **Half-Duplex**: Data can flow in both directions, but only one direction at a time. It's like a walkie-talkie where only one person can talk at a time. Both devices can send and receive, but not simultaneously.
    
- **Full-Duplex**: Data can flow in both directions simultaneously, like a two-way street with traffic flowing in both directions at the same time. This is common in modern networks, allowing devices to send and receive data at the same time, significantly increasing efficiency.

## **Data Transmission Characteristics**:

- **Bandwidth**: This refers to the maximum rate at which data can be transmitted over a communication medium. It's often measured in bits per second (bps), kilobits per second (Kbps), megabits per second (Mbps), or gigabits per second (Gbps). Higher bandwidth means more data can be sent in a given amount of time.
    
- **Analog vs. Digital Signals**: Data can be transmitted as either analog or digital signals. Analog transmission uses continuous waves, like sound waves or traditional telephone signals. Digital transmission, on the other hand, sends data in the form of discrete bits (0s and 1s), which is what computers primarily use.
    
- **Serial vs. Parallel Transmission**: This describes how bits are sent:
    
    - **Serial Transmission**: All data bits are transmitted one bit after another in a continuous line. This is common for long-distance communication because it requires fewer wires and reduces synchronization issues.
    - **Parallel Transmission**: Data bits are sent at the same time along multiple paths or wires. This is faster for short distances but can be more complex and expensive due to the need for more wires and careful synchronization.

Finally, let's touch on addressing types:

- **MAC Broadcast Address**: This is a special Layer 2 address (FF:FF:FF:FF:FF:FF) that forces all devices on a local area network (LAN) to process the frame. It's used for things like ARP requests and DHCP discovery.
    
- **Multicast**: This is a one-to-many communication method where a single stream of data is sent to a specific group of recipients. It's efficient for things like video streaming or routing protocol updates. IPv4 multicast addresses fall within the 224.0.0.0 to 239.255.255.255 range (Class D).
    
- **Unicast**: This is a one-to-one communication, where data is sent from a single source to a single destination. Most common network traffic, like web browsing or email, uses unicast.

## **Network Segmentation**

As networks grow, especially those using hubs, performance can suffer due to too much traffic. This is because hubs create a single **collision domain** where all connected devices compete to send data, leading to frequent collisions. They also create a single **broadcast domain**, meaning all devices hear every broadcast message, which can cause 'broadcast storms' and overwhelm the network.

**Network Segmentation** is the process of dividing a large network into smaller, more manageable segments. This helps to:

- Reduce broadcast traffic.
- Improve network security by isolating sensitive data.
- Enhance overall network performance.
- Simplify network management.

Different devices segment networks in different ways:

- **Hubs**: As we learned, hubs do NOT segment a network. They connect hosts within a single network segment, meaning all ports share one collision domain and one broadcast domain.
    
- **Switches**: Switches are much better for segmentation! Each port on a switch creates a separate **collision domain**. This means devices connected to different switch ports won't experience collisions with each other. However, by default, a Layer 2 switch still keeps all connected devices within a single **broadcast domain**. This means broadcast messages still reach all devices connected to the switch.
    
- **Routers**: Routers are the ultimate segmenters! By default, each interface on a router creates a separate **broadcast domain** AND a separate **collision domain**. This is why routers are used to connect different networks (or subnets) together, as they stop broadcasts from flooding across the entire internetwork.
    

**Broadcast Storm Prevention** is crucial for network health. Solutions include:

- **Spanning Tree Protocol (STP)**: This protocol prevents switching loops, which can cause broadcast storms, by intelligently blocking redundant paths.
- **Broadcast Storm Control** and **Rate Limiting**: These features on switches can limit the amount of broadcast traffic allowed on a port.
- **VLAN Segmentation**: As we'll see in the next chapter, Virtual Local Area Networks (VLANs) allow you to logically separate devices into different broadcast domains, even if they are on the same physical switch.


## **VLANs - Virtual Local Area Networks**

Imagine a single physical switch, but you want to treat different groups of devices connected to it as if they are on completely separate networks. That's exactly what VLANs allow you to do! They provide **logical segmentation** of a physical network.

Here are the amazing benefits of implementing VLANs:

- **Broadcast Domain Separation**: This is a huge one! Each VLAN creates its own separate broadcast domain. This means broadcast messages sent within one VLAN will not be forwarded to other VLANs, significantly reducing broadcast traffic and preventing broadcast storms from affecting the entire physical network.
- **Security Isolation**: By separating sensitive data traffic into its own VLAN, you can enhance network security. Devices in one VLAN cannot directly communicate with devices in another VLAN without a Layer 3 device (like a router).
- **Traffic Management**: VLANs help manage traffic flow more efficiently by confining traffic to specific logical groups.
- **Simplified Administration**: VLANs make it easier for IT staff to configure new logical groups and manage moves, adds, and changes of hosts on the network, as physical location becomes less important than logical grouping.

To make VLANs work across multiple switches or between a switch and a router, we use **VLAN Tagging**. The most common standard for this is **IEEE 802.1Q**. When frames travel between switches or to a router, a special tag is added to the frame to identify which VLAN it belongs to. This allows multiple VLANs to share a single physical link.

There are two main types of ports when dealing with VLANs:

- **Access Ports**: These ports belong to a single VLAN and are typically used to connect end-user devices like computers or printers. Frames sent from an access port are usually untagged.
- **Trunk Ports**: These ports are configured to carry traffic for multiple VLANs between switches or between a switch and a router. They use 802.1Q tagging to identify which VLAN each frame belongs to.

What if devices in different VLANs need to communicate? This is where **Inter-VLAN Routing** comes in. Since VLANs create separate broadcast domains (like separate networks), a Layer 3 device (a router or a Layer 3 switch) is needed to route traffic between them. A common setup is 'router-on-a-stick', where a single router interface is configured with multiple sub-interfaces, each acting as the default gateway for a different VLAN.

## **Trunking & EtherChannel**

**Trunking** is the process of carrying traffic for multiple VLANs over a single physical link. Instead of needing a separate cable for each VLAN between switches, a trunk link allows all VLAN traffic to flow over one connection. The two main link protocols used for this are:

- **IEEE 802.1Q**: This is the industry-standard trunking protocol. It inserts a small tag (4 bytes) into the Ethernet frame header to identify the VLAN ID. Frames belonging to the 'native VLAN' are typically sent untagged by default. If there's a native VLAN mismatch between two trunk ports, it can cause communication issues.
- **ISL (Inter-Switch Link)**: This is a Cisco-proprietary trunking protocol. Instead of tagging, it encapsulates the entire Ethernet frame with an ISL header and trailer. ISL is older and less common now, with 802.1Q being preferred.

When configuring trunk ports, you can set different **trunking modes** to control how the port behaves:

- **On**: The port is permanently in trunking mode.
- **Auto**: The port becomes a trunk if the neighboring port is set to 'desirable' or 'on'.
- **Desirable**: The port actively attempts to become a trunk. It will become a trunk if the neighboring port is 'on', 'auto', or 'desirable'.
- **Passive**: The port becomes a trunk only if the neighboring port is 'desirable' or 'on'.

Now, let's talk about **EtherChannel**. Imagine you have multiple physical links between two switches, but you want them to act as one logical link to increase bandwidth and provide redundancy. That's what EtherChannel does!

**EtherChannel** bundles multiple physical Ethernet links into a single logical link. This provides several benefits:

- **Increased Bandwidth**: The total bandwidth of the bundled links is combined.
- **Load Balancing**: Traffic is distributed across the physical links within the EtherChannel.
- **Redundancy**: If one physical link in the bundle fails, traffic is automatically redistributed over the remaining active links, without causing a topology change that Spanning Tree Protocol (STP) would need to react to.

EtherChannel can be configured using different protocols:

- **PAgP (Port Aggregation Protocol)**: A Cisco-proprietary protocol for EtherChannel negotiation.
- **LACP (Link Aggregation Control Protocol)**: An open-standard protocol (IEEE 802.3ad) for EtherChannel negotiation.

When configuring a Layer 3 EtherChannel, the IP address is configured on the logical **port-channel interface**, not on the individual physical interfaces. This simplifies management and ensures consistent routing behavior.
































## **Key Concepts**

- The OSI Model has seven layers, each with a specific function.
- It helps standardize network communication.
- Each layer builds upon the services of the layer below it.
- Understanding the layers helps in network design and troubleshooting.
- TCP/IP is the foundational protocol suite for the internet.
- HTTP/HTTPS are for web communication.
- DNS translates domain names to IP addresses.
- DHCP automates IP address assignment.
- FTP handles file transfers.
- ARP resolves IP addresses to MAC addresses.
- ICMP is used for network diagnostics and error reporting.
- Transmission modes define data flow: Simplex (one-way), Half-Duplex (two-way, one at a time), Full-Duplex (two-way, simultaneous).
- Bandwidth is the maximum data transfer rate.
- Data can be Analog (continuous waves) or Digital (discrete bits).
- Bits can be sent Serially (one by one) or in Parallel (multiple at once).
- Broadcast, Multicast, and Unicast are different ways to address recipients.
- Network segmentation divides large networks to improve performance and security.
- Hubs create one collision and one broadcast domain.
- Switches create separate collision domains per port but one broadcast domain by default.
- Routers create separate collision and broadcast domains per interface.
- Broadcast storms can be prevented using STP, rate limiting, and VLANs.
- VLANs logically segment a physical network.
- They create separate broadcast domains, improving security and reducing traffic.
- 802.1Q is the standard for VLAN tagging on trunk links.
- Access ports are for single VLANs (end devices), trunk ports carry multiple VLANs.
- Inter-VLAN routing requires a Layer 3 device to enable communication between different VLANs.
- Trunking allows multiple VLANs over a single link using 802.1Q (standard) or ISL (Cisco proprietary).
- Trunking modes (on, auto, desirable, passive) control negotiation.
- EtherChannel bundles multiple physical links into one logical link for increased bandwidth and redundancy.
- EtherChannel uses PAgP (Cisco) or LACP (open standard).
- For Layer 3 EtherChannel, IP addresses are configured on the logical port-channel interface.