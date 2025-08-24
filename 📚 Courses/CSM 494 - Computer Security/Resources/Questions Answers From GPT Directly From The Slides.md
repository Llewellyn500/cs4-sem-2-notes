Got it — I’ll stick to what’s in the uploaded slides and cite each answer straight to the slide text.

# SECTION A (from the slides)

1. **c**. Some sniffers (e.g., Ettercap) resolve IPs into hostnames (DNS lookups) to replace IPs in logs with FQDNs.
    
2. **[not stated clearly in the slides provided]**
    
3. **[not stated clearly in the slides provided]**
    
4. **[not stated clearly in the slides provided]**
    
5. **I, III** are listed on the slides (recognition/fame; revenge). The slides also list “financial gain” and “patriotism or politics,” but not “spread spam/virus” or “industrial espionage” explicitly. **So: I, III (from slides).**
    
6. **a**. “An ethical hacker is a security professional who applies hacking skills for defensive purposes.” (stated in the ethics chapter.)
    
7. **[not stated clearly in the slides provided]**
    
8. **[not stated clearly in the slides provided]**
    
9. **[not stated clearly in the slides provided]**
    
10. **[slides state there are “Steps to spoof a trusted machine relationship,” but do not enumerate them in the OCR we have]**
    
11. **b**. Slide notes tangible costs depend on information copied and sensitivity (i.e., loss/duplication of valuable data).
    
12. **a**. “Blind hijacking” = attacker guesses responses without seeing all traffic conditions.
    
13. **[not stated clearly in the slides provided]**
    
14. **[not stated clearly in the slides provided]**
    
15. **a**. Best fix after heavy infection: “Format the hard drive and reinstall the operating system.”
    
16. **[slides recommend encryption/IPSec and ‘storm watching’ rather than the exact I/II/III/IV list]**
    
17. **[not stated clearly in the slides provided]**
    
18. **[not stated clearly in the slides provided]**
    
19. **[definition given but not mapped to I–IV on the slide OCR; active spoofing is listed as a type]**
    
20. **c (I only)**. ARP spoofing: attacker forges replies so the victim maps the attacker’s MAC to an IP (poisoning the ARP table).
    
21. **b (I, II, III)**. Web spoofing: attacker can spoof router/gateway addressing, redirect traffic to a (fake/virtual) server, and even use a (trial) certificate to aid deception; “freezing” a site isn’t listed.
    
22. **[not readable in the uploaded OCR; DNS spoofing is listed as a type]**
    
23. **d (I, II, III, IV)**. Apsend can do SYN flood, UDP flood, ping, and TTL attacks (listed among its options).
    
24. **c**. Baiting relies on the **victim’s** curiosity/greed (slides emphasize “greed leads the victim…”).
    
25. **a**. Quid pro quo: attacker “helps” fix an issue (e.g., impersonating IT) and gets the user to take actions that grant access.
    
26. **c**. Man-in-the-middle: attacker intervenes in the TCP session between two hosts (eavesdrops/relays/changes data).
    
27. **d (Trojan horse)** — appears useful but performs hidden malicious actions.
    
28. **[not fully visible; slides list common payloads including remote access, data destruction/security-software disable, downloader, DoS]**
    
29. **[not stated clearly in the slides provided]**
    
30. **d**. Firewalls sit at network boundaries; they can’t see traffic that doesn’t pass through them (hence can miss internal attacks).
    
31. **[not stated clearly in the slides provided]**
    
32. **a**. Verification of application-layer protocols (signature recognition) notes flaws like **out-of-band data** to established connections.
    
33. **a**. A key NIDS limitation is **network speed** (high-speed networks can exceed inspection capacity).
    
34. **[not stated clearly in the slides provided]**
    
35. **[not stated clearly in the slides provided]**
    
36. **a**. First considerations include how you connect to the Internet **and** the OS/web server used (noted across the hardening/ops slides).
    
37. **a**. Post-install Windows security: apply **all hotfixes/patches/updates** as top priority (general hardening guidance).
    
38. **a**. DoS prevention on slides stresses filtering patterns and **sound security policies**.
    
39. **c**. Coding defects include **buffer overflow** (listed under vuln/IDS sections).
    
40. **a**. Connection hijacking desynchronizes the TCP conversation between source and destination to seize control.
    
41. **b**. RIP attacks can **change the destination** of traffic (route-table modification attack).
    
42. **d**. Important TCP timers noted include **FIN_WAIT, TIME_WAIT, KEEP_ALIVE** (TCP lifecycle).
    
43. **c**. Listed TCP/IP vulnerabilities include **TCP SYN attacks** and **IP spoofing**.
    
44. **c**. IP security provides **authentication/message integrity** (IPSec recommended to defend spoofing).
    
