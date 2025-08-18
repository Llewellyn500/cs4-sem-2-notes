# **Question**

![[END OF SEM 2 EXAMS NETWORKING 2020.pdf]]

# **ANSWERS**

Here are the solutions and explanations for the networking exam questions, based on the provided PDF.

---

## **Analysis of `195.143.208.133/25`**

### a. What class is the IP address?

**Answer:** **Class C**1.

**Explanation:** The class of an IP address is determined by the value of its first octet. The range for Class C addresses is 192 to 223. Since the first octet of this IP address is **195**, it falls within the Class C range.

### b. What subnet is the address on?

**Answer:** The address is on the **`195.143.208.128`** subnet2.

**Explanation:** To find the subnet address, you perform a bitwise AND operation between the IP address and the subnet mask.

- **IP Address (`133`):** `10000101`
    
- **Subnet Mask (`/25` is `128`):** `10000000`
    
- AND Result: 10000000, which is 128 in decimal.
    
    So, the subnet address is 195.143.208.128.
    

### c. What is the NetID of the address?

**Answer:** `195.143.208`3.

**Explanation:** For a Class C address, the default **Network ID (NetID)** consists of the first three octets.

### d. What is the HostID of the address?

**Answer:** `133`4.

**Explanation:** For a default Class C address, the **Host ID (HostID)** is the fourth octet.

### e. What is the SubnetID of the address?

**Answer:** The **SubnetID** is the bit value `1`5.

**Explanation:** A default Class C network has a `/24` mask. This network uses a `/25` mask, which means **1 bit** has been borrowed from the host portion to create subnets. Looking at the fourth octet (`133` is `10000101` in binary), the first bit (the borrowed subnet bit) is **1**. This indicates the address is on the second subnet (the first subnet would have a `0` in this position).

### f. What is the site address?

**Answer:** `195.143.208.128`6.

**Explanation:** The "site address" is another term for the subnet address, which is the identifier for the specific subnet the host belongs to. This was calculated in question (b).

### g. Give the address in its BITWISE notation.

**Answer:** `11000011.10001111.11010000.10000101`7.

**Explanation:** This is the binary equivalent of each octet in the IP address `195.143.208.133`.

- 195 = `11000011`
    
- 143 = `10001111`
    
- 208 = `11010000`
    
- 133 = `10000101`
    

### h. What does the `/25` mean?

**Answer:** It's **CIDR (Classless Inter-Domain Routing) notation**8. The

`/25` indicates that the first **25 bits** of the address are used to identify the network (including the subnet), leaving the remaining 7 bits for host addresses.

### i. Give the dotted decimal notation of the `/25` and also give bitwise notation equivalent.

**Answer:**

- **Dotted Decimal:** `255.255.255.128`9.
    
- **Bitwise Notation:** `11111111.11111111.11111111.10000000`10.
    

**Explanation:** A `/25` mask is represented by 25 consecutive `1`s followed by 7 `0`s in binary. Converting this 32-bit number to dotted decimal gives the result above.

---

## **Network Design and Implementation**

### j. Design a suitable network for the organisation ensuring the most efficient usage of addresses.

**Answer:** To serve 5 branches, the `/25` address space (which only provides 2 subnets) is insufficient. **Assuming the bank was given the entire `195.143.208.0/24` network**, we can use **VLSM (Variable Length Subnet Mask)** for an efficient design.

**Assumptions:**

- A central Head Office (HQ) needs 50 hosts.
    
- Each of the 5 branches needs 20 hosts.
    
- The 5 WAN links connecting HQ to the branches only need 2 hosts each.
    

Here is the efficient VLSM design:

| Subnet Purpose | Host Req. | Mask | Subnet Address | Host Range | Broadcast |

| :--- | :--- | :--- | :--- | :--- | :--- |

| HQ LAN | 50 | /26 | 195.143.208.0 | .1 - .62 | .63 |

| Branch 1 LAN | 20 | /27 | 195.143.208.64 | .65 - .94 | .95 |

| Branch 2 LAN | 20 | /27 | 195.143.208.96 | .97 - .126| .127|

| Branch 3 LAN | 20 | /27 | 195.143.208.128| .129 - .158| .159|

| Branch 4 LAN | 20 | /27 | 195.143.208.160| .161 - .190| .191|

| Branch 5 LAN | 20 | /27 | 195.143.208.192| .193 - .222| .223|

| WAN Link 1 | 2 | /30 | 195.143.208.224| .225 - .226| .227|

| WAN Link 2 | 2 | /30 | 195.143.208.228| .229 - .230| .231|

| WAN Link 3 | 2 | /30 | 195.143.208.232| .233 - .234| .235|

| WAN Link 4 | 2 | /30 | 195.143.208.236| .237 - .238| .239|

| WAN Link 5 | 2 | /30 | 195.143.208.240| .241 - .242| .243|

### k. List all the SubnetID's

Answer: Based on the design above, the SubnetIDs (subnet addresses) are:

`195.143.208.0/26`, `195.143.208.64/27`, `195.143.208.96/27`, `195.143.208.128/27`, `195.143.208.160/27`, `195.143.208.192/27`, `195.143.208.224/30`, `195.143.208.228/30`, `195.143.208.232/30`, `195.143.208.236/30`, `195.143.208.240/30`11.

---

## **Analysis of `195.143.208.133/28`**

### l. Give the subnet address that this IP address resides on

**Answer:** `195.143.208.128`12.

**Explanation:** The mask `/28` is `255.255.255.240`. ANDing `133` (`10000101`) with `240` (`11110000`) results in `128` (`10000000`).

### m. What is the site address for the given address in 'l' above

**Answer:** `195.143.208.128`13.

