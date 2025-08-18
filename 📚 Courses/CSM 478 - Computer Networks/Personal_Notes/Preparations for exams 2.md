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



## 1. Basic IP Address Analysis (Classful)

The notes show a quick method for breaking down an IP address based on its class (A, B, or C) without any subnetting.

#### Example 1: `187.132.65.7` (Class B)

Because the first number `187` is between 128 and 191, it's a **Class B** address. This means the first two numbers are the network part and the last two are the host part.

- **Network Address**: `187.132.0.0` (The host part is set to all zeros).
    
- **Network ID**: `187.132`
    
- **Host ID**: `65.7`
    
- **Broadcast Address**: `187.132.255.255` (The host part is set to all ones).
    
- **Last Valid Host**: `187.132.255.254` (The address right before the broadcast).
    

#### Example 2: `121.69.72.14` (Class A)

Because `121` is between 1 and 126, it's a **Class A** address. The first number is the network part and the last three are the host part.

- **Network Address**: `121.0.0.0`
    
- **Network ID**: `121`
    
- **Host ID**: `69.72.14`
    
- **Broadcast Address**: `121.255.255.255`
    
- **Last Valid Host**: `121.255.255.254`
    

---

## 2. Network Diagram Analysis

The notes analyze a network diagram to identify its key components.

- **Broadcast Domains**: These are created by routers. A broadcast sent in one domain will not cross the router into another. The diagram has **3 broadcast domains** because the routers separate the network into three segments with hosts.
    
- **Collision Domains**: These are created by switches. Each port on a switch is a separate collision domain, meaning devices can send data at the same time without causing a "collision." The diagram has **9 collision domains**.
    
- **Subnets**: Every router interface connects to a unique subnet. By counting the connections between routers and from routers to switches, the notes correctly identify **6 subnets**.
    
- **Topology**: The diagram shows a **hybrid topology** (a mix of different types, like star and bus) and uses a **client-server architecture**.

![[Pasted image 20250818201329.png]]

---

## 3. Private vs. Public IP Addressing

- **Private IP Addresses**: These are reserved for use inside an internal network (like your home or office Wi-Fi). They are **not routable** on the public internet. The reserved ranges are:
    
    - Class A: `10.0.0.0` – `10.255.255.255`
        
    - Class B: `172.16.0.0` – `172.31.255.255`
        
    - Class C: `192.168.0.0` – `192.168.255.255`
        
- **Public IP Addresses**: These are provided by an Internet Service Provider (ISP) and are unique across the entire internet.
    
- **NAT (Network Address Translation)**: As the notes mention, NAT is the protocol used by routers to map multiple private IP addresses to a single public IP address, allowing devices on the private network to access the internet.
    

---

## 4. Subnetting with VLSM

The notes describe a scenario where a network administrator is given a Class C block (`192.168.16.0/24`) and must divide it to fit the 6 subnets in the diagram.

- **The Challenge**: Different subnets have different numbers of hosts (one needs 80 hosts, others need fewer).
    
- **The Solution**: **VLSM (Variable Length Subnet Mask)**. This is an efficient subnetting technique that allows you to use different mask lengths for different subnets. You can create a larger subnet for the 80 hosts and much smaller subnets for the router-to-router links (which only need 2 hosts). As the notes say, this is an "intelligent" method that conserves IP addresses.
    

---

## 5. Domain Name System (DNS)

Finally, the notes explain the hierarchy of a domain name using `orbit-computer.solutions.com` as an example.

- **`.com`**: **Top-Level Domain (TLD)**. Managed by root servers.
    
- **`solutions`**: **Second-Level Domain**. This is the domain you typically purchase.
    
- **`orbit-computer`**: **Third-Level Domain (or subdomain)**. This often points to a specific server or service (the "actual machine").


## **FLSM (Fixed Length Subnet Mask)**.

The overall goal is to take one large network (`192.168.16.0/24`) and break it into eight smaller, equal-sized networks to be used in the provided network diagram.

---

## 1. The Starting Point

- **Given Network**: The notes start with the public IP address `192.168.16.5/24`.
    
- **Analysis**: This is a Class C network. The `/24` CIDR notation means it's a standard, unsubnetted network with 24 bits for the network part and 8 bits for the host part, providing 254 usable host addresses.
    
- **The Goal**: The network diagram requires at least 6 separate subnets. The task is to divide the `192.168.16.0/24` network to meet this requirement.
    

---

## 2. The Subnetting Process (FLSM)

**FLSM** means every new subnet will have the exact same size and subnet mask. The process involves "borrowing" bits from the host portion to use for creating new network IDs.

1. **Determine Bits to Borrow**: The notes calculate how many bits to borrow to get at least 6 subnets.
    
    - Borrowing 2 bits: $2^2$=4 subnets. (Not enough)
        
    - Borrowing **3 bits**: $2^3$=8 subnets. (This is enough)
        
2. **Calculate the New Subnet Mask**:
    
    - The original mask was `/24`.
        
    - By borrowing 3 bits, the new mask length becomes 24+3=27.
        
    - The new CIDR notation for all subnets is **`/27`**.
        
    - In binary, the new mask is `11111111.11111111.11111111.11100000`.
        
