---
date: 2025-08-17
course: CSM 478 - Computer Networks
tags:
  - personal
  - study
  - CSM478
---
## **Reference For this Section**

![[csm 478 lecture2-NEW.pdf]]

Nodes are attached to networks through communications media via Network Interface Card (NIC)

## NETWORKING HARDWARE OR NETWORKING DEVICES

- Repeaters (also called amplifiers) – electronic devices that receive signals and amplify and send them along the network 
- Hub/Switches – electronic device (with a number of ports) used in a LAN to link groups of computers 
- Routers - electronic devices used to ensure messages are sent to their intended destinations 
- Bridge – consists of hardware and/or software that allows communication between two similar networks 
- Gateway – consists of hardware and/or software that allows communications between dissimilar networks

## How does Bob get Sally’s MAC address since he knows only Sally’s name and does not even have her IP address yet? 

- Bob will begin what is known as Hostname to IP address resolution since he knows only Sally’s name
- Scenario 1 – If the two hosts are on different Networks, then this will Require a Domain Name Service (DNS)
- Scenario 2 – If the two hosts are on the same LAN, then Bob can just send a BROADCAST massage to all hosts on the network to request for the required info


## **Functions of a Router**

- Packet Switching 
- Packet filtering 
- Internetwork communication 
- Path selection


Routers connect two or more networks and forward data packets between them. When data arrives from one of the segments, the router decides, according to it's routing table, to which segment to forward that data.

| Feature                | Router                                                          | Switch                                                             |
| ---------------------- | --------------------------------------------------------------- | ------------------------------------------------------------------ |
| **Alternate Name**     | Layer 3 Switch                                                  | Layer 2 Switch                                                     |
| **OSI Model Layer**    | Layer 3                                                         | Layer 2                                                            |
| **TCP/IP Model Layer** | Layer 3                                                         | Layer 2                                                            |
| **Internetworking**    | Creates internetworks                                           | Does not create internetworks                                      |
| **Broadcast Domains**  | Provides a separate broadcast domain for each of its interfaces | Does not break up broadcast domains by default                     |
| **Collision Domains**  | -                                                               | Breaks up collision domains by default                             |
| **Primary Purpose**    | Forwarding packets                                              | To make a LAN work better by providing more bandwidth to LAN users |
| **Data Handling**      | Forwards packets                                                | Switches frames from one port to another within a switched network |
| **Domain Creation**    | Provides a separate broadcast domain for each of its interfaces | Creates separate collision domains but a single broadcast domain   |

## **Bridges**

A bridge is a network device that filters data traffic from one network to another network

![[Pasted image 20250818171231.png]]

A bridge examines each data frame on a LAN, "passing" those known to be within the same LAN segment , and forwarding those known to be on the other interconnected LAN segment.

