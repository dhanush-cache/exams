# Ethical Hacking - November 2025 - Answers

## Q1
**a) What are the skills required of an Ethical Hacker? Explain.**

An ethical hacker requires a combination of technical and soft skills. Technical skills include in-depth knowledge of operating systems (Windows, Linux), networking concepts (TCP/IP, OSI model), security concepts (firewalls, IDS/IPS), and proficiency in programming and scripting languages (Python, Bash). They must be adept at using various hacking tools like Nmap, Wireshark, and Metasploit. Soft skills are equally important and include strong problem-solving abilities, creativity, attention to detail, and excellent communication skills to report findings effectively. A strong ethical code and integrity are paramount.

**b) Describe the term DNS Enumeration in detail.**

DNS enumeration is the process of locating all DNS servers and their corresponding records for a target network. It's a crucial part of the information-gathering phase. By querying DNS servers, an attacker can obtain a wealth of information, such as usernames, hostnames, IP addresses, and other network details. This information can then be used to create a map of the target network and identify potential vulnerabilities. Common tools used for DNS enumeration include `nslookup`, `dig`, and `fierce`.

**c) Explain the HTTP Tunneling technique.**

HTTP tunneling is a technique used to bypass firewalls and other network security measures by encapsulating traffic from other protocols within HTTP requests. Since most firewalls are configured to allow HTTP traffic (port 80) to pass through, an attacker can use this to exfiltrate data or establish a command-and-control channel. The non-HTTP data is encoded and placed in the body of an HTTP POST request, which is then sent to a server controlled by the attacker. The server extracts the data and processes it.

**d) Write a short note on footprinting.**

Footprinting is the first phase of ethical hacking, where the goal is to gather as much information as possible about a target organization. This is a passive process that doesn't involve direct interaction with the target's systems. Information gathered can include domain names, IP address ranges, network blocks, employee information, and technologies used. This information is gathered from public sources like websites, social media, and search engines. The goal is to create a complete profile of the target's security posture.

**e) Explain the different steps in Enumeration process.**

Enumeration is the process of actively connecting to a target system to discover potential attack vectors. The steps typically include:
1.  **Network and Port Scanning:** Identify live hosts and open ports on the target network using tools like Nmap.
2.  **Service Identification:** Determine the services running on the open ports.
3.  **User and Group Enumeration:** Extract information about users, groups, and their permissions (e.g., via SNMP, NetBIOS).
4.  **System Enumeration:** Gather details about the operating system, running processes, and system configurations.
5.  **Vulnerability Scanning:** Use automated tools to identify known vulnerabilities in the discovered services and systems.

**f) Describe the most commonly used ping sweep techniques.**

A ping sweep is used to determine which hosts are active on a network. The most common techniques are:
1.  **ICMP Echo Ping:** This is the standard ping command, which sends an ICMP Echo Request to a target. If the target is online, it will respond with an ICMP Echo Reply.
2.  **TCP ACK Ping:** This technique sends a TCP ACK packet to a specific port. If the host is up, it will respond with a TCP RST packet. This is useful for bypassing firewalls that block ICMP traffic.
3.  **TCP SYN Ping:** This technique sends a TCP SYN packet (similar to the first step of a three-way handshake). An active host will respond with a SYN/ACK or RST packet. This is a stealthier technique than a full connect scan.

## Q2
**a) Describe the working of DOS attack and its types.**

A Denial-of-Service (DoS) attack aims to make a machine or network resource unavailable to its intended users. It does this by overwhelming the target with a flood of traffic or by sending malformed requests that cause the target system to crash. Common types of DoS attacks include:
*   **SYN Flood:** The attacker sends a succession of SYN requests to a target's system in an attempt to consume enough server resources to make the system unresponsive to legitimate traffic.
*   **Ping of Death:** The attacker sends a malformed or oversized ICMP packet that can crash the target system.
*   **UDP Flood:** The attacker floods the target with a large number of UDP packets to random ports.

**b) What are Keyloggers and how do they work?**

A keylogger is a type of spyware that records the keystrokes made by a user on a computer. Keyloggers can be either hardware-based (a physical device connected between the keyboard and the computer) or software-based (a program running on the victim's machine). They work by intercepting the signals sent from the keyboard to the operating system. The recorded keystrokes are then saved to a log file, which can be accessed by the attacker to steal sensitive information like passwords, credit card numbers, and personal messages.

**c) Define rootkits. Explain its types.**

A rootkit is a collection of software tools that enables an unauthorized user to gain control of a computer system without being detected. Rootkits are designed to be stealthy and can hide their presence and activities from the user and security software. Types of rootkits include:
*   **Kernel-level Rootkits:** These are the most powerful type, as they operate at the kernel level of the OS, giving them unrestricted access to the system.
*   **User-level Rootkits:** These operate in the user space and are easier to detect and remove.
*   **Bootloader Rootkits:** These infect the master boot record (MBR) and are loaded before the operating system, making them very difficult to detect.

