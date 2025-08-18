---
date: 2025-08-17
course: CSM 478 - Computer Networks
tags:
  - personal
  - study
  - CSM478
---
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