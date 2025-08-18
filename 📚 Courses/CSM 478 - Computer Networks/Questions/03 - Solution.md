# **Quesiton**

![[VLSM_Network_Design_Question.pdf]]

# **Answer**

Of course. Here is a complete network design that efficiently allocates the given IP address space according to the company's requirements, along with explanations for each step.

---

## **D. Network Design for ABC Company**

The task is to design a network for ABC Company using the IP address

**`192.3.4.0/24`**1. The most efficient way to do this is with

**Variable Length Subnet Mask (VLSM)**, which creates subnets of different sizes based on the specific host requirements for each branch.

The process involves arranging the requirements from largest to smallest and allocating address blocks sequentially.

### **VLSM Calculation and Allocation**

1. **Asokwa Branch (Largest Requirement)**
    
    - **Hosts Needed**: 582.
        
    - **Calculation**: To get at least 58 usable addresses, we need 6 host bits (26=64 total addresses, leaving 62 for hosts). This requires a `/26` subnet mask (32 total bits - 6 host bits).
        
    - **Result**: The first available block `192.3.4.0` is used.
        
2. **Asafo Branch**
    
    - **Hosts Needed**: 263.
        
    - **Calculation**: To get 26 usable addresses, we need 5 host bits (25=32 total addresses, leaving 30 for hosts). This requires a `/27` subnet mask.
        
    - **Result**: The next available block, `192.3.4.64`, is used.
        
3. **Adum Branch**
    
    - **Hosts Needed**: 104.
        
    - **Calculation**: To get 10 usable addresses, we need 4 host bits (24=16 total addresses, leaving 14 for hosts). This requires a `/28` subnet mask.
        
    - **Result**: The next available block, `192.3.4.96`, is used.
        
4. **WAN Links**
    
    - **Hosts Needed**: 2 for each of the three links5.
        
    - **Calculation**: To get 2 usable addresses for a point-to-point link, we need 2 host bits (22=4 total addresses). This requires a `/30` subnet mask.
        
    - **Result**: The next three available blocks (`.112`, `.116`, `.120`) are used for the WAN links.
        

### **Final IP Addressing Plan**

This table summarizes the complete and efficient network design.

|Subnet Purpose|Hosts Needed|Subnet Address (Site Address)|IP Address Range|Broadcast Address|
|---|---|---|---|---|
|**Asokwa LAN**|58|`192.3.4.0/26`|`192.3.4.1` - `192.3.4.62`|`192.3.4.63`|
|**Asafo LAN**|26|`192.3.4.64/27`|`192.3.4.65` - `192.3.4.94`|`192.3.4.95`|
|**Adum LAN**|10|`192.3.4.96/28`|`192.3.4.97` - `192.3.4.110`|`192.3.4.111`|
|**WAN Link 1**|2|`192.3.4.112/30`|`192.3.4.113` - `192.3.4.114`|`192.3.4.115`|
|**WAN Link 2**|2|`192.3.4.116/30`|`192.3.4.117` - `192.3.4.118`|`192.3.4.119`|
|**WAN Link 3**|2|`192.3.4.120/30`|`192.3.4.121` - `192.3.4.122`|`192.3.4.123`|

---

## **E. Network Diagram**

Based on the client-server architecture connecting the three branches, a **Hub-and-Spoke** topology is the most common and logical design. This involves a central router connecting to each of the branch routers.

**Description of the Diagram**:

- A central **Hub Router** acts as the main connection point.
    
- The three **WAN links** connect the Hub Router to a dedicated router at each of the three branches (Asokwa, Asafo, and Adum).
    
- Each branch router connects to a local **Switch**.
    
- The workstations (hosts) for each branch connect to their local switch.
    
- The diagram would be labeled with the IP address scheme from the table above. For example:
    
    - The **Asokwa LAN** segment would be labeled **`192.3.4.0/26`**.
        
    - The **WAN link** connecting to the Asokwa router would be labeled **`192.3.4.112/30`**.