**d) What does MAC flooding mean? Explain.**

MAC flooding is a technique used to compromise the security of network switches. A switch maintains a MAC address table that maps each MAC address to a specific port on the switch. In a MAC flooding attack, the attacker sends a large number of Ethernet frames with different source MAC addresses to the switch. This overwhelms the switch's memory, causing it to enter a "fail-open" mode where it broadcasts all incoming packets to all ports, effectively turning the switch into a hub. This allows the attacker to sniff all the traffic on the network.

**e) Explain the Patch Management techniques applied to secure a Webserver.**

Patch management is the process of identifying, testing, and deploying software patches to fix security vulnerabilities. For a web server, this is a critical security practice. The techniques include:
1.  **Vulnerability Scanning:** Regularly scan the web server and its applications for known vulnerabilities.
2.  **Patch Acquisition:** Obtain patches from the software vendors as soon as they are released.
3.  **Patch Testing:** Test the patches in a non-production environment to ensure they don't cause any new issues.
4.  **Patch Deployment:** Deploy the patches to the production web server in a timely manner.
5.  **Verification:** Verify that the patches have been successfully applied and have fixed the vulnerabilities.

**f) State and explain some countermeasures on DOS/DDOS attack.**

Countermeasures against DoS/DDoS attacks focus on detection and mitigation.
1.  **Rate Limiting:** This involves configuring routers and firewalls to limit the number of incoming requests from a single IP address.
2.  **Blackholing/Sinkholing:** This technique redirects malicious traffic to a non-existent or "blackhole" IP address, effectively dropping the traffic.
3.  **Intrusion Detection/Prevention Systems (IDS/IPS):** These systems can be configured to detect the patterns of a DoS attack and block the malicious traffic.
4.  **Content Delivery Networks (CDNs):** CDNs can help to absorb and distribute the traffic from a DDoS attack across their large network of servers.
5.  **Upstream Filtering:** Work with your ISP to filter out malicious traffic before it even reaches your network.

## Q3
**a) Define following term: a) Threats, b) Malware, c) Phishing**

*   **Threats:** A threat is any potential danger that can exploit a vulnerability to compromise the security of an asset. It can be natural, intentional, or unintentional.
*   **Malware:** Short for "malicious software," malware is any software intentionally designed to cause damage to a computer, server, client, or computer network. Examples include viruses, worms, Trojans, and ransomware.
*   **Phishing:** Phishing is a type of social engineering attack where an attacker sends a fraudulent message designed to trick a human victim into revealing sensitive information to the attacker or to deploy malicious software on the victim's infrastructure like ransomware.

**b) Explain in detail Wireless Sniffing and its working.**

Wireless sniffing is the process of capturing and analyzing data packets that are transmitted over a wireless network. Since wireless networks broadcast data through the air, anyone within range can potentially intercept the traffic. An attacker uses a wireless network adapter in "monitor mode" and a sniffing tool like Wireshark or Kismet. In monitor mode, the adapter can capture all wireless packets in the air, not just those addressed to it. If the network is unencrypted, the captured data can be read in plain text. If the network is encrypted (e.g., with WEP, WPA, or WPA2), the attacker may try to crack the encryption key to decrypt the data.

**c) Define the term Rogue Access Point and explain its working.**

A rogue access point is a wireless access point that has been installed on a secure network without explicit authorization from a local network administrator. Rogue APs can be set up by either a well-intentioned employee trying to get better wireless reception, or by a malicious attacker. A malicious rogue AP can be configured to intercept traffic, capture sensitive information like passwords, or launch man-in-the-middle attacks. It works by tricking users into connecting to it instead of the legitimate access point. The attacker might give the rogue AP the same SSID as the legitimate network to fool users.

**d) Explain steps to secure wireless networks in details.**

Securing a wireless network involves several layers of defense:
1.  **Change Default Credentials:** Immediately change the default administrator username and password of your wireless router.
2.  **Enable Strong Encryption:** Use WPA3 or at least WPA2 with a strong, complex password. Avoid the outdated and insecure WEP.
3.  **Disable SSID Broadcasting:** Hiding the network name makes it slightly harder for casual attackers to find your network.
4.  **Enable MAC Address Filtering:** This allows you to specify which devices are allowed to connect to your network.
5.  **Keep Firmware Updated:** Regularly check for and install firmware updates for your router to patch security vulnerabilities.
6.  **Use a Firewall:** Enable the firewall on your router to control incoming and outgoing traffic.

