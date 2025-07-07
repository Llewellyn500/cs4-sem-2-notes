# **Question** 

![[20200129_151600.jpg]]

---
# **Answers**

### **Analysis of the Original Network (Hub)**

The diagram shows 10 computers connected to a central Hub. This is a classic Star topology. The key to answering the initial questions is understanding how a Hub functions. A Hub is a Layer 1 (Physical Layer) device that acts as a simple repeater. It receives an electrical signal on one port and regenerates it out to all other ports.

---

**1. How many nodes has the network?**

- **Answer:** 11 nodes.
    
- **Explanation:** A node is any active device on a network. In this diagram, there are 10 workstations (computers) and 1 Hub, for a total of 11 nodes.
    

**2. How many collision domains are there?**

- **Answer:** 1 collision domain.
    
- **Explanation:** A collision domain is a network segment where data packets can collide. Because a Hub regenerates all traffic to all ports, all connected devices share the same bandwidth and are part of a single collision domain. If two devices try to send data at the same time, a collision will occur.
    

**3. How many broadcast domains are there?**

- **Answer:** 1 broadcast domain.
    
- **Explanation:** A broadcast domain is a logical area where all devices receive broadcast frames. Hubs do not segment a network. Only a Layer 3 device, like a Router, can create separate broadcast domains. Therefore, the entire network is one large broadcast domain.
    

**4. How many workstations are there?**

- **Answer:** 10 workstations.
    
- **Explanation:** Simply counting the computer icons in the diagram shows 10 workstations.
    

**5. What line protocol is used by the network?**

- **Answer:** Ethernet.
    
- **Explanation:** The diagram depicts a standard Local Area Network (LAN). The dominant protocol for such wired LANs is Ethernet.
    

**6. What line configuration does the network use?**

- **Answer:** Bus topology.
    
- **Explanation:** 
    

**7. Outline the problem(s) with the network.**

- **Answer:** The primary problems with this hub-based network are:
    
    - **Single Collision Domain:** It leads to frequent data collisions, which require devices to retransmit data, severely slowing down the network.
        
    - **Half-Duplex Communication:** Devices cannot send and receive data at the same time, limiting the effective bandwidth.
        
    - **Shared Bandwidth:** The total bandwidth of the network (e.g., 100 Mbps) is shared among all 10 devices, so each device gets only a fraction of the total.
        
    - **Security Risk:** The Hub broadcasts all data to every port, meaning any device can easily "sniff" traffic intended for another device using packet-capturing software.
        

**8. Assuming a transmission from PC1 is sent to PC7, which node(s) will hear?**

- **Answer:** All other nodes (PC2, PC3, PC4, PC5, PC6, PC8, PC9, and PC10) and the intended recipient (PC7).
    
- **Explanation:** A Hub is not an intelligent device. It operates at the physical layer and simply repeats any incoming signal to every other port. While only PC7 will accept and process the data frame (because the destination MAC address matches), all other PCs will receive the signal.
    

**9. Give reason(s) for your answer in (Q8).**

- **Answer:** The reason is that a Hub is a Layer 1 multiport repeater. It has no knowledge of MAC addresses or IP addresses. Its only function is to take an incoming electrical signal and regenerate it out of all other ports, regardless of the intended destination.
    

**10. Explain the access method used by the network.**

- **Answer:** The network uses **CSMA/CD (Carrier Sense Multiple Access with Collision Detection)**.
    
- **Explanation:**
    
    - **CSMA:** Devices first "listen" to the network cable (Carrier Sense) to check if it's free before transmitting.
        
    - **MA:** Multiple devices have Access to the same network medium.
        
    - **CD:** If two devices transmit at once, they detect the Collision, stop, wait a random amount of time (a process called backoff), and then attempt to retransmit.
        

**11. What LAN transmission method is used by PC1 in {Q8}?**

- **Answer:** Unicast.
    
- **Explanation:** A unicast transmission is a one-to-one communication. The data frame sent by PC1 is addressed to the specific MAC address of PC7. Even though the Hub physically broadcasts the frame, it is logically a unicast message intended for a single recipient.
    

**12. Explain your answer in (Q11).**

- **Answer:** The Ethernet frame header contains a destination MAC address field. For this transmission, PC1 populates this field with the unique MAC address of PC7. Only the device whose network card has this matching address will fully process the frame; all others will discard it.
    

**13. What LAN transmission method is used by PC7 to respond to PC1 in {Q8}?**

- **Answer:** Unicast.
    
- **Explanation:** Just like the initial transmission, the response from PC7 back to PC1 is a one-to-one communication, addressed specifically to PC1's MAC address.
    

---

### **Proposed Solution and Analysis (Switch)**

The following answers relate to improving the network. The most logical and standard upgrade is to replace the Hub with a Switch.

---