3. **Calculate the "Block Size"**: The block size is the increment between each new subnet address. With 3 bits borrowed, there are 5 host bits remaining (8−3=5).
    
    - The block size is calculated as $2^5$=32.
        
    - This means the new subnets will start at `.0`, `.32`, `.64`, `.96`, and so on.
        

---

## 3. The Resulting Subnets

The notes then list the 8 new subnets created from this process. Each `/27` subnet has 32 total addresses, which provides 32−2=30 **valid hosts**.

|Subnet #|Subnet Address|Host Range|Broadcast Address|
|---|---|---|---|
|**1**|`192.168.16.0/27`|`192.168.16.1` - `30`|`192.168.16.31`|
|**2**|`192.168.16.32/27`|`192.168.16.33` - `62`|`192.168.16.63`|
|**3**|`192.168.16.64/27`|`192.168.16.65` - `94`|`192.168.16.95`|
|**4**|`192.168.16.96/27`|`192.168.16.97` - `126`|`192.168.16.127`|
|**5**|`192.168.16.128/27`|`192.168.16.129`- `158`|`192.168.16.159`|
|**6**|`192.168.16.160/27`|`192.168.16.161`- `190`|`192.168.16.191`|
|**7**|`192.168.16.192/27`|`192.168.16.193`- `222`|`192.168.16.223`|
|**8**|`192.168.16.224/27`|`192.168.16.225`- `254`|`192.168.16.255`|

---

## 4. Applying the Subnets to the Diagram

Finally, the note "NOW WE PROCEED TO DESIGN THE NETWORK" indicates that these newly created subnets are now ready to be assigned to the different segments in the network diagram. The first image shows this has been done, with subnets like `.32/27`, `.64/27`, and `.96/27` labeling the different connections and LANs.

![[Pasted image 20250818211351.png]]


## **VLSM (Variable Length Subnet Mask)**

The core idea is to stop wasting IP addresses by creating subnets that are perfectly sized for their specific needs.

---

## 1. The Problem with FLSM

The notes start by identifying the major inefficiency of the previous FLSM design.

- In the FLSM example, every subnet was `/27`, providing 30 usable host IP addresses.
    
- However, the network diagram shows several "point-to-point" links between routers. These connections only ever need **two** host IP addresses (one for each router interface).
    
- **The Waste**: Assigning a subnet with 30 addresses to a link that only needs 2 wastes 28 IP addresses. When this is repeated across the network, hundreds of IPs can be wasted.
    

---

## 2. The VLSM Procedure: A New Focus

VLSM solves this problem by changing the focus of the subnetting process.

- **FLSM focuses on**: The total **number of subnets** you need.
    
- **VLSM focuses on**: The **number of hosts** required for each _individual_ subnet.

The procedure is to start with the largest host requirement and create a custom-sized subnet for it. Then you move to the next largest requirement and create another custom-sized subnet from the remaining address space.

---

## 3. Two Solutions for Implementing VLSM

The notes cleverly propose two ways to achieve this efficient design.

### Solution 1: Subnetting an Existing Subnet

This is a hybrid approach.

1. **Start** with one of the `/27` subnets created during the FLSM exercise (e.g., `192.168.16.32/27`).
    
2. **Subnet it again**: Break this smaller block down even further. To get 2 valid hosts, you need a `/30` mask (which provides 22−2=2 hosts).
    
3. **Result**: The `192.168.16.32/27` block is carved into smaller `/30` subnets like `192.168.16.32/30`, `192.168.16.36/30`, etc. These small subnets are then perfect for the router-to-router links.
    

### Solution 2: A Full VLSM Design (Recommended)

This is the more direct and efficient method.

1. **Start** with the original large network: `192.168.16.0/24`.
    
2. **Identify Requirements**: Look at the entire network diagram and find the largest host requirement. In this case, every single subnet (both the LANs and the router links) only needs a maximum of 2 hosts.
    
3. **Calculate the Mask**: To satisfy a requirement of 2 hosts, you need a `/30` mask. The block size for a `/30` mask is 4.
    
4. **Result**: The entire `192.168.16.0/24` network is divided into many small `/30` subnets. The notes create a table showing the first several of these.
    

|Subnet #|Subnet Address|Host Range|Broadcast Address|
|---|---|---|---|
|**1**|`192.168.16.0/30`|`192.168.16.1` - `2`|`192.168.16.3`|
|**2**|`192.168.16.4/30`|`192.168.16.5` - `6`|`192.168.16.7`|
|**3**|`192.168.16.8/30`|`192.168.16.9` - `10`|`192.168.16.11`|
|...|...|...|...|

---

## 4. The Final, Efficient Network

The final network diagram shows the result of the VLSM process. Each link and each local network is assigned a tiny, perfectly-sized `/30` subnet.

As the note at the bottom says: **"This Network ensures maximum and efficient utilization of IP Addresses such that no IP Address is wasted."**

![[Pasted image 20250818210937.png]]
