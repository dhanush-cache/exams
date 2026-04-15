# Ethical Hacking - April 2024 - Answers

## Q1
a) Explain the Types of Ethical Hacking.  
**Answer:** Ethical hacking can be categorized based on the knowledge and access provided to the ethical hacker.
    *   **White Box Hacking:** The hacker has full knowledge of the target system, including source code, network diagrams, and credentials. This allows for a comprehensive internal security assessment.
    *   **Black Box Hacking:** The hacker has no prior knowledge of the target system and must discover vulnerabilities from an external perspective, similar to a real-world attacker.
    *   **Grey Box Hacking:** The hacker has partial knowledge of the target system, such as user-level access or some network information. This simulates an attack from an internal user with limited privileges.

b) Explain Hacking Technology and its types in detail.  
**Answer:** Hacking technology refers to the tools and techniques used to compromise systems.
    *   **Network Scanners:** Tools like Nmap are used to discover hosts and services on a network, creating a map of the network and identifying potential attack vectors.
    *   **Vulnerability Scanners:** Tools like Nessus or OpenVAS scan systems for known vulnerabilities, such as unpatched software or misconfigurations.
    *   **Password Crackers:** Tools like John the Ripper or Hashcat are used to recover passwords from stolen password hashes using techniques like brute-force, dictionary attacks, and rainbow tables.
    *   **Sniffers:** Tools like Wireshark capture and analyze network traffic, allowing attackers to intercept sensitive information like passwords and session cookies.
    *   **Exploitation Frameworks:** Frameworks like Metasploit provide a collection of exploits for known vulnerabilities, allowing hackers to easily compromise systems.

c) Define Hacktivism and explain ways to manifest it.  
**Answer:** Hacktivism is the use of hacking techniques to promote a political or social agenda. Hacktivists target organizations they oppose to disrupt their operations, steal and leak data, or deface their websites.
    *   **Website Defacement:** Hacktivists replace the content of a website with their own message.
    *   **Denial-of-Service (DoS) Attacks:** Hacktivists flood a target's servers with traffic, making their services unavailable to legitimate users.
    *   **Data Theft and Leaks:** Hacktivists steal sensitive information from a target and leak it to the public to damage the target's reputation or expose wrongdoing.
    *   **Doxing:** Hacktivists publish private information about individuals online to harass or intimidate them.

d) Explain any 5 Hacker Classes.  
**Answer:** Hackers can be classified based on their motives and ethics.
    *   **White Hat Hackers (Ethical Hackers):** Security professionals who use their skills to help organizations improve their security. They have permission to hack systems and report their findings.
    *   **Black Hat Hackers (Crackers):** Malicious hackers who break into systems for personal gain or to cause damage. Their activities are illegal.
    *   **Grey Hat Hackers:** Hackers who may violate laws or ethical standards, but not for malicious purposes. They might hack a system and then offer to fix the vulnerability for a fee.
    *   **Script Kiddies:** Inexperienced hackers who use tools and scripts created by others to attack systems. They often lack a deep understanding of the underlying technology.
    *   **Hacktivists:** Hackers who use their skills to promote a political or social agenda.

e) What are the ways to conduct Ethical Hacking.  
**Answer:** Ethical hacking is conducted systematically to ensure all vulnerabilities are found and reported.
    *   **Reconnaissance:** Gathering information about the target system, such as IP addresses, domain names, and employee information. This can be passive (e.g., searching online) or active (e.g., scanning the network).
    *   **Scanning:** Using tools to identify open ports, running services, and potential vulnerabilities on the target system.
    *   **Gaining Access:** Exploiting vulnerabilities to gain access to the target system. This could involve using a known exploit, cracking a password, or tricking a user into running malicious code.
    *   **Maintaining Access:** Installing backdoors or other tools to maintain access to the compromised system for future use.
    *   **Covering Tracks:** Removing evidence of the hack, such as log files, to avoid detection.
    *   **Reporting:** Documenting the vulnerabilities found and providing recommendations for fixing them.