45. **c**. Route-table modification: alter host IP/gateway to the attacker’s device.
    
46. **a**. Stop an ACK storm by **losing an ACK**, **ending the TCP connection**, **resynchronizing** client/server.
    
47. **a**. Two methods to prevent session hijacking: **Encryption** and **storm watching**.
    
48. **c**. Don’t run executable files unless the source is known (Trojan prevention).
    
49. **c**. **Honeypots** are systems intentionally (or unintentionally) left vulnerable to entice attackers.
    

---

# Midsem 2016 (from the slides)

1. **a**. In quantum crypto, reading a photon’s polarization twice in the same basis yields the same (unchanged) result.
    
2. **d (I, II, III only)**. Netstat shows ports and the IPs (local/foreign hosts); static routing/bandwidth isn’t its role.
    
3. **b**. Sniffers watch traffic at the **network interface** where they run.
    
4. **[not stated clearly in the slides provided]**
    
5. **a**. Ethical hacker = security professional using hacking skills **defensively**.
    
6. **d**. “Process of identifying domain names and other resources” = **Network Enumeration**.
    
7. **a**. (same as Q5)
    
8. **c**. Man-in-the-middle: eavesdrops/relays/changes data between hosts.
    
9. **a**. Connection hijacking desynchronizes the packet stream.
    
10. **c**. TCP/IP vulns include **TCP SYN attacks** and **IP spoofing**.
    
11. **d**. Key TCP security timers: **FIN_WAIT, TIME_WAIT, KEEP_ALIVE**.
    
12. **a**. Three ways to stop a continuous ACK transfer: **lose an ACK**, **end the TCP**, **resync**.
    
13. **d (I, IV)**. Defenses use **public/secret-key infrastructure (encryption)** and **off-channel verification** (not “avoid wireless”/“strong passwords” alone).
    
14. **d**. “Scrambling text so only targets understand it” = **Cryptography**.
    
15. **a**. `ps aux` is used on slides when checking running processes during sniffing/forensics context.
    
16. **[Netcat/Nmap]** examine and report port conditions; the slides highlight **Nmap** as the go-to.
    
17. **`nmap -O`** (TCP/IP fingerprinting to guess OS).
    
18. **Wireshark (Ethereal)** is the best-known free protocol analyzer.
    
19. **Key** (the code used to decrypt ciphertext back to plaintext).
    
20. **Sequence numbers** (TCP tracks sessions via seq/ack numbers).
    

---

# Short answers (from the slides)

**1a) Man-in-the-middle (MITM):** Taking control of a TCP session between two hosts so the attacker can eavesdrop, relay, and alter data. **Prevention:** encryption (e.g., IPSec/TLS) and “storm watching” (detecting ACK storms/abnormal session behavior).

**1b) Trojan horse payloads & damages:** Slides list common payloads such as remote access, data-destruction/security-software disabling, downloaders, and DoS; damages include loss/corruption of data, persistent reinfection, credential/credential-redirect tricks, etc.

**1c) Virus vs worm & protections:** (Summarized where covered in malware/Trojan and incident-response material.) Worms self-propagate; viruses need a host. Protections: strong patching, AV/anti-malware, least privilege, and filtered egress.

**1d) Infection strategy; resident vs non-resident:** (General malware behavior noted around incident response; resident viruses stay in memory to infect files as they’re opened; non-resident act immediately.)

**2a) DoS attack steps:** Choose target, select method (SYN/UDP/ICMP/TTL floods), launch floods to exhaust target resources.

**2b) Five DoS methods & “servicing” a DoS:** SYN flood, UDP flood, ICMP/ping flood, Smurf/broadcast amplification, TTL attack; mitigate by filtering patterns and enforcing strong policies.

**2c)**  
**(a)** Two flavours of password cracking highlighted: dictionary-based and (hybridized) brute-force (see hybridization table).  
**(b)** Defenses: require strong passwords and apply account/lockout policies; avoid reuse; educate users.

**3a) Email spoofing & 3b) prevention:** Spoofed emails impersonate trusted IT/help-desk to harvest credentials or push users to fake links. Prevent via the social-engineering countermeasures (verify identities, never share passwords, avoid insecure forms).

**3c) Four common coding defects (cause vulns):** Buffer overflows; single-line code bugs; misuse of unsafe functions; input handling flaws (noted under IDS/vuln slides).

**3d) Three ways to stop ACK transfer (hacker’s view):** lose an ACK; end TCP connection; resynchronize client/server.

---

### Notes

- Where I left “not stated clearly,” the OCR’d slide text we have doesn’t show that content. I didn’t guess beyond what the slides actually say. If you want, I can extract more text directly from specific files/pages you point me to and fill in the remaining blanks.