**e) Define stack based buffer overflow in brief.**

A stack-based buffer overflow is a type of vulnerability that occurs when a program writes more data to a buffer on the stack than the buffer is allocated to hold. The stack is a region of memory used to store local variables and function call information. When a buffer on the stack is overflowed, the excess data can overwrite adjacent memory, including the return address of the current function. An attacker can exploit this by crafting a malicious input that overwrites the return address with the address of their own malicious code, which will then be executed when the function returns.

**f) Define term authentication and its types.**

Authentication is the process of verifying the identity of a user, process, or device. It is a prerequisite for granting access to resources in a system. The types of authentication are typically categorized based on the factors used for verification:
1.  **Something you know (Knowledge factor):** This is the most common type and includes passwords, PINs, and security questions.
2.  **Something you have (Possession factor):** This involves something the user physically possesses, such as a security token, a smart card, or a mobile phone (for receiving one-time passwords).
3.  **Something you are (Inherence factor):** This uses biometric data to identify a user, such as fingerprints, facial recognition, or iris scans.
Multi-factor authentication (MFA) combines two or more of these types for stronger security.

## Q4
**a) Define Hacktivism and explain the different ways it can be manifested.**

Hacktivism is the use of computer hacking techniques to promote a political agenda or social cause. Hacktivists may target government websites, corporate networks, or other organizations to protest their policies or actions. Hacktivism can manifest in several ways:
*   **Website Defacement:** Changing the visual appearance of a website to display a political message.
*   **Denial-of-Service (DoS) Attacks:** Flooding a target website with traffic to make it unavailable.
*   **Data Leaks:** Stealing and publishing sensitive or confidential information.
*   **Doxing:** Publishing a person's private information online.

**b) What is ARP spoofing? Explain in detail.**

ARP spoofing, also known as ARP poisoning, is a type of attack in which an attacker sends falsified ARP (Address Resolution Protocol) messages over a local area network. This links the attacker's MAC address with the IP address of a legitimate computer or server on the network. As a result, any traffic meant for that IP address is sent to the attacker instead. This allows the attacker to intercept, modify, or stop the traffic. ARP spoofing is often used for man-in-the-middle attacks, session hijacking, and denial-of-service attacks.

**c) Define web application threats and explain their different types.**

Web application threats are vulnerabilities in web applications that can be exploited by attackers to compromise the security of the application, its data, or its users. Some of the most common types of web application threats (as defined by OWASP Top 10) include:
*   **Injection:** Such as SQL injection, where an attacker can execute malicious SQL queries on the database.
*   **Broken Authentication:** Weaknesses in session management or credential management that allow an attacker to impersonate users.
*   **Cross-Site Scripting (XSS):** Injecting malicious scripts into a web page, which are then executed by other users.
*   **Insecure Deserialization:** Exploiting vulnerabilities in how an application deserializes data.
*   **Security Misconfiguration:** Improperly configured security settings, such as default passwords or verbose error messages.

**d) What are the different types of DNS records in Ethical Hacking?**

In ethical hacking, several types of DNS records are particularly useful for gathering information about a target:
*   **A Record:** Maps a domain name to an IPv4 address.
*   **AAAA Record:** Maps a domain name to an IPv6 address.
*   **CNAME Record:** Creates an alias for a domain name.
*   **MX Record:** Specifies the mail server for a domain.
*   **NS Record:** Lists the authoritative name servers for a domain.
*   **PTR Record:** Maps an IP address to a domain name (reverse DNS).
*   **TXT Record:** Can contain arbitrary text and is often used for SPF records (to combat email spoofing) or to verify domain ownership.

**e) Define e-mail Tracking and explain how it works.**

Email tracking is the process of monitoring the delivery and opening of an email. It is often used in marketing to measure the effectiveness of email campaigns, but it can also be used by attackers for reconnaissance. It typically works by embedding a small, invisible image (a tracking pixel) in the body of the email. When the recipient opens the email, their email client requests the image from the sender's server. This request reveals the recipient's IP address, the time the email was opened, and the type of device and email client used.

**f) Briefly explain the CEH Scanning Methodology.**

The Certified Ethical Hacker (CEH) scanning methodology is a systematic approach to identifying vulnerabilities in a target network. It consists of three main phases:
1.  **Pre-Attack Phase:** This involves reconnaissance and footprinting to gather information about the target.
2.  **Attack Phase:** This is where the actual scanning takes place. It includes port scanning to find open ports, vulnerability scanning to identify weaknesses, and enumeration to extract detailed information about the system.
3.  **Post-Attack Phase:** This involves analyzing the results of the scan, generating reports, and cleaning up any traces of the scan. The goal is to provide the target organization with a clear picture of their security posture and a list of actionable recommendations for improvement.