f) Write a short note on foot printing.  
**Answer:** Footprinting is the first phase of ethical hacking and involves gathering as much information as possible about a target organization. This information is used to build a profile of the target and identify potential attack vectors. The goal is to create a map of the organization's network, systems, and personnel. Techniques include searching public websites, using search engines, querying DNS records, and using social engineering. The more information gathered during footprinting, the more likely a successful attack becomes.

## Q2
a) Explain Active and Passive Sniffing.  
**Answer:**
    *   **Passive Sniffing:** This is done on a network with a hub. In a hub-based network, all traffic is sent to all ports, so a sniffer can simply listen to all the traffic passing through. The sniffer does not need to inject any packets into the network, making it very difficult to detect.
    *   **Active Sniffing:** This is done on a network with a switch. Switches are smarter than hubs and only send traffic to the intended recipient. To sniff on a switched network, the attacker must actively inject packets into the network to redirect traffic to their own machine. Techniques like ARP poisoning are used for active sniffing. Because the attacker is sending packets, active sniffing is easier to detect than passive sniffing.

b) Explain ARP Poisoning in Detail.  
**Answer:** ARP (Address Resolution Protocol) poisoning is a type of active sniffing attack where an attacker sends forged ARP messages onto a local area network. This tricks other devices on the network into sending their traffic to the attacker's machine instead of the legitimate destination. The attacker can then intercept, modify, or drop the traffic. For example, an attacker could poison the ARP cache of a victim's computer to redirect traffic destined for the network's gateway to the attacker's machine. This would allow the attacker to perform a man-in-the-middle attack and intercept all of the victim's internet traffic.

c) Explain DNS Spoofing Techniques in detail.  
**Answer:** DNS spoofing, or DNS cache poisoning, is an attack where an attacker introduces false information into a DNS resolver's cache. This causes the resolver to return an incorrect IP address for a domain name, redirecting users to a malicious website.
    *   **Man-in-the-Middle Attack:** The attacker intercepts a user's DNS query and responds with a forged DNS response containing a malicious IP address.
    *   **DNS Server Compromise:** The attacker compromises a DNS server and modifies its records to point to malicious IP addresses.
    *   **Cache Poisoning:** The attacker sends a large number of forged DNS responses to a DNS resolver, hoping that one of them will be accepted and cached.

d) Explain the working of DOS attack in detail.  
**Answer:** A Denial-of-Service (DoS) attack is an attempt to make a machine or network resource unavailable to its intended users. This is typically done by flooding the target with a large amount of traffic or by sending malformed requests that cause the target to crash. For example, in a SYN flood attack, the attacker sends a rapid succession of SYN requests to a target's system in an attempt to consume enough server resources to make the system unresponsive to legitimate traffic. The attacker does not complete the three-way handshake, leaving the server with a large number of half-open connections.

e) Explain Smurf attack in detail.  
**Answer:** A Smurf attack is a type of DoS attack in which an attacker sends a large number of ICMP echo requests (pings) to a network's broadcast address, with the source IP address spoofed to be the victim's IP address. This causes all the devices on the network to reply to the victim's machine, overwhelming it with traffic and making it unavailable. The network acts as an amplifier, as a single ping from the attacker can result in hundreds of replies bombarding the victim.

f) Explain types of Session Hijacking.  
**Answer:** Session hijacking is an attack where an attacker takes control of a user's session to gain unauthorized access to a system.
    *   **Session Sniffing:** The attacker uses a packet sniffer to capture the user's session cookie as it is transmitted over the network. This is most effective on unencrypted networks.
    *   **Cross-Site Scripting (XSS):** The attacker injects a malicious script into a website that is then executed by the victim's browser. The script can steal the victim's session cookie and send it to the attacker.
    *   **Session Fixation:** The attacker tricks the user into using a session ID that the attacker already knows. When the user logs in, the attacker can use the same session ID to access the user's account.
    *   **Man-in-the-Browser Attack:** The attacker infects the user's browser with a Trojan horse that can intercept and modify the user's traffic, including session cookies.