Bridges learn which MAC addresses are on which network and develop a learning table (aka. Bridging Table so that subsequent messages can be forwarded to the right network.

A bridge is sometimes combined with a router in a product called a brouter.

## **Gateway**

"Gateway" is a term that was once used to refer to a routing device.

The term gateway now refers to special-purpose devices, that perform protocol conversions. Gateways implement application layer conversions of information received from various protocols.

## **Internet Protocols** 

![[Pasted image 20250818173057.png]]


--- 
---
---
---
---
---


## **Reference For this Section**
![[Computer Networks IP Addressing.pdf]]



## IP Address

- IPv4 [32 bits]
- IPv6 [128 bits]

![[Pasted image 20250818174339.png]]

In short, the diagram shows that the 8-bit binary number `11111111` is equal to the decimal number `255`.

## **Why This is Important for IPv4** 💻

An **IPv4 address** is a 32-bit number, but to make it easier for humans to read, it's broken into four 8-bit octets, which are then written in decimal format and separated by dots (e.g., `192.168.1.10`).

This conversion is especially important for understanding **subnet masks**. A common subnet mask is `255.255.255.0`. Your diagram perfectly explains how each `255` part of that mask is represented in binary as `11111111`.

![[Pasted image 20250818174720.png]]

NB: A network can't exist without a host

|              | Network                                     | Host                                       |
| ------------ | ------------------------------------------- | ------------------------------------------ |
| **Analogy**  | The Street                                  | A house on the street                      |
| **Role**     | The infrastructure that connects everything | An individual device on the infrastructure |
| **Function** | Routes and manages data traffic             | Creates, sends, and receives data          |
| **Address**  | Identified by a shared **Network ID**       | Identified by a unique **Host ID**         |

## **Class A IPv4 address**

![[Pasted image 20250818174801.png]]

### **Class A Network Calculation** 🌐

For Class A, the first 8 bits (the first octet) are dedicated to the **Network part**, while the remaining 24 bits are for the **Host part**. The notes explain the calculation for the number of available Class A networks:

- **Identifying Bit**: A Class A address is identified because its very first bit is always **0**. This leaves 7 remaining bits in the first octet to define the network number (N).
    
    - Structure: `0NNNNNNN.HHHHHHHH.HHHHHHHH.HHHHHHHH`
        
- **Total Possible Networks**: With 7 bits available for the network ID, the total number of possible networks is 27=128. These networks would range from 0 to 127.
    
- **Reserved Networks**: As the notes highlight in the bubbles, two of these network addresses are reserved and cannot be used for assigning to networks:
    
    - **Network 0** (binary `00000000`): This is reserved for the default route.
        
    - **Network 127** (binary `01111111`): This is reserved for **loopback testing** (e.g., `ping 127.0.0.1` tests your own computer's network card).
        
- **Valid Networks**: Subtracting the two reserved networks gives the final count:
    
    - 128−2=126 **valid Class A networks**.
        
    - This is why the first number in a Class A IP address is always between **1** and **126**.

### **Class A Host Calculation** 💻

The notes then explain how the number of available hosts for each Class A network is determined:

1. **Available Bits**: Class A uses the last three octets for the host portion, which provides **24 bits** (H).
    
2. **Total Possible Hosts**: The total number of host addresses that can be created with 24 bits is 224=16,777,216.
    
3. **Reserved Hosts**: Just like with networks, two host addresses within every network are reserved and cannot be assigned to devices:
    
    - **The Network Identification Address**: The address where all host bits are 0 (e.g., `10.0.0.0`). This address identifies the network itself.
        
    - **The Broadcast Address**: The address where all host bits are 1 (e.g., `10.255.255.255`). Packets sent to this address are delivered to all hosts on the network.
        
4. **Valid Hosts**: Subtracting these two reserved addresses gives the final count:
    
    - 16,777,216−2=16,777,214 **valid hosts per network**.

#### **The Problem with Large Networks**

The second image concludes the discussion on Class A networks by highlighting a major practical issue and its solution.

1. **Network Structure Recap**: It shows that each of the 126 valid Class A networks (from `1.0.0.0` to `126.0.0.0`) consists of three components:
    
    - The **Network ID** itself (e.g., `10.0.0.0`).
        
    - The huge pool of **Valid Hosts** (16,777,214 of them).
        
    - The **Broadcast Address** (e.g., `10.255.255.255`).
        
2. **The Problem**: The note points out that having such a massive number of hosts on a single network is not practical. It would lead to severe network **congestion** from things like **multicast traffic** and **broadcast storms** (where a single broadcast message gets sent to all ~16.7 million hosts, overwhelming the network).
    
3. **The Solution**: To solve this, large networks are divided into smaller, more manageable segments. As the note says, "we **subnet** the network." **Subnetting** is the process of breaking a large network into smaller ones, which improves performance and security.


## **Class B IPv4 address**

![[Pasted image 20250818180433.png]]

The notes first establish the basic layout of a Class B address. The 32 bits are split evenly:

- **Network Part**: The first 16 bits (first two octets) identify the network.
    
- **Host Part**: The last 16 bits (last two octets) identify the host on that network.
    

This is often represented as `N.N.H.H`, where `N` is a network octet and `H` is a host octet.

---

### **Class B Network Calculation** 🌐

The notes show how to determine the characteristics of the Class B network space.

#### 1. First Octet Range (128 - 191)

A Class B address is always identified by its first two bits, which are fixed as **10**. The notes use the rule from your previous uploads to calculate the range of the first octet:

- **Start Address**: The first bit is a `1` in the 27 position, so the starting value is **128**.
    
- **End Address**: The second bit is a `0` in the 26 (or 64) position. The calculation is 255−64=191.
    
- This confirms that any IP address starting with a number from **128 to 191** belongs to Class B.
    

#### 2. Number of Networks

- The network part uses 16 bits, but since the first two are fixed (`10`), that leaves **14 bits** to create unique network IDs.
    
- The total number of possible networks is therefore $2^{14}$=16,384.
    
- The notes show a calculation of $2^{14}$−2=16,382. This `-2` logic is typically applied to hosts or subnets, but some older texts applied it to networks as well. For modern understanding, **16,384** is the correct number of Class B networks.
    

---

### **Class B Host Calculation** 💻

The notes then explain how the number of hosts for each Class B network is calculated.

1. **Available Bits**: The host part uses the last two octets, which provides **16 bits** for host addresses.
    
2. **Total Hosts**: The total number of host addresses that can be created with 16 bits is 216=65,536.
    
3. **Valid Hosts**: As with any network, two addresses are reserved and cannot be assigned to a device:
    
    - **The Network ID**: The address where all host bits are 0 (e.g., `172.16.0.0`).
        
    - **The Broadcast Address**: The address where all host bits are 1 (e.g., `172.16.255.255`).
        
4. **Final Calculation**: Subtracting these two reserved addresses gives the final count of usable hosts:
    
    - 216−2=65,534 **valid hosts per network**.



## **Class C Address (192-223)**

Class C is designed for smaller networks.

- **Structure**: The first 24 bits (three octets) are for the **Network part**, and the final 8 bits (one octet) are for the **Host part** (`N.N.N.H`).
    
- **First Octet Range**: A Class C address is identified because its first three bits are fixed as **110**.
    
    - **Starting Value**: The first two `1`s are in the 27 and 26 positions, making the starting value 128+64=192.
        
    - **Ending Value**: The `0` is in the 25 (32) position. The calculation is 255−32=223.
        
    - This confirms the Class C range of **192-223**.
        
- **Number of Networks**: With 24 bits for the network ID and the first 3 fixed, there are **21 bits** available for unique networks (221=2,097,152 networks).
    
- **Number of Hosts**: The host part uses 8 bits.
    
    - Total Hosts: 28=256.
        
    - Valid Hosts: After reserving the network and broadcast addresses, you get 28−2=254 valid hosts per network.
        

---

## **Class D (Multicast) and Class E (Experimental)**

These classes are not used for assigning IP addresses to regular hosts.

### **Class D (224-239)**

- **Purpose**: Used for **multicast transmissions**. This is a way to send a single data packet to a group of interested destinations simultaneously, like in video conferencing or online gaming.
    
- **Identification**: The first four bits are fixed as **1110**.
    
- **Range**: This results in a first octet range from **224 to 239**.
    
- **Note**: Class D addresses don't have the traditional network/host structure.
    

### **Class E (240-255)**

- **Purpose**: Reserved for **network research and experimentation**.
    
- **Identification**: The first four bits are fixed as **1111**.
    
- **Range**: This results in a first octet range from **240 to 255**.
    
- **Note**: These addresses are not used on the public internet.




## **Introduction to Network Masks** 🎭

The second image introduces a crucial concept for how computers understand IP addresses.

- **Network Analysis**: A computer uses two things to determine which network an IP address belongs to:
    
    1. A **Mask** (specifically a Subnet Mask)
        
    2. A logical **AND gate** operation
        
- **Default Mask**: Each address class has a "default mask" that reflects its standard network/host division. This mask helps a computer identify the network portion of an IP address. The notes call this a "boundary level MASK."
    
    - **Class A**: `255.0.0.0`
        
    - **Class B**: `255.255.0.0`
        
    - **Class C**: `255.255.255.0`
        

The primary purpose of this mask, as the notes state, is to know if a network is using its default boundary or if it has been broken down into smaller pieces (**subnetted**).

These notes tie everything together by explaining **default subnet masks** and introducing **CIDR notation**, which is used to describe subnetting and supernetting.

The main takeaway from the notes is: **Every IP address requires a mask** to define which part of the address is the network and which part is the host.

---

## **Default Masks (Classful Addressing)**

Each of the main address classes (A, B, and C) has a default mask that reflects its standard network/host division. The notes show this in three different formats.

|Class|Bitwise Notation (Binary)|Dotted-Decimal|Default CIDR|
|---|---|---|---|
|**A**|`11111111.00000000.00000000.00000000`|`255.0.0.0`|`/8`|
|**B**|`11111111.11111111.00000000.00000000`|`255.255.0.0`|`/16`|
|**C**|`11111111.11111111.11111111.00000000`|`255.255.255.0`|`/24`|

- **Bitwise Notation**: Shows the mask in binary. The `1`s represent the **network** portion and the `0`s represent the **host** portion.
    
- **Dotted-Decimal**: The common way we write the mask.
    
- **CIDR Notation**: A shorthand that simply counts the number of `1`s in the mask. For example, a Class C mask has 24 ones, so its CIDR is `/24`.
    

---

## Subnetting and Supernetting ↔️

CIDR notation makes it easy to see if a network is using its default size, has been broken down (**subnetted**), or has been combined with others (**supernetted**).

The rule is simple:

- **Subnetting**: The CIDR number is **larger** than the default.
    
- **Supernetting**: The CIDR number is **smaller** than the default.
    

### Subnetting (Creating Smaller Networks)

As one note says, "We subnet networks to convert hosts to create networks." This means we "borrow" bits from the host portion to create more network IDs, resulting in more, smaller networks.

- **Example**: A Class A network is `/8` by default. If you see an address like `10.20.30.40/16`, the `/16` tells you it's a **subnet** of the larger Class A network.
    

### Supernetting (Creating Larger Networks)

This is the opposite of subnetting. It combines multiple smaller networks into a single, larger one by making the mask shorter (fewer `1`s).

- **Example**: The notes show `129.22.4.13/8`.
    
    - The IP `129.22.4.13` is in the Class B range (128-191), which has a default mask of `/16`.
        
    - However, the mask used is `/8`, which is shorter. This indicates that multiple Class B networks have been grouped together to form one large **supernet**.
        

---

## Summary of IP Address Classes

This diagram from your notes provides a great summary of the first-octet ranges and the default CIDR mask for each class.

|Class|First Octet Range|Default CIDR Mask|
|---|---|---|
|**A**|1 - 126|`/8`|
|**B**|128 - 191|`/16`|
|**C**|192 - 223|`/24`|
|**D**|224 - 239|`/30` (as noted, though not a standard mask)|
|**E**|240 - 255|N/A|




