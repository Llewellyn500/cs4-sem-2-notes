# **Questions**

![[Networking Trials Questions.pdf]]

# **Answers**

Of course. Here are the solutions and explanations for the questions in the provided assignment.

The scenario involves a rural bank with 5 branches that has acquired the IP address

`195.143.208.133/25` from an ISP1.

---

## **Analysis of `195.143.208.133/25`**

1. What class is the IP address? 2

**Answer**: **Class C**.

**Explanation**: The class of an IP address is determined by its first octet. The range for Class C is 192-223. Since the first octet is **195**, it falls into the Class C category.

2. What subnet is the address on? 3

**Answer**: The address is on the **`195.143.208.128`** subnet.

**Explanation**: You find the subnet address by performing a bitwise AND operation between the IP address and the subnet mask. The last octet of the IP is `133` (`10000101`) and the last octet of the `/25` mask is `128` (`10000000`). The result of the AND operation is `128` (`10000000`).

3. What is the NetID of the address? 4

**Answer**: `195.143.208`.

**Explanation**: For a Class C address, the default **Network ID (NetID)** is the first three octets.

4. What is the HostID of the address? 5

**Answer**: `133`.

**Explanation**: In a default Class C address, the **Host ID (HostID)** is the fourth and final octet.

5. What is the SubnetID of the address? 6

**Answer**: The **SubnetID** is `1`.

**Explanation**: A standard Class C network has a `/24` mask. Since this network uses a `/25` mask, one bit has been "borrowed" from the host portion to create subnets. In the fourth octet (`133` is `10000101`), that first borrowed bit is a **1**, which is the SubnetID.

6. What is the site address? 7

**Answer**: `195.143.208.128`.

**Explanation**: "Site address" is another term for the subnet address, which identifies the specific subnet the host is on.

7. Give the address in its BITWISE notation. 8

**Answer**: `11000011.10001111.11010000.10000101`.

**Explanation**: This is the binary representation of each decimal number in the IP address.

8. What does the /25 mean? 9

**Answer**: This is **CIDR (Classless Inter-Domain Routing) notation**. The `/25` signifies that the first **25 bits** of the 32-bit address represent the network portion (including the subnet), leaving the remaining 7 bits for host addresses.

9. Give the dotted decimal notation of the /25 and also give bitwise notation equivalent. 10

**Answer**:

- **Dotted Decimal**: `255.255.255.128`
    
- **Bitwise Notation**: `11111111.11111111.11111111.10000000`
    

**Explanation**: A `/25` mask consists of 25 ones followed by 7 zeros. Converting this binary value to decimal results in the notation above.

---

## **Network Design**

10. Design a suitable network for the organization ensuring the most efficient usage of addresses. 11

**Answer**: The given `/25` address space only provides two subnets, which is not enough for 5 branches and a head office. **Assuming the bank was actually assigned the entire `195.143.208.0/24` block**, we can use **VLSM (Variable Length Subnet Mask)** for an efficient design.

**Assumptions**:

- A Head Office (HQ) requires 50 host addresses.
    
- Each of the 5 branches requires 20 host addresses.
    
- The 5 WAN links connecting HQ to each branch require 2 host addresses each.
    

The most efficient design is as follows:

| Purpose | Hosts Needed | Mask | Subnet Address | Host Range | Broadcast |

| :--- | :--- | :--- | :--- | :--- | :--- |

| HQ LAN | 50 | /26 | 195.143.208.0 | .1 - .62 | .63 |

| Branch 1 LAN | 20 | /27 | 195.143.208.64 | .65 - .94 | .95 |

| Branch 2 LAN | 20 | /27 | 195.143.208.96 | .97 - .126 | .127 |

| Branch 3 LAN | 20 | /27 | 195.143.208.128| .129 - .158 | .159 |

| Branch 4 LAN | 20 | /27 | 195.143.208.160| .161 - .190 | .191 |

| Branch 5 LAN | 20 | /27 | 195.143.208.192| .193 - .222 | .223 |

| WAN Link 1 | 2 | /30 | 195.143.208.224| .225 - .226 | .227 |

| WAN Link 2 | 2 | /30 | 195.143.208.228| .229 - .230 | .231 |

| WAN Link 3 | 2 | /30 | 195.143.208.232| .233 - .234 | .235 |

| WAN Link 4 | 2 | /30 | 195.143.208.236| .237 - .238 | .239 |

| WAN Link 5 | 2 | /30 | 195.143.208.240| .241 - .242 | .243 |

11. List all the SubnetIDs. 12

Answer: Based on the VLSM design, the SubnetIDs (subnet addresses) are:

195.143.208.0/26, 195.143.208.64/27, 195.143.208.96/27, 195.143.208.128/27, 195.143.208.160/27, 195.143.208.192/27, 195.143.208.224/30, 195.143.208.228/30, 195.143.208.232/30, 195.143.208.236/30, and 195.143.208.240/30.

---

## **Analysis of `195.143.208.133/28`**

12. Give the subnet address that this IP address resides on (195.143.208.133/28). 13

**Answer**: `195.143.208.128`.

**Explanation**: A `/28` mask is `255.255.255.240`. Performing a bitwise AND between `133` (`10000101`) and `240` (`11110000`) results in `128` (`10000000`).

13. What is the site address for the given address in question 12 above? 14

**Answer**: `195.143.208.128`.

14. What is the NetID for the given address in question 12 above? 15

**Answer**: `195.143.208`.

15. What is the HostID for the given address in question 12 above? 16

**Answer**: `133`.

16. What is the SubnetID for the given address in question 12 above? 17

**Answer**: The **SubnetID** is `1000` in binary, or `8` in decimal.

**Explanation**: A `/28` mask on a Class C network means 4 bits have been borrowed for the subnet (28−24=4). The first 4 bits of the fourth octet of the IP address (`1000`0101) represent this SubnetID.

---

## **Network Diagram**

17. Draw the network diagram that can be used for the implementation of the organization's network. 18

Answer: The best topology for this scenario is a Hub-and-Spoke model.

Description:

- A central **Hub** site (Head Office) has a main router connected to the ISP.
    
- This router also connects to the local HQ LAN via a switch.
    
- Five separate WAN links (the **Spokes**) connect the Hub router to a dedicated router at each of the 5 branch offices.
    
- Each branch router connects to a local switch to provide network access for the devices in that branch.
    
- Each of the 11 subnets from the VLSM design in question 10 would be assigned to a specific LAN or WAN link in this diagram.