### n. What is the NetID for the given address in 'l' above

**Answer:** `195.143.208`14.

### o. What is the HostID for the given address in 'l' above

**Answer:** `133`15.

### p. What is the SubnetID for the given address in 'l' above

**Answer:** The **SubnetID** is `1000` in binary, or `8` in decimal16.

**Explanation:** A `/28` mask on a Class C network means 4 bits have been borrowed (28−24=4). The first 4 bits of the fourth octet (`133` is `10000101`) are `1000`, which is the SubnetID.

---

## **Diagram and Network Concepts**

### q. Draw the network diagram

Answer: The most suitable design is a Hub-and-Spoke topology.

Description: A central router at the Head Office (the Hub) connects to the ISP. This router also connects to the HQ's local LAN (via a switch). Five separate WAN links connect the HQ router to a router at each of the 5 branches (the Spokes). Each branch router connects to its own local LAN switch, where workstations and printers are connected.

### r. Explain the functionality of each of the devices

- **Router:** Operates at Layer 3. Its primary function is to connect different networks (subnets) and make decisions on where to forward packets based on their destination IP address. In this diagram, routers connect the branch LANs to the HQ LAN and the entire organization to the internet.
    
- **Switch:** Operates at Layer 2. Its function is to connect devices on the same local network (LAN). It forwards data frames only to the specific port connected to the destination device, creating separate collision domains for each port.
    

### s. How will you ensure Internet connectivity for host at each of the 5 branches?

Internet connectivity is achieved by configuring the HQ router to connect to the ISP. All 5 branches will be configured to send internet-bound traffic through their WAN link to the HQ router. **Network Address Translation (NAT)** will be enabled on the HQ router to translate the private IP addresses of all internal hosts to the single public IP address provided by the ISP.

### t. Explain type(s) of connections in your network diagram

- **LAN (Local Area Network) Connections:** These are within a single site (e.g., connecting workstations to a switch at a branch). They typically use **Ethernet** cables (e.g., Cat6).
    
- **WAN (Wide Area Network) Connections:** These connect the different geographical sites (HQ to each branch). They would likely be implemented using technologies like leased lines, MPLS, or a secure VPN over the internet.
    

### u. Explain the protocols for devices communication

- **IP (Internet Protocol):** The core Layer 3 protocol that provides logical addressing (IP addresses) and routing of packets between different networks.
    
- **Ethernet:** The dominant Layer 2 protocol for LANs, responsible for framing data and managing access to the physical media.
    
- **PPP (Point-to-Point Protocol) or HDLC:** Common Layer 2 protocols used for data transmission over WAN links.
    

### v. Explain protocol for 3 applications communication

1. **HTTP/HTTPS (Hypertext Transfer Protocol/Secure):** Used for accessing websites. A user's browser sends an HTTP request to a web server, which sends back the website data.
    
2. **DNS (Domain Name System):** Translates human-readable domain names (e.g., [www.google.com](https://www.google.com/)) into machine-readable IP addresses. This must happen before most internet communication can begin.
    
3. **SMTP (Simple Mail Transfer Protocol):** Used for sending emails from an email client to an email server.
    

### w. Explain the addressing mechanism in the movement of packets from one branch to the other

When a PC at Branch 1 wants to send a packet to a PC at Branch 2, it uses IP addressing.

1. The sending PC sees the destination IP is on a different subnet and sends the packet to its **default gateway** (the Branch 1 router).
    
2. The Branch 1 router looks at its routing table and determines the best path is via the WAN link to the HQ router.
    
3. The HQ router receives the packet, checks its routing table, and sees that the destination network is connected via the WAN link to the Branch 2 router. It forwards the packet there.
    
4. The Branch 2 router receives the packet, sees that the destination IP is on its local LAN, and forwards the packet directly to the receiving PC.
    

### x. Assuming each branch has 8 workstations and a network printer, how many collision domains has your network diagram

**Answer:** **55 collision domains**.

**Explanation:** A switch creates a separate collision domain for every port.

- Each of the 5 branches has 9 devices (8 workstations + 1 printer), so that's **9 collision domains** per branch. Total for branches: 9×5=45.
    
- Let's assume the HQ has at least 10 hosts/servers. That's another **10 collision domains**.
    
- Total = 45+10=55.
    

### y. As follow-up question to 'x', how many broadcast domains has your network diagram?

**Answer:** **6 broadcast domains**.

**Explanation:** Routers create broadcast domains. A broadcast sent on one interface will not be forwarded out another. In the Hub-and-Spoke design:

- The HQ LAN is one broadcast domain.
    
- Each of the 5 branch LANs is its own broadcast domain.
    
- Total = 1(HQ)+5(Branches)=6.
    

### z. Write a convincing summary statement to convince management

**To the Management of the Bank,**

"Investing in this proposed network design will transform our 5 branches and Head Office into a single, cohesive, and secure digital ecosystem. By implementing this modern infrastructure, we stand to gain significant advantages:

1. **Enhanced Productivity:** Staff at any branch can instantly and securely access centralized data and applications, eliminating delays and improving workflow efficiency.
    
2. **Improved Customer Service:** Fast and reliable inter-branch communication means quicker processing of transactions and customer requests, leading to higher client satisfaction.
    
3. **Centralized Security:** This design allows us to centralize our security measures at the Head Office, ensuring that all 5 branches are protected by a robust, consistently managed firewall and threat prevention system, safeguarding sensitive financial data.
    
4. **Scalability for the Future:** The network is built on a flexible foundation that can easily be expanded to include more branches or new digital banking services without requiring a costly overhaul.
    

This investment is not just an IT upgrade; it's a strategic step towards building a more agile, secure, and competitive bank for the future."