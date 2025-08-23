---
date: 2025-08-23
course: CSM 494 - Computer Security
tags:
  - personal
  - study
  - CSM494
---
## What are Sniffers? 🧐

A **sniffer**, also known as a **packet sniffer**, is a software application designed to monitor, filter, and capture data packets as they travel across a network1. These tools can be run from almost any computer and are notoriously difficult to detect while in operation2.

The main objectives of this chapter are to:

- Identify different types and examples of sniffers3.
    
- Understand how sniffers work and what their functions are4.
    
- Learn how to detect sniffers on a network5.
    
- Discover the best methods to protect a network from sniffing attacks6.
    

There are three main categories of sniffers7:

1. **Bundled**: These sniffers are included with an operating system88.
    
2. **Commercial**: These are sold by companies and often come with support9999.
    
3. **Free**: These are available at no cost but typically have minimal support10101010.
    

---

## How Sniffers Work

A sniffer operates by capturing the data that passes through the

**Network Interface Adapter (NIC)** of the computer it's running on11. This means it can only see traffic from the local network segment it's connected to12. To capture all traffic and not just traffic addressed to it, a sniffer places the NIC into

**promiscuous mode**13.

### Key Components of a Sniffer

- **Capture Driver**: This is the software that communicates directly with the NIC to capture the data packets14.
    
- **Buffer**: This is a temporary storage area for captured packets. Data can be stored until the buffer is full or by using a
    
    **round-robin method**, where older data is overwritten by new data15.
    
- **Decoder**: This component interprets the raw binary data from the packets and displays it in a human-readable format16.
    
- **Packet Analysis**: Most sniffers provide real-time analysis of the packets they capture, allowing for immediate review of the network traffic17.
    

### Where to Place a Sniffer

A sniffer is most effective when strategically placed in a location where it can capture the most relevant data18. Common placements include computers, routers, cable connections, and network segments that are connected to the internet or to servers that handle sensitive information like passwords19.

---

## Catalog of Sniffer Programs 🧰

There are numerous sniffer programs, each with different features and platforms.

### Free & Bundled Sniffers

- **Wireshark (formerly Ethereal)**: Considered the most powerful free network protocol analyzer, Wireshark works on UNIX/Linux and Windows20. It captures live network data from various interfaces like Ethernet, PPP, and more21.
    
- **Tcpdump/Windump**: This is a widely used command-line tool that comes bundled with most Linux distributions (`tcpdump`) and is available for Windows (`windump`)22. It can decode and monitor headers from IP, TCP, UDP, and ICMP packets23.
    
- **Snort**: A highly versatile tool that can function as a packet sniffer, packet logger, or a full Network Intrusion Detection System (NIDS)24. It can perform real-time traffic analysis and detect various attacks, such as buffer overflows25. It runs on multiple platforms including Linux, Solaris, and Windows26.
    
- **Network Monitor**: This sniffer is bundled with Microsoft Windows Server operating systems (NT, 2000, 2003)27. It is known for its advanced filtering, support for many protocols, and ability to monitor high-speed and wireless networks28.
    

### Commercial Sniffers

Commercial sniffers are used by companies for network monitoring and analysis. They are typically used for29:

- **Fault analysis**: Detecting network problems30.
    
- **Performance analysis**: Finding network bottlenecks31.
    
- **Sniffer Pro**: A commercial tool from Network Associates, Inc. that has an easy-to-use interface for capturing traffic, including usernames and passwords32.
    
- **EtherPeek NX and Fluke Networks Protocol Analyzers** are also mentioned as commercial options33.
    

### Antiquated Sniffers

Some older tools, now mainly of historical interest, include

**Gobbler**, **Ethload**, **Sunsniff**, and **Linux_sniffer**34343434.

---

## Detecting Sniffers on a Network 🕵️‍♀️

Because sniffers are passive tools, they are difficult to detect35. Detection methods focus on identifying if a machine's NIC is in

**promiscuous mode**36.

### Detection Methods

- **Ping Test**: This test, performed with a tool like **AntiSniff**, sends a packet to a host with a correct IP address but a fake MAC address. A normal host will ignore it, but a host in promiscuous mode will respond, revealing its presence37.
    
- **ARP Test**: This method sends a packet with the target's IP address but a special MAC address (e.g., `ff:00:00:00:00:00`). A Windows machine in promiscuous mode will mistakenly process and respond to this packet38.
    
- **DNS Test**: Some sniffers perform reverse DNS lookups to convert IP addresses to hostnames in their logs. This activity can be monitored to detect a potential sniffer39.
    
- **Decoy Method**: This involves setting up a fake server with dummy user accounts and having a client log in. An attacker sniffing the network may capture these credentials and attempt to use them, which would be logged by the server40.
    
- **Time Domain Reflectometers (TDR)**: This hardware-based method sends an electrical pulse down a network cable to detect physical taps or unauthorized hardware sniffers41.
    

---

## How to Protect Against Sniffers 🛡️

The most effective defense against sniffing is to make the captured data unusable through

**encryption**42424242.

### Key Protection Technologies

- **Secure Sockets Layer (SSL)**: A standard security protocol built into all web browsers and servers that provides data encryption and authentication for TCP/IP connections43. It comes in 40-bit and 128-bit versions44.
    
- **Pretty Good Privacy (PGP) and S/MIME**: These are methods used to secure e-mail messages with privacy and authentication, as e-mail can be easily sniffed45.
    
- **Secure Shell (SSH)**: A secure alternative to Telnet that protects against IP spoofing, DNS spoofing, man-in-the-middle attacks, and the interception of cleartext passwords46.
    
- **Additional Protections**:
    
    - At
        
        **Layer 2**, you can enable port security on network switches and use static ARP tables47.
        
    - At
        
        **Layer 3**, you can use **IPSEC** along with DNSSEC for secure name resolution48.
        
    - Be aware that
        
        **firewalls** can be a double-edged sword, as sniffers are highly effective _behind_ them where older, cleartext protocols are often permitted49.

## **Key Concepts**

-

## **References**

-
