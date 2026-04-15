# Ethical Hacking - April 2025 - Answers

## Q1

### a) Define the term Hacktivism and explain Hacker Classes.

**Hacktivism** is a portmanteau of "hacking" and "activism". It refers to the use of computer hacking techniques for political or social causes. Hacktivists target computer systems and networks to disrupt services, steal or leak information, or deface websites to draw attention to their cause. Their motivations are ideological rather than financial.

**Hacker Classes** are categories used to classify hackers based on their motives, skills, and ethics.
*   **Black Hat Hackers:** These are malicious hackers who violate computer security for personal gain (e.g., theft, fraud) or for malicious reasons (e.g., cyber terrorism, espionage). They are the stereotypical "bad guys".
*   **White Hat Hackers:** Also known as ethical hackers, they are security professionals who use their hacking skills to identify security vulnerabilities in systems with the owner's permission. They help organizations improve their security posture.
*   **Grey Hat Hackers:** This is a blend of black and white hat hackers. They may break into systems without permission, but their intent is not malicious. They often discover vulnerabilities and report them to the owner, sometimes requesting a fee for the information.
*   **Script Kiddies:** These are amateur hackers who lack in-depth technical skills. They use pre-written scripts and tools created by others to launch attacks. Their attacks are often unsophisticated and easy to detect.
*   **Hacktivists:** As defined above, they are motivated by political or social agendas.

### b) Describe in detail any one method of Information gathering:

**Footprinting**

Footprinting is the first and most crucial phase of ethical hacking. It is a systematic process of gathering as much information as possible about a target organization and its systems before launching an attack. The goal is to create a complete profile of the target's security posture, including its network infrastructure, employee information, and publicly available data. This information helps the attacker identify potential vulnerabilities and plan their attack strategy.

**Footprinting Techniques:**

1.  **Open-Source Intelligence (OSINT):** This involves gathering information from publicly available sources.
    *   **Search Engines:** Using advanced search operators on Google, Bing, etc., to find sensitive information, employee details, and technical data.
    *   **Social Media:** Mining platforms like LinkedIn, Facebook, and Twitter for employee information, organizational structure, and technologies used.
    *   **Company Website:** Analyzing the website for contact details, employee names, technologies used (e.g., in job postings), and business partners.
2.  **Whois Lookup:** This technique is used to find information about a domain name, such as the domain owner, registration date, expiry date, and DNS servers.
3.  **DNS Enumeration:** This involves querying the Domain Name System (DNS) to gather information about a target's network infrastructure, such as IP addresses, hostnames, and mail servers. Tools like `nslookup` and `dig` are used for this purpose.
4.  **Network Reconnaissance:** This involves identifying the target's network range, active machines, and open ports. Tools like `ping` and `traceroute` are used to map the network path to the target.

By the end of the footprinting phase, the attacker has a blueprint of the target's network, which they can use to launch more targeted attacks in the subsequent phases of hacking.

### c) Write a short note on keystroke logging.

**Keystroke logging**, or **keylogging**, is the act of recording the keys struck on a keyboard, typically covertly, so that the person using the keyboard is unaware that their actions are being monitored. The data recorded can then be retrieved by the person operating the logging program.

Keyloggers can be implemented as either hardware or software:

*   **Hardware Keyloggers:** These are physical devices that are placed between the keyboard and the computer. They are difficult to detect by software because they do not install any software on the target computer. Examples include keyboard adapters and overlays.
*   **Software Keyloggers:** These are programs that run on the target computer. They can be installed by a user or remotely by an attacker. They can be more powerful than hardware keyloggers as they can capture not only keystrokes but also screenshots, clipboard data, and other user activities.

**Purpose of Keylogging:**

*   **Malicious Use:** Attackers use keyloggers to steal sensitive information such as usernames, passwords, credit card numbers, and personal messages.
*   **Legitimate Use:** Keyloggers can be used for legitimate purposes, such as parental control to monitor a child's computer activity, or by employers to monitor employee activity on company-owned computers.

**Detection and Prevention:**

*   **Anti-keylogger software:** These programs are designed to detect and remove software keyloggers.
*   **On-screen keyboards:** Using a virtual keyboard can prevent keyloggers from capturing keystrokes.
*   **Regularly scanning for malware:** Anti-virus and anti-malware software can often detect and remove software keyloggers.

