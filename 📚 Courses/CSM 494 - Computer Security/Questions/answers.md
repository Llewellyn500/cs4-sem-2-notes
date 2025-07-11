37. The very first thing you must consider on your network is the way it is connected to the internet and also **a. The operating system and the web server in use**. The security of your operating systems and applications (like a web server) is a fundamental consideration. Vulnerabilities in these components are a primary target for attackers, making their security a top priority.
    
38. Which of the following is a windows post-security installation method **a. Apply all hotfixes patches and updates as a number one priority and also never use passwords entry blank**. Applying security patches and updates is the most critical and universally recommended step to secure any operating system after its initial installation.
    
39. A DOS attack can be prevented by **a. Filtering out frequently appearing patterns on your computer and also create and implement good security policies**. A common defense against a Denial-of-Service (DoS) attack is to use a firewall or an Intrusion Prevention System (IPS) to filter and block traffic patterns associated with the attack. This is part of a broader security policy.
    
40. Software subversion vulnerabilities results from the coding detects such as **c. Use of a buffer overflow**. A buffer overflow is a classic and highly exploitable programming defect that allows an attacker to "subvert" the normal execution flow of a program, often leading to a system compromise.
    
41. In a connection hijacking **a. An attacker desynchronizes a series of packet between the source and destination computer**. In a TCP session hijacking attack, the attacker intercepts the communication and injects packets with incorrect sequence numbers. This causes the legitimate client and server to become desynchronized, allowing the attacker to take control of the session.
    
42. In RIP (routing information protocol) attacks **b. Attacks on RIP change the destination of the data**. An attacker exploiting the Routing Information Protocol (RIP) can send false routing updates to routers on a network. This poisons the routing table, causing traffic to be misdirected to the attacker's machine or to a dead end.
    
43. Some of the timer that are important for TCP/IP security are **d. Connection establishment, FIN_WAIT, TIME_WAIT and KEEP_ALIVE**. These are all standard TCP states or timers that are part of the protocol's state machine and are critical for managing connections securely. For example, `TIME_WAIT` prevents delayed packets from an old connection from interfering with a new one.
    
44. TCP/IP vulnerabilities include **c. TCP SYN attacks and IP spoofing**. Both TCP SYN attacks (e.g., SYN flood) and IP spoofing are fundamental vulnerabilities that exploit the core design of the TCP/IP suite.
    
45. IP security provides **c. Authentication of message integrity**. The IPsec protocol suite is designed to provide secure communication over IP networks. Its core security services include authentication (verifying the identity of the sender) and message integrity (ensuring the data has not been altered in transit).
    
46. Hackers can modify a routing table by **d. Erase all necessary records from the table and then provide the hacker’s own IP address as the default gateway address**. This describes a classic routing table manipulation attack. By injecting false routing information, the attacker can redirect all traffic intended for the outside world to their own machine, acting as a malicious gateway.
    
47. Three ways of stopping a continuous ACK transfer: **b. Losing an ACK, exceeding the Time –To-live, dropping packets**. This is likely referring to a defense against a flood attack. A firewall or intrusion prevention system would:
    

- Identify packets that are part of an attack (e.g., an ACK flood) and choose to `drop packets`.
    
- If a packet is part of a routing loop created by the attacker, its `Time-To-Live` will be `exceeded`, causing it to be discarded.
    

48. Two methods used to prevent session hijacking are **a. Encryption and storm watching**. Encryption (e.g., using HTTPS/SSL/TLS) is the most effective method, as it prevents the attacker from reading or modifying the session data, making a hijacking attack futile. "Storm watching" is an unusual term, but it likely refers to network monitoring for a flood or "storm" of suspicious activity, which is also a defense.
    
49. To prevent a Trojan horse attack **c. Executable file formats should not be open or run unless the source of the file is known**. A Trojan horse relies on being executed by the victim. The most effective prevention is to be suspicious of files from unknown sources and to not open or run them.
    
50. **c. Honey pots** are computer that are either intentionally or unintentionally left vulnerable to an attack by crackers. A honeypot is a decoy system or network designed to attract attackers and gather information about their methods. It is intentionally left vulnerable for this purpose.