**14. Provide a suitable solution to address the problem(s) of the network outlined in (Q7).**

- **Answer:** Replace the central Hub with a **Switch**.
    

**15. How does your solution improve the network?**

- **Answer:** A Switch is a more intelligent Layer 2 device that improves the network in several ways:
    
    - **Eliminates Collisions:** It creates a separate collision domain for each port, virtually eliminating collisions.
        
    - **Enables Full-Duplex:** It allows devices to send and receive data simultaneously, doubling the potential bandwidth.
        
    - **Provides Dedicated Bandwidth:** It forwards data only to the intended recipient's port based on MAC addresses, so each port gets dedicated, unshared bandwidth.
        
    - **Improves Security:** Since data is sent only to the destination port, other devices cannot easily intercept the traffic.
        

**16. What topology is the network?**

- **Answer:** Star topology.
    

**17. What topology is your proposed solution?**

- **Answer:** Star topology.
    
- **Explanation:** Replacing the central Hub with a Switch does not change the physical wiring layout. The nodes are still connected to a central device, so the physical topology remains a Star.
    

**18. Give the pros and cons of the topologies in (Q16) and (Q17).**

- **Answer:** Star topologies.
    
    - **Pros:**
        
        - **Reliable:** A single cable failure only affects one node.
            
        - **Scalable:** Easy to add or remove devices without disrupting the network.
            
        - **Easy to Troubleshoot:** Faults can be easily isolated to a specific device or cable.
            
    - **Cons:**
        
        - **Single Point of Failure:** If the central device (Hub or Switch) fails, the entire network goes down.
            
        - **Higher Cable Cost:** Requires more cable than other topologies like Bus or Ring.
            
- Bus Topology
	- **Pros:**
		- **Low Cost & Simple Cabling**: It's one of the cheapest topologies to implement because it requires less cable than others, like a star topology. The setup is straightforward, making it easy to install.
    
		- **Easy to Extend**: You can easily add new devices to the network by simply extending the main cable and tapping into it with a connector.
    
		- **Good for Small Networks**: Its simplicity and low cost make it a practical choice for small, temporary networks where traffic is light.
		
	- **Cons:**
		- **Single Point of Failure**: This is the biggest drawback. If the main backbone cable fails or is broken at any point, the **entire network goes down**.
    
		- **Difficult Troubleshooting**: Locating a fault on the network can be very challenging. Since all devices are on the same cable, it's hard to isolate which device or section of the cable is causing the problem.
    
		- **Performance Issues**: All data travels along the single bus. As you add more devices, the network traffic increases, which can lead to frequent data collisions and a significant slowdown for all users.
    
		- **Termination Required**: The bus must be properly terminated at both ends with a resistor. If a terminator is missing or faulty, signals can bounce back, causing interference and bringing the network down.
    
		- **Security Risks**: All data is sent across the entire bus, so every device on the network can "see" all the traffic. This makes it inherently less secure than a switched network.


**19. Draw the network diagrams for your solution in (Q14).**

- **Answer:** The diagram would look identical to the one provided, with the only change being that the central box would be labeled "**Switch**" instead of "Hub".
    

**20. Explain the multicast process?**

- **Answer:** Multicast is a "one-to-many" communication method. A source sends a single stream of data to a multicast group address. Devices that want to receive this data "subscribe" to that group. Network devices like switches and routers then intelligently forward the multicast traffic only to the ports where subscribed devices are connected, making it much more efficient than broadcasting to everyone. This is commonly used for streaming video or online gaming.
    

**21. How does your solution deal with issue of broadcast?**

- **Answer:** A standard Switch, by itself, **does not reduce broadcast traffic**. A switch still forwards broadcast frames to every port. Therefore, the entire switched network remains a single broadcast domain. To solve the broadcast issue, you would need a more advanced configuration, such as creating **VLANs (Virtual LANs)** on a managed switch or using a Router.
    

**22. How many collision domains is your proposed solution?**

- **Answer:** **10** collision domains.
    
- **Explanation:** In a switched network, every port on the switch is its own collision domain. Since the 10 workstations would each be connected to a separate port, there would be 10 collision domains.
    

**23. How many broadcast domains are there after your proposed solution?**

- **Answer:** **1** broadcast domain.
    
- **Explanation:** Unless VLANs are configured, a single switch operates as one large broadcast domain. It will forward any broadcast frame it receives to all of its ports.
    

**24. How many workstations are there after your proposed solution?**

- **Answer:** 10 workstations.
    
- **Explanation:** The solution only changes the central network device, not the number of end-user computers.
    

**25. What line transmission mode does the proposed solution use?**

- **Answer:** **Full-Duplex**.
    
- **Explanation:** Because a switch creates separate collision domains for each port, the connected devices can send and receive data at the same time. This is a significant performance improvement over the half-duplex mode used with a hub.