### d) Explain any two common types of Attack.

1.  **Phishing:** Phishing is a type of social engineering attack where an attacker attempts to trick a user into revealing sensitive information, such as usernames, passwords, and credit card details, by masquerading as a trustworthy entity in an electronic communication.

    **How it works:**
    *   The attacker creates a fake website that looks identical to a legitimate one (e.g., a bank's website).
    *   They send an email or a message that appears to be from the legitimate entity, with a link to the fake website.
    *   The message often creates a sense of urgency, for example, by claiming that the user's account has been compromised and they need to log in to fix it.
    *   When the user clicks the link and enters their credentials on the fake website, the attacker captures the information.

    **Prevention:**
    *   Be cautious of unsolicited emails and messages.
    *   Check the sender's email address and the URL of the website carefully.
    *   Enable two-factor authentication (2FA) wherever possible.

2.  **Denial-of-Service (DoS) Attack:** A DoS attack is a cyber-attack in which the perpetrator seeks to make a machine or network resource unavailable to its intended users by temporarily or indefinitely disrupting services of a host connected to the Internet. A Distributed Denial-of-Service (DDoS) attack is a variant of a DoS attack where the attack is launched from multiple compromised computer systems.

    **How it works:**
    *   The attacker floods the target system with a large volume of traffic or requests, overwhelming its resources.
    *   This prevents legitimate users from accessing the service.
    *   Common types of DoS attacks include TCP SYN flood attacks, UDP flood attacks, and ICMP flood attacks.

    **Prevention:**
    *   Using firewalls and intrusion detection systems to filter malicious traffic.
    *   Using a DDoS mitigation service that can absorb and filter large volumes of traffic.
    *   Configuring network hardware to limit the rate of incoming traffic.

### e) State and explain the HTTP Tunneling Technique.

HTTP tunneling is a technique used to bypass firewall restrictions by encapsulating traffic from other protocols within HTTP requests and responses. Many networks restrict traffic to only allow certain protocols, such as HTTP (port 80) and HTTPS (port 443), for web browsing. HTTP tunneling takes advantage of this by making traffic from blocked protocols (like SSH, FTP, or RDP) look like regular web traffic.

**How it works:**

1.  **Client-Side:** A client application on the internal network wants to communicate with a server on the internet using a blocked protocol. The client encapsulates its request (e.g., an SSH command) within the body of an HTTP POST request.
2.  **Firewall Traversal:** The firewall sees a standard HTTP request and allows it to pass through to the internet.
3.  **Server-Side:** The HTTP request reaches a special server on the internet that is designed to understand these tunneled requests. This server extracts the encapsulated data from the HTTP request.
4.  **Forwarding:** The server then forwards the extracted data to the actual destination server using the original, intended protocol (e.g., SSH).
5.  **Response:** The destination server sends its response back to the tunneling server. The tunneling server encapsulates this response within an HTTP response and sends it back to the client. The client's application then extracts the response.

**Uses:**

*   **Bypassing Firewalls:** The most common use is to get around restrictive network policies.
*   **Malicious Use:** Attackers use HTTP tunneling to create a covert channel for C&C (Command and Control) communication with malware inside a compromised network, exfiltrating data without being detected by security systems.

### f) What are the various IP Spoofing techniques?

IP spoofing is the creation of Internet Protocol (IP) packets with a forged source IP address. The purpose is to either hide the identity of the sender or to impersonate another computing system.

**IP Spoofing Techniques:**

1.  **Simple IP Spoofing:** In this basic form, an attacker simply changes the source IP address in the packet header to a different, random, or specific IP address. This is often used in DoS attacks where the attacker doesn't need to see the response packets. The goal is to flood the target without revealing the true source of the attack traffic.

2.  **Man-in-the-Middle (MITM) Attack:** An attacker can use IP spoofing to position themselves between two communicating parties.
    *   The attacker spoofs the IP address of one party to trick the other into sending traffic to the attacker's machine instead.
    *   By also spoofing the other party's IP address, the attacker can intercept, read, modify, and relay the traffic between the two parties, who remain unaware of the attacker's presence. ARP poisoning is a common method to achieve this on a local network.

3.  **Non-Blind Spoofing:** This occurs when the attacker is on the same subnet as the victim. The attacker can see the sequence and acknowledgment numbers of the packets being exchanged between the two parties. This allows the attacker to hijack an existing session by forging packets with the correct sequence numbers, effectively taking over the communication.

4.  **Blind Spoofing:** This is more difficult and occurs when the attacker is on a different network and cannot see the traffic between the victim and the target host. The attacker must guess the correct sequence and acknowledgment numbers to successfully inject data or commands into a TCP session. The attacker sends a series of packets to the target, hoping one of them will have the correct sequence number to be accepted. This is often used to exploit trust relationships between systems (e.g., rlogin).

5.  **IP Fragmentation Attack:** Attackers can send fragmented IP packets that, when reassembled by the target, can bypass security measures like firewalls or Intrusion Detection Systems (IDS). By splitting the malicious payload across multiple small fragments, the IDS may fail to detect the attack signature.

## Q2

### a) Explain the various types of password effective in securing user account.

Effective password security involves creating passwords that are difficult to guess or crack. Here are various types and characteristics of strong passwords:

*   **Complex Passwords:** These passwords combine uppercase letters, lowercase letters, numbers, and special characters (e.g., `P@ssw0rd!`). The complexity makes them resistant to brute-force and dictionary attacks.
*   **Long Passwords (Passphrases):** Instead of a single word, a passphrase is a sequence of words (e.g., `correct-horse-battery-staple`). They are easier for users to remember but are significantly longer, making them computationally very difficult to crack.
*   **One-Time Passwords (OTP):** These passwords are valid for only one login session or transaction. They are often used as a second factor of authentication (2FA). OTPs can be generated using a hardware token or a software application on a smartphone.
*   **Multi-Factor Authentication (MFA):** This is not a type of password but a method of securing accounts that requires more than one method of authentication from independent categories of credentials to verify the user's identity for a login or other transaction. Examples include something you know (password), something you have (OTP token), and something you are (biometrics).

### b) Define Active and Passive sniffing and state its characteristics.

**Sniffing** is the process of capturing and monitoring data packets that pass through a computer network.

**Passive Sniffing:**
*   **Definition:** In passive sniffing, the attacker only listens to the traffic on the network without interacting with it. This is possible on networks that use a hub, where all traffic is broadcast to all devices.
*   **Characteristics:**
    *   It is very difficult to detect because the sniffer does not send any packets on the network.
    *   It is only effective on networks with hubs or when used in conjunction with techniques like ARP poisoning on switched networks.
    *   The sniffer's network interface card (NIC) is put into "promiscuous mode" to accept all packets, not just those addressed to it.

**Active Sniffing:**
*   **Definition:** In active sniffing, the attacker actively injects traffic into the network to enable the sniffing of a switched network. Switched networks only send traffic to the intended recipient, so an attacker must actively intervene to intercept the traffic.
*   **Characteristics:**
    *   It is easier to detect than passive sniffing because the attacker is sending packets on the network.
    *   Common techniques for active sniffing include ARP poisoning, MAC flooding, and DNS spoofing.
    *   The goal is to trick the switch into sending traffic to the attacker's machine.

### c) Describe the ARP poisoning process.

ARP (Address Resolution Protocol) is used to map an IP address to a physical MAC address on a local network. **ARP poisoning** (also known as ARP spoofing) is an attack where an attacker sends forged ARP messages onto a local area network.

**Process:**

1.  **Attacker's Goal:** The attacker's goal is to associate their MAC address with the IP address of another host, such as the default gateway (router). This causes any traffic meant for that IP address to be sent to the attacker instead.
2.  **Sending Forged ARP Responses:** The attacker sends a forged ARP response to the victim machine. This response tells the victim that the MAC address of the gateway is the attacker's MAC address.
3.  **Poisoning the Victim's ARP Cache:** The victim machine receives the forged ARP response and updates its ARP cache with the incorrect MAC address for the gateway.
4.  **Intercepting Traffic:** Now, when the victim tries to send traffic to the gateway (and thus to the internet), it sends it to the attacker's machine instead.
5.  **Man-in-the-Middle:** The attacker can now intercept, inspect, and modify the traffic before forwarding it to the actual gateway. The victim is unaware that their traffic is being intercepted. The attacker can also poison the gateway's ARP cache to intercept the return traffic.

### d) Write a short note on BOT and BOTNET’s.

A **bot** (short for "robot") is a type of software application or script that performs tasks that are simple and repetitive, much faster than a human could. While bots can be used for legitimate purposes (e.g., search engine crawlers), they are often used for malicious purposes. A malicious bot is a compromised computer under the control of a remote attacker.

A **botnet** is a network of these compromised computers, called "bots" or "zombies," that are controlled as a group without the owners' knowledge. The attacker who controls the botnet is known as the "botmaster" or "botherder."

**How it works:**
*   **Infection:** Computers are typically infected with bot malware through phishing emails, malicious websites, or by exploiting vulnerabilities in their software.
*   **Command and Control (C&C):** Once infected, the bots connect to a C&C server, which is a central point of control for the botmaster. The botmaster can then issue commands to the entire botnet.

**Uses of Botnets:**
*   **DDoS Attacks:** Botnets are commonly used to launch large-scale DDoS attacks.
*   **Spamming:** Sending out massive amounts of spam emails.
*   **Click Fraud:** Generating fake clicks on pay-per-click ads.
*   **Information Theft:** Stealing sensitive information from the compromised computers.

### e) Differentiate between spoofing and Hijacking.

| Feature         | Spoofing                                                                    | Hijacking                                                                      |
|-----------------|-----------------------------------------------------------------------------|--------------------------------------------------------------------------------|
| **Definition**  | Impersonating another device or user on a network to hide one's identity.     | Taking control of an existing, active session between two parties.              |
| **Goal**        | To gain access, launch attacks, or bypass access controls by faking an identity. | To monitor, modify, or terminate the communication between two parties.        |
| **Interaction** | Often a one-way attack, especially in blind spoofing or DoS attacks.         | An active, real-time attack that involves intercepting and manipulating a session. |
| **Example**     | An attacker sending packets with a forged source IP address (IP Spoofing).    | An attacker taking over a user's authenticated web session (Session Hijacking). |
| **Analogy**     | Forging a letter with someone else's return address.                         | Intercepting a phone call and continuing the conversation while pretending to be one of the original speakers. |

### f) Explain the types of attack on a Webserver.

Web servers are a common target for attackers due to the valuable data they often hold and their public-facing nature. Common attacks include:

*   **Denial-of-Service (DoS) and Distributed Denial-of-Service (DDoS) Attacks:** As explained earlier, these attacks aim to make the web server unavailable to legitimate users by overwhelming it with traffic.
*   **SQL Injection (SQLi):** If a web application uses a database, an attacker can insert malicious SQL queries into input fields to manipulate the database. This can be used to steal, modify, or delete data.
*   **Cross-Site Scripting (XSS):** An attacker injects malicious scripts into a trusted website. When a user visits the website, the script is executed in their browser. This can be used to steal session cookies, redirect the user to a malicious website, or deface the website.
*   **Directory Traversal (Path Traversal):** This attack allows an attacker to access files and directories that are stored outside the web root folder. By manipulating file paths in the URL, an attacker can access sensitive files like configuration files or system files.
*   **File Inclusion:** This vulnerability allows an attacker to include a file, usually through a script on the web server. This can be a local file on the server (Local File Inclusion) or a remote file from another server (Remote File Inclusion), leading to code execution or information disclosure.

## Q3

### a) State and explain the different Web Application Vulnerabilities.

Web applications are prone to a variety of vulnerabilities that can be exploited by attackers. Some of the most common ones include:

*   **Injection Flaws:** These occur when untrusted data is sent to an interpreter as part of a command or query. The most common is SQL Injection, but others include NoSQL injection, OS command injection, and LDAP injection.
*   **Broken Authentication:** Incorrectly implemented authentication and session management can allow attackers to compromise passwords, keys, or session tokens, or to impersonate other users' identities temporarily or permanently.
*   **Cross-Site Scripting (XSS):** As explained before, XSS allows attackers to execute scripts in the victim's browser, which can hijack user sessions, deface web sites, or redirect the user to malicious sites.
*   **Insecure Deserialization:** This flaw occurs when an application deserializes untrusted data without sufficient verification, leading to remote code execution.
*   **Security Misconfiguration:** This is a very common issue and includes insecure default configurations, incomplete or ad-hoc configurations, open cloud storage, misconfigured HTTP headers, and verbose error messages containing sensitive information.

### b) Describe the User authentication types used to verify User Identity.

User authentication is the process of verifying the identity of a user. The most common authentication methods are based on one or more of the following factors:

*   **Something you know (Knowledge Factor):** This is the most common form of authentication. It relies on the user knowing a secret, such as a password, PIN, or the answer to a security question.
*   **Something you have (Possession Factor):** This type of authentication relies on the user possessing a physical object. Examples include a smart card, a security token (like a YubiKey), or a mobile phone that can receive a one-time password (OTP).
*   **Something you are (Inherence Factor):** This method uses biometric data to verify a user's identity. Examples include fingerprint scans, facial recognition, iris scans, and voice recognition.

**Multi-Factor Authentication (MFA)** combines two or more of these independent authentication factors to create a more secure authentication process. For example, a user might be required to enter a password (something they know) and then use a fingerprint scan (something they are).

### c) Explain the sequence of steps involved in the SQL Injection attack.

A SQL Injection (SQLi) attack is a multi-stage process that allows an attacker to interfere with the queries that an application makes to its database.

**Sequence of steps:**

1.  **Find an Injection Point:** The attacker first needs to find a part of the web application that accepts user input and uses it in a database query. This could be a search box, a login form, or even a parameter in the URL.
2.  **Test for Vulnerability:** The attacker then tests the input field to see if it is vulnerable to SQL injection. This is often done by entering a single quote (`'`) or other special characters to see if it causes a database error. An error message indicates that the application is likely vulnerable.
3.  **Determine the Database Schema:** Once a vulnerability is confirmed, the attacker tries to learn about the database. They can use `UNION` based SQLi to determine the number of columns in the table, the names of tables and columns, and the type of database being used (e.g., MySQL, MSSQL).
4.  **Extract Data:** With knowledge of the database schema, the attacker can now craft malicious SQL queries to extract sensitive data from the database. This could include usernames, passwords, credit card numbers, or other personal information. The `UNION` operator is commonly used to append the results of the attacker's query to the legitimate query.
5.  **Escalate Privileges (Optional):** In some cases, an attacker might be able to use SQL injection to gain a foothold on the underlying server. For example, on some database systems, they might be able to write files to the server or execute operating system commands, leading to a full system compromise.

### d) State and explain the Mutation Techniques.

In the context of ethical hacking, mutation refers to the techniques used by malware authors to modify their code to evade detection by signature-based antivirus software. The goal is to create variants of the malware that have the same functionality but a different binary signature.

**Mutation Techniques:**

*   **Polymorphic Code:** Polymorphic malware changes its code with each infection. It uses an encryption key to encrypt the main body of the malware, and the decryption routine is modified with each new copy. This means that the malware looks different on each infected system, making it difficult for antivirus software to create a single signature to detect it.
*   **Metamorphic Code:** Metamorphic malware is even more advanced. Instead of just encrypting its code, it completely rewrites itself with each new infection. The new code has the same functionality but a different structure and sequence of instructions. This makes it extremely difficult to detect with signature-based methods.
*   **Oligomorphic Code:** This is a simpler form of mutation where the malware has a limited number of different decryption routines that it can use. This is easier to create than polymorphic code but also easier to detect.
*   **Code Obfuscation:** This involves making the code difficult for humans and security tools to understand. Techniques include inserting junk code, renaming variables, and using complex control flows.

### e) Explain the term Wireless Hacking.

Wireless hacking is the act of exploiting vulnerabilities in wireless networks (like Wi-Fi) to gain unauthorized access to the network and the data transmitted over it. Since wireless networks broadcast their signals through the air, they are inherently more vulnerable to eavesdropping and attack than wired networks.

**Common Wireless Hacking Techniques:**

*   **Cracking Wi-Fi Passwords:** Attackers can capture the WPA/WPA2 handshake that occurs when a device connects to the network and then use brute-force or dictionary attacks to crack the password offline.
*   **Evil Twin Attack:** An attacker sets up a rogue Wi-Fi access point that appears to be a legitimate one (e.g., "Free_Airport_Wi-Fi"). When users connect to the evil twin, the attacker can intercept all their traffic.
*   **Packet Sniffing:** If the wireless network is unencrypted or uses weak encryption (like WEP), an attacker can easily capture and read all the data being transmitted over the network.
*   **Deauthentication Attack:** An attacker can send deauthentication frames to a user's device, disconnecting them from the Wi-Fi network. This can be used to force the user to reconnect, allowing the attacker to capture the WPA/WPA2 handshake.
*   **Jamming:** Attackers can use a device to broadcast noise on the same frequency as the Wi-Fi network, disrupting the service for all users.

### f) Describe the function of Penetration testing Automated tools.

Penetration testing (pen testing) is a simulated cyber attack against a computer system to check for exploitable vulnerabilities. Automated penetration testing tools are software applications that help automate parts of this process, making it faster and more efficient.

**Functions of Automated Pen Testing Tools:**

*   **Scanning and Reconnaissance:** These tools can automatically scan a network or web application to discover hosts, open ports, running services, and potential vulnerabilities. Examples include Nmap for network scanning and Nessus for vulnerability scanning.
*   **Exploitation:** Some tools can automatically attempt to exploit the vulnerabilities they find. For example, Metasploit is a popular framework that contains a large database of exploits and can be used to launch attacks against vulnerable systems.
*   **Web Application Analysis:** Tools like Burp Suite and OWASP ZAP are specifically designed for testing web applications. They can crawl a website, identify vulnerabilities like SQL injection and XSS, and provide tools for manually testing them.
*   **Password Cracking:** Tools like John the Ripper and Hashcat can be used to crack password hashes that have been obtained during a penetration test.
*   **Reporting:** Many automated tools can generate detailed reports of their findings, including a list of vulnerabilities, their severity, and recommendations for remediation. This helps streamline the reporting phase of a penetration test.

While automated tools are powerful, they are not a replacement for manual penetration testing. A skilled human tester is needed to interpret the results, find business logic flaws, and perform more complex attacks that automated tools might miss.

## Q4

### a) Define the CIA triad.

The CIA triad is a model designed to guide policies for information security within an organization. The three letters stand for Confidentiality, Integrity, and Availability. These three principles are considered the most important components of security.

*   **Confidentiality:** This principle ensures that sensitive information is not disclosed to unauthorized individuals, entities, or processes. It is about preventing the unauthorized reading of data. Measures to ensure confidentiality include encryption, access control lists, and data classification.
*   **Integrity:** This principle ensures that data is not altered or destroyed in an unauthorized manner. It is about maintaining the accuracy and completeness of data. Measures to ensure integrity include hashing, digital signatures, and version control.
*   **Availability:** This principle ensures that systems, applications, and data are accessible to authorized users when they need them. It is about preventing the disruption of services. Measures to ensure availability include redundancy, backups, and disaster recovery plans.

### b) Mention the different phases of Ethical Hacking.

Ethical hacking is a structured process that can be broken down into several distinct phases. These phases are:

1.  **Reconnaissance (Footprinting):** This is the information gathering phase where the ethical hacker collects as much information as possible about the target system. This can be done passively (without directly interacting with the target) or actively.
2.  **Scanning:** In this phase, the ethical hacker uses tools to scan the target network and systems for open ports, running services, and potential vulnerabilities.
3.  **Gaining Access (Exploitation):** This is the phase where the ethical hacker attempts to exploit the vulnerabilities found during the scanning phase to gain access to the target system. This could involve using an exploit, cracking a password, or using social engineering.
4.  **Maintaining Access:** Once access is gained, the ethical hacker may try to maintain that access for future use. This could involve installing a backdoor or a rootkit. In a real attack, this phase allows the attacker to continue to access the system.
5.  **Covering Tracks (Clearing Tracks):** In this final phase, the ethical hacker attempts to remove all evidence of their presence on the system to avoid detection. This could involve deleting logs, hiding files, and removing any tools they used. The purpose of this phase in ethical hacking is to demonstrate how a real attacker would cover their tracks.

### c) What is meant by the term Smurf attack?

A Smurf attack is a type of Distributed Denial-of-Service (DDoS) attack in which an attacker attempts to flood a target system with a large number of ICMP (Internet Control Message Protocol) echo requests (pings).

**How it works:**

1.  **Spoofing the Source IP:** The attacker sends a large number of ICMP echo requests to a network's broadcast address. The source IP address of these packets is spoofed to be the IP address of the target victim.
2.  **Broadcasting the Requests:** When the router receives these requests on the broadcast address, it forwards them to all the hosts on the network.
3.  **Flooding the Victim:** Each host on the network receives the echo request and sends an ICMP echo reply to the spoofed source IP address, which is the victim's IP address.
4.  **Amplification:** If the network has a large number of hosts, this can result in a massive flood of traffic to the victim's system, overwhelming its resources and making it unavailable. This is known as an amplification attack because a single packet from the attacker can generate hundreds or thousands of responses.

Modern networks are generally configured to not forward ICMP requests sent to a broadcast address, so this attack is less common today.

### d) Mention the purpose of Web Hardening.

Web hardening, or web server hardening, is the process of securing a web server and its associated software to reduce its attack surface and protect it from attack. The goal is to make the server more resilient to both automated and targeted attacks.

**The purpose of web hardening includes:**

*   **Reducing the Attack Surface:** This involves disabling unnecessary services, ports, and software features that are not required for the web application to function. The fewer components are running, the fewer potential vulnerabilities an attacker can exploit.
*   **Preventing Unauthorized Access:** This includes implementing strong access control policies, using strong passwords, and configuring file permissions to prevent unauthorized users from accessing sensitive files and directories.
*   **Protecting against Common Attacks:** Hardening involves configuring the web server and application to defend against common attacks like SQL injection, XSS, and directory traversal. This can include using a web application firewall (WAF).
*   **Minimizing Information Leakage:** This involves configuring the server to not reveal sensitive information in error messages or server banners, which could be useful to an attacker.
*   **Maintaining System Integrity:** This includes keeping the server's operating system and all software up to date with the latest security patches to protect against known vulnerabilities.

### e) Define XSS.

**Cross-Site Scripting (XSS)** is a type of web application vulnerability that allows an attacker to inject malicious scripts (usually JavaScript) into web pages viewed by other users. The user's browser, trusting the website, executes the script.

**How it works:**
The vulnerability occurs when a web application takes user-supplied data and includes it in its output without properly validating or encoding it.

There are three main types of XSS:

1.  **Stored XSS (Persistent XSS):** The malicious script is permanently stored on the target server, such as in a database, in a comment field, or in a forum post. When a user visits the affected page, the script is retrieved from the server and executed in their browser.
2.  **Reflected XSS (Non-Persistent XSS):** The malicious script is embedded in a URL and is reflected off the web server to the victim's browser. This is often delivered to the victim via an email or a chat message. When the victim clicks the link, the script is executed in their browser.
3.  **DOM-based XSS:** This is an advanced type of XSS where the vulnerability is in the client-side code rather than the server-side code. The attack payload is executed as a result of modifying the DOM (Document Object Model) "environment" in the victim's browser.

**Impact:**
XSS can be used to steal session cookies, hijack user accounts, redirect users to malicious websites, or perform other malicious actions on behalf of the user.

### f) Describe the term passive Spraying.

**Password spraying** is a type of brute-force attack where an attacker attempts to gain unauthorized access to a large number of accounts with a few commonly used passwords. Instead of trying many passwords for one account, the attacker tries one password against many accounts.

**Passive spraying** is a variation of this attack that is designed to be slow and stealthy to avoid detection.

**How it works:**
*   **Gathering Usernames:** The attacker first compiles a list of valid usernames for the target organization. This can be done through OSINT, social media, or by exploiting other vulnerabilities.
*   **Choosing Common Passwords:** The attacker then chooses a few very common or weak passwords, such as "Password123", "Winter2024", or the company's name followed by a year.
*   **Slow and Low Attack:** The attacker then tries to log in to each of the usernames with one of the chosen passwords. They do this very slowly, with long intervals between login attempts, to avoid triggering account lockout policies or alerting security monitoring systems.
*   **Rotating Passwords:** After trying one password against all the usernames, the attacker will wait for a period of time (hours or even days) before trying the next password in their list.

The "passive" nature of the attack refers to its low and slow approach, which makes it much harder to detect than a traditional brute-force attack that generates a lot of noise.
