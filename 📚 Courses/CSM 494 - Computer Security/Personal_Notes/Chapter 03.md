---
date: 2025-08-23
course: CSM 494 - Computer Security
tags:
  - personal
  - study
  - CSM494
---
### **Introduction to Scanning**

Scanners are essential software tools used in penetration testing to find and fix security weaknesses on both local and remote computers within a network1. A specialized type of scanner, called a

**port scanner**, specifically works by examining the ports on a machine to report whether they are open or closed and, if possible, which application is actively listening on that port2. The main objectives are to understand how these scanners function, their history, the different scanning techniques, and to identify specific scanner tools available3.

---

### **The Evolution of Scanners**

The concept of scanning predates even the ARPANET, where early versions were used to monitor connections between mainframes4. The launch of the internet in the 1970s brought about UNIX-like systems that had virtually no security measures5. Users connected to remote servers by having modems dial specific phone numbers. This practice led to the creation of the

**war dialer**6.

A war dialer is an automated script that instructs a modem to dial a user-defined range of phone numbers to identify which ones connect to a remote computer7. By the early 1980s, with most servers running on UNIX, system administrators began creating their own shell scripts to proactively check for security weaknesses on their networks to prevent hacking8. As the internet became more popular and interconnected, scanners evolved and are now widely available for all popular operating systems9.

---

### **How Scanners Work**

Scanners function by automating the process of checking a network for vulnerabilities10. It's important to note that they are

**not heuristic**; they do not learn or guess but follow a pre-programmed set of steps11. The process involves three main functions:

1. **Connect** to one or more target hosts12.
    
2. **Examine** the target to see which services are running13.
    
3. **Analyze** each running service for any known vulnerabilities14.
    

---

### **Types of Scanning Techniques**

There are several methods a scanner can use to probe a target system.

- **TCP Connect Scanning**: This is a straightforward method where the scanner attempts to complete a full TCP three-way handshake with every port on the target machine15. If a connection is successful, the port is marked as active16. This type of scan doesn't require special user privileges, but it is very noisy and easily detected by nearly all Intrusion Detection Systems (IDS)17.
    
- **Half-Open Scanning (SYN Scan)**: This is a stealthier technique where the scanner does not complete the TCP handshake18. The scanner sends a SYN (synchronize) packet, and if it receives a SYN/ACK (synchronize/acknowledge) response, the port is open19. The scanner then immediately sends an RST (reset) flag to tear down the connection before it's fully established, making it less likely to be logged20. This method requires root or administrator privileges to run21.
    
- **UDP Scanning**: This technique checks the status of UDP ports22. The scanner sends a 0-byte UDP packet to every port on the target23. If a port is closed, the target should reply with an "ICMP unreachable" message24. However, this method is often slow and impractical because most operating systems limit the rate at which these ICMP messages are generated25.
    
- **IP Protocol Scanning**: This scan determines which IP protocols (such as TCP, UDP, ICMP, etc.) are supported by a target host26. It works by sending IP packets for each protocol to the target27. If the scanner receives an "ICMP unreachable" message, it means the target does not use that protocol28.
    
- **Ping Scanning**: This is a basic scan used to determine if a remote host is online and active29. It works by sending ICMP echo request packets (pings) to the target30.
    
- **Stealth Scanning**: This is a general category for scanning techniques designed to avoid detection31. These methods are useful for examining hosts that are protected by firewalls and packet filters, as they aim to prevent the target system from logging the scanning activity32.
    

---

### **Catalog of Common Scanner Tools**

The presentation highlights several well-known scanning tools.

- **Nessus**: Formerly an open-source tool, Nessus is a powerful remote security scanner designed for Unix-like operating systems33. It operates on a client-server model, where the server conducts the scans using a large, plug-in-based database of known vulnerabilities34.
    
- **Nmap (Network Mapper)**: Described as "probably the best all-around network scanner," Nmap is a powerful, flexible, and easy-to-use tool that runs on many operating systems35. Its key advantages include being free, portable, well-documented, and widely supported36. You can check if it's installed on Red Hat Linux using the commands
    
    `rpm -q nmap` and `rpm -q nmap-frontend`37.
    
- **Knmap**: This tool is a graphical user interface (GUI) for Nmap, designed for the KDE desktop on Linux38. However, the project is considered defunct, as it has not been updated since 200239.
    
- **Strobe**: A fast TCP port scanner for BSD and Red Hat Linux, famously developed by Julian Assange40. It is known for its speed in identifying all open ports but is also an older tool with no active development41.
    
- **Cheops**: A port scanner for Linux designed for the GNOME desktop environment42. A significant drawback is that it consumes a very large amount of CPU power, which can slow the host system to a crawl43.
    
- **SARA and SAINT**: These tools are mentioned by name only, without any description44.
    

---

### **Final Summary Points**

- Scanning is a critical step for attackers to discover vulnerabilities, and many of the best tools are open source or freeware45.
    
- In the early days of computing, security flaws were plentiful but not widely known, forcing attackers to check for vulnerabilities manually46. The rise of scanning tools automated this process47.
    
- Scanners can be configured to target a single IP address or an entire range of addresses and are available for all major platforms (UNIX, Windows, Macintosh)48.
    
- **Warning**: Scanning networks that you do not own is risky. If the target server is running an IDS, the activity can be detected, and your Internet Service Provider (ISP) may block your access49.

## **Key Concepts**

-

## **References**

![[ch03.ppt]]