## Q3
a) Explain methods involved in Google Hacking.  
**Answer:** Google hacking, also known as "Google dorking," involves using advanced Google search operators to find security vulnerabilities and sensitive information.
    *   `site:`: Restricts the search to a specific website.
    *   `inurl:`: Searches for a specific string in the URL.
    *   `intitle:`: Searches for a specific string in the page title.
    *   `filetype:`: Searches for a specific file type, such as `log` or `pwd`.
    *   `intext:`: Searches for a specific string in the page content.
    *   By combining these operators, an attacker can find things like error messages that reveal sensitive information, files containing usernames and passwords, and vulnerable web applications. For example, `site:example.com filetype:log intext:password`.

b) Define the term Authentication and its types.  
**Answer:** Authentication is the process of verifying the identity of a user or system. It ensures that a user is who they claim to be.
    *   **Something you know (Knowledge Factor):** This is the most common type of authentication and includes things like passwords and PINs.
    *   **Something you have (Possession Factor):** This includes things like security tokens, smart cards, and mobile phones.
    *   **Something you are (Inherence Factor):** This includes biometric authentication methods like fingerprint scans, facial recognition, and iris scans.
    *   **Multi-factor authentication (MFA)** combines two or more of these types to provide stronger security.

c) Define SQL injection and name its types.  
**Answer:** SQL injection is a web security vulnerability that allows an attacker to interfere with the queries that an application makes to its database. It allows an attacker to view data that they are not normally able to retrieve. This might include data belonging to other users, or any other data that the application itself is able to access. In many cases, an attacker can modify or delete this data, causing persistent changes to the application's content or behavior.
    *   **In-band SQLi (Classic SQLi):** The attacker uses the same communication channel to launch the attack and gather results. The two most common types of in-band SQLi are Error-based SQLi and Union-based SQLi.
    *   **Inferential SQLi (Blind SQLi):** The attacker sends data payloads to the server and observes the response and behavior of the server to learn about its structure. The two types of inferential SQLi are Boolean-based (content-based) SQLi and Time-based SQLi.
    *   **Out-of-band SQLi:** The attacker can only exfiltrate data through a different channel (e.g., DNS or HTTP requests to an attacker-controlled server).

d) Explain Buffer Overflow and its types.  
**Answer:** A buffer overflow is a vulnerability where a program, while writing data to a buffer, overruns the buffer's boundary and overwrites adjacent memory locations. This can be triggered by inputs that are designed to execute code, or it can be a result of a programming error. Attackers can exploit buffer overflows to corrupt data, crash the program, or execute arbitrary code.
    *   **Stack-based Buffer Overflow:** This is the most common type of buffer overflow. The attacker sends data to a program that is larger than the buffer on the stack. This overwrites the return address, allowing the attacker to redirect the program's execution to their own malicious code.
    *   **Heap-based Buffer Overflow:** This occurs in the heap data area. The attacker overwrites data in the heap, which can lead to arbitrary code execution or other security issues. These are generally harder to exploit than stack-based overflows.

e) Explain WEP in detail.  
**Answer:** WEP (Wired Equivalent Privacy) is a security protocol for Wi-Fi networks. It was introduced in 1999 and was intended to provide the same level of security as a wired network. However, WEP has been found to have serious security flaws and is no longer considered secure. WEP uses the RC4 stream cipher for confidentiality, and the CRC-32 checksum for integrity. The main weakness of WEP is its use of a short, static, and reused initialization vector (IV), which makes it vulnerable to statistical attacks that can recover the WEP key. Tools like Aircrack-ng can crack a WEP key in minutes. WPA and WPA2 were developed to address the weaknesses in WEP.

