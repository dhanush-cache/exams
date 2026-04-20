# Ethical Hacking - Repeated Topics & Cheatsheet

## High Frequency (3 Appearances)
- **Hacktivism**: Using hacking to promote political or social agendas.
    - *Methods*: Website defacement, DoS attacks, data leaks, and doxing.
- **Footprinting**: The initial phase of gathering information to build a profile of a target.
    - *Techniques*: Searching public websites, DNS queries, and social engineering.
- **Authentication**: The process of verifying a user's identity.
    - *Factors*: Something you know (passwords), have (tokens), or are (biometrics).
- **ARP Poisoning / Spoofing**: Sending forged ARP messages to a LAN to link an attacker's MAC address with a legitimate IP.
    - *Goal*: Enables Man-in-the-Middle (MITM) attacks to intercept or modify traffic.
- **Scanning**: Identifying open ports, running services, and vulnerabilities on a target system.
    - *Tools*: Nmap (port scanning), Nessus (vulnerability scanning).
- **Enumeration**: Intrusive process of extracting detailed info like usernames, machine names, and network resources.
- **Web Server Hardening**: Securing a server by reducing its attack surface.
    - *Steps*: Patching, removing unnecessary services, least privilege, and enabling logging.

## Medium Frequency (2 Appearances)
- **Types of Ethical Hacking**:
    - *White Box*: Full knowledge of the target.
    - *Black Box*: No prior knowledge (simulates external attacker).
    - *Grey Box*: Partial knowledge (simulates internal user).
- **Hacker Classes**:
    - *White Hat*: Ethical/Legal hackers.
    - *Black Hat*: Malicious/Illegal hackers.
    - *Grey Hat*: Violate ethics but usually without malicious intent.
    - *Script Kiddies*: Use existing tools without deep understanding.
- **Active and Passive Sniffing**:
    - *Passive*: Listening on a hub-based network (hard to detect).
    - *Active*: Injecting packets to redirect traffic on a switched network (e.g., ARP poisoning).
- **DOS Attack**: Flooding a system to make it unresponsive.
    - *Example*: SYN flood (consuming resources with half-open connections).
- **Smurf Attack**: Spoofing a victim's IP to a network broadcast address so all devices reply to the victim.
- **SQL Injection**: Injecting malicious SQL code into web queries to manipulate a database.
    - *Types*: In-band (Classic), Inferential (Blind), and Out-of-band.
- **Buffer Overflow**: Writing more data to a buffer than it can hold, overwriting adjacent memory.
    - *Types*: Stack-based (common, overwrites return address) and Heap-based.
- **Wireless Sniffing**: Capturing packets on a Wi-Fi network using "monitor mode."
- **Information Gathering**:
    - *Passive*: No direct interaction (Google, Whois).
    - *Active*: Direct interaction (Port scanning, ping sweeps).
- **Password Types**: Static, One-Time Passwords (OTP), Passphrases, and Biometrics.
- **Mutation Techniques**: Used by malware to evade antivirus signatures.
    - *Polymorphic*: Encrypted body with a changing decryption routine.
    - *Metamorphic*: Rewrites its own code structure entirely.
- **Rogue Access Point**: Unauthorized AP installed on a secure network (e.g., Evil Twin).

## Low Frequency (1 Appearance - April 2024 only)
- **Hacking Technology**: Tools for scanning (Nmap), vulnerabilities (Nessus), cracking (John the Ripper), and sniffing (Wireshark).
- **DNS Spoofing Techniques**: Introducing false info into a DNS resolver's cache to redirect users to malicious sites.
- **Session Hijacking**: Taking control of a user's session (e.g., via session sniffing or XSS).
- **Google Hacking**: Using advanced operators (`site:`, `filetype:`, `intitle:`) to find vulnerabilities.
- **WEP (Wired Equivalent Privacy)**: Obsolete Wi-Fi protocol; vulnerable due to weak IV reuse and RC4 cipher flaws.