f) Explain the working of wireless sniffing.  
**Answer:** Wireless sniffing is the process of capturing and analyzing traffic on a wireless network. This is done using a wireless network adapter that is put into "monitor mode," which allows it to capture all wireless packets within its range, not just the ones addressed to it. The captured packets can then be analyzed using a packet sniffer like Wireshark. An attacker can use wireless sniffing to intercept sensitive information like usernames, passwords, and credit card numbers if the traffic is not encrypted. If the traffic is encrypted with WEP or a weak WPA passphrase, the attacker may be able to crack the encryption and decrypt the traffic.

## Q4
a) Explain the methods to perform information Gathering.  
**Answer:** Information gathering, or reconnaissance, is the first step in an attack.
    *   **Passive Reconnaissance:** Gathering information without directly interacting with the target. This includes searching public records, news articles, and social media. Tools like Google, Whois, and NSlookup are used.
    *   **Active Reconnaissance:** Directly interacting with the target to gather information. This includes port scanning, network mapping, and vulnerability scanning. Tools like Nmap, Nessus, and OpenVAS are used.
    *   **Social Engineering:** Tricking employees into revealing sensitive information. This can be done through phishing emails, phone calls, or in person.

b) Define Password and its types.  
**Answer:** A password is a secret word or string of characters used to confirm a user's identity.
    *   **Static Passwords:** The most common type of password. The user creates a password and uses it for an extended period.
    *   **One-Time Passwords (OTP):** Passwords that are valid for only one login session or transaction. They are often generated by a hardware token or a mobile app.
    *   **Passphrases:** A sequence of words or other text that is easy to remember but hard to guess. They are generally more secure than traditional passwords.
    *   **Biometric Passwords:** Using a physical characteristic to authenticate, such as a fingerprint, face, or iris.

c) Explain Mutation Techniques.  
**Answer:** Mutation techniques are used by malware authors to evade detection by antivirus software. The malware's code is changed slightly with each new infection, while keeping the malware's functionality the same. This makes it difficult for signature-based antivirus software to detect the malware, as the signature is constantly changing.
    *   **Polymorphic Code:** The malware uses an encryption key to encrypt its main body, and the decryption routine is changed with each infection.
    *   **Metamorphic Code:** The malware rewrites its own code with each infection, changing its structure and instruction sequence. This is more advanced and difficult to detect than polymorphic code.

d) Define the terms (i) Scanning (ii) Enumeration.  
**Answer:**
    *   **(i) Scanning:** Scanning is the process of using tools to identify open ports, running services, and potential vulnerabilities on a target system. It is a form of active reconnaissance. The goal of scanning is to create a profile of the target system that can be used to plan an attack. Tools like Nmap are commonly used for scanning.
    *   **(ii) Enumeration:** Enumeration is the process of extracting more detailed information from a target system, such as usernames, machine names, network resources, and services. This is a more intrusive phase than scanning and involves making active connections to the target system. The goal of enumeration is to find potential attack vectors.

e) What is Web Server Hardening?  
**Answer:** Web server hardening is the process of securing a web server to reduce its attack surface and make it more resistant to attack. This involves a number of steps, including:
    *   Removing unnecessary services and applications.
    *   Keeping the server software up to date with the latest security patches.
    *   Configuring the server to run with the principle of least privilege.
    *   Using a firewall to restrict access to the server.
    *   Enabling logging and monitoring to detect and respond to attacks.
    *   Using strong passwords and access controls.

f) Write a short note on Rogue Access Point.  
**Answer:** A rogue access point is a wireless access point that has been installed on a secure network without explicit authorization from a local network administrator. Rogue access points can be set up by either a well-intentioned employee trying to get better wireless reception, or by a malicious attacker. An attacker can use a rogue access point to bypass network security and gain access to the network. They can also use it to launch man-in-the-middle attacks and intercept traffic. A common type of rogue access point is an "evil twin," which is a rogue access point that is configured with the same SSID as a legitimate access point to trick users into connecting to it.
