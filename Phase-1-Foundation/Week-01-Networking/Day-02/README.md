# Day 2: OSI Model & TCP/IP Fundamentals
## Understanding How Data Travels on the Internet

---

## 🎯 Today's Objectives

By the end of today, you will:
- ✅ Understand all 7 layers of OSI Model
- ✅ Know TCP/IP protocol suite
- ✅ Understand how data packets travel
- ✅ Identify which protocols work at which layer
- ✅ Complete hands-on labs on TryHackMe
- ✅ Understand why this matters for security

**Time Required:** 3-4 hours  
**Difficulty:** ⭐⭐ Beginner-Intermediate  
**Prerequisites:** Day 1 completed

---

## 📚 Theory (60 minutes)

### What is the OSI Model?

**OSI = Open Systems Interconnection**

The OSI Model is a **7-layer framework** that describes how data travels from one computer to another over a network.

**Why learn this?**
- Every security attack happens at one of these layers
- Understanding layers helps find vulnerabilities
- Essential for penetration testing
- Asked in every security interview

---

### The 7 Layers (Easy to Remember!)

**Mnemonic:** **P**lease **D**o **N**ot **T**hrow **S**ausage **P**izza **A**way!

| Layer | Name | Function | Protocols | Security Concerns |
|-------|------|----------|-----------|-------------------|
| 7 | **Application** | User interface | HTTP, HTTPS, FTP, DNS, SMTP | SQL injection, XSS, CSRF |
| 6 | **Presentation** | Data format/encryption | SSL/TLS, JPEG, ASCII | Encryption flaws |
| 5 | **Session** | Maintains connections | NetBIOS, PPTP | Session hijacking |
| 4 | **Transport** | End-to-end delivery | TCP, UDP | SYN flood, port scanning |
| 3 | **Network** | Routing/IP addressing | IP, ICMP, IPsec | IP spoofing, routing attacks |
| 2 | **Data Link** | MAC addressing | Ethernet, Wi-Fi, ARP | ARP poisoning, MAC spoofing |
| 1 | **Physical** | Physical hardware | Cables, Wi-Fi signals | Physical access, wire tapping |

---

### Layer-by-Layer Breakdown

#### Layer 7: Application Layer (सर्वात वरचा)
**What it does:**
- Where applications interact with network
- User sees this layer
- Web browsers, email clients work here

**Protocols:**
- **HTTP/HTTPS** - Web browsing
- **FTP** - File transfer
- **SMTP** - Email sending
- **DNS** - Domain name resolution
- **SSH** - Secure remote access

**Security Testing Focus:**
- 90% of web attacks happen here!
- SQL injection, XSS, CSRF
- API vulnerabilities
- Authentication bypass

**Example:**
```
You type: www.google.com
Application layer: "I need to load this website"
```

---

#### Layer 6: Presentation Layer
**What it does:**
- Translates data formats
- Encryption/Decryption
- Compression

**Protocols:**
- **SSL/TLS** - Encryption
- **JPEG, GIF** - Image formats
- **ASCII, EBCDIC** - Character encoding

**Security Focus:**
- Weak encryption
- SSL/TLS vulnerabilities (Heartbleed)
- Certificate issues

---

#### Layer 5: Session Layer
**What it does:**
- Establishes, manages, terminates sessions
- Keeps track of connections

**Protocols:**
- **NetBIOS**
- **PPTP** - VPN protocol
- **RPC** - Remote Procedure Call

**Security Focus:**
- Session hijacking
- Session fixation
- Man-in-the-middle attacks

---

#### Layer 4: Transport Layer (महत्वाचा!)
**What it does:**
- Breaks data into segments
- Ensures reliable delivery
- Error checking

**Protocols:**
- **TCP** - Reliable, connection-oriented
- **UDP** - Fast, connectionless

**TCP vs UDP:**
```
TCP (Transmission Control Protocol):
- Reliable (guarantees delivery)
- Slower
- Used for: Web browsing, email, file transfer
- Three-way handshake: SYN → SYN-ACK → ACK

UDP (User Datagram Protocol):
- Fast
- No guarantee of delivery
- Used for: Video streaming, gaming, DNS
- No handshake
```

**Security Focus:**
- Port scanning (Nmap works here!)
- SYN flood attacks
- Firewall bypass
- Service enumeration

**Important Ports:**
```
Common TCP Ports:
20/21  - FTP (File Transfer)
22     - SSH (Secure Shell)
23     - Telnet (Insecure remote access)
25     - SMTP (Email)
80     - HTTP (Web)
443    - HTTPS (Secure Web)
3306   - MySQL Database
3389   - RDP (Remote Desktop)
8080   - Alternative HTTP

Common UDP Ports:
53     - DNS
67/68  - DHCP
161    - SNMP
```

---

#### Layer 3: Network Layer
**What it does:**
- Routing between networks
- IP addressing
- Packet forwarding

**Protocols:**
- **IP (IPv4/IPv6)** - Internet Protocol
- **ICMP** - Ping, traceroute
- **IPsec** - VPN security

**IP Address Example:**
```
IPv4: 192.168.1.1
IPv6: 2001:0db8:85a3:0000:0000:8a2e:0370:7334

Private IP Ranges:
10.0.0.0    - 10.255.255.255
172.16.0.0  - 172.31.255.255
192.168.0.0 - 192.168.255.255
```

**Security Focus:**
- IP spoofing
- ICMP flood (Ping of death)
- Routing attacks
- Network reconnaissance

---

#### Layer 2: Data Link Layer
**What it does:**
- MAC addressing
- Switching
- Error detection at physical level

**Protocols:**
- **Ethernet**
- **Wi-Fi (802.11)**
- **ARP** - Maps IP to MAC

**MAC Address:**
```
Example: 00:1A:2B:3C:4D:5E
- First 6 characters: Manufacturer
- Last 6 characters: Device ID
```

**Security Focus:**
- ARP spoofing/poisoning
- MAC spoofing
- VLAN hopping
- Switch attacks

---

#### Layer 1: Physical Layer
**What it does:**
- Actual transmission of bits
- Cables, signals, voltages

**Components:**
- Network cables (Ethernet)
- Wi-Fi radio waves
- Fiber optics
- Hubs, repeaters

**Security Focus:**
- Physical access attacks
- Wire tapping
- Signal interference
- Keyloggers (hardware)

---

### TCP/IP Model (Real-World Usage)

While OSI has 7 layers, the internet actually uses **TCP/IP model** with **4 layers**:

| TCP/IP Layer | OSI Layers | Protocols |
|--------------|------------|-----------|
| **Application** | 7, 6, 5 | HTTP, FTP, DNS, SMTP |
| **Transport** | 4 | TCP, UDP |
| **Internet** | 3 | IP, ICMP, ARP |
| **Network Access** | 2, 1 | Ethernet, Wi-Fi |

**Why both models?**
- OSI: Academic/teaching model (theory)
- TCP/IP: What internet actually uses (practical)

---

### How Data Travels (Example)

**Scenario:** You visit www.google.com

```
SENDING (Your Computer):
Layer 7: Browser creates HTTP request
Layer 6: Encrypts with TLS (HTTPS)
Layer 5: Creates session with Google server
Layer 4: TCP breaks data into segments, adds port 443
Layer 3: IP adds source/destination IP addresses
Layer 2: Ethernet adds MAC addresses
Layer 1: Converts to electrical signals → sent over cable/Wi-Fi

↓ ↓ ↓ INTERNET ↓ ↓ ↓

RECEIVING (Google Server):
Layer 1: Receives electrical signals
Layer 2: Reads MAC address, confirms it's for this server
Layer 3: Reads IP address, confirms destination
Layer 4: TCP reassembles segments, confirms delivery
Layer 5: Maintains session
Layer 6: Decrypts TLS data
Layer 7: Web server processes HTTP request, sends Google homepage
```

**Then the same process happens in REVERSE to send data back to you!**

---

## 🎥 Video Tutorials (45 minutes)

### 1. OSI Model Explained (15 min)
**Channel:** Professor Messer  
**Search:** "Professor Messer OSI Model"  
**Link:** https://youtube.com/watch?v=vv4y_uOneC0  
**Watch for:** Layer-by-layer explanation

### 2. TCP/IP Model (15 min)
**Channel:** NetworkChuck  
**Search:** "NetworkChuck TCP/IP"  
**Link:** https://youtube.com/watch?v=OTwp3xtd4dg  
**Watch for:** How internet really works

### 3. TCP vs UDP Explained (10 min)
**Channel:** PowerCert Animated Videos  
**Search:** "PowerCert TCP vs UDP"  
**Watch for:** Visual explanation of protocols

### 4. Three-Way Handshake (5 min)
**Channel:** Sunny Classroom  
**Search:** "TCP Three Way Handshake"  
**Watch for:** SYN, SYN-ACK, ACK process

---

## 🔧 Hands-on Labs (90 minutes)

### Lab 1: TryHackMe - Introductory Networking (60 min)

**Steps:**
1. Login to TryHackMe
2. Search: "Introductory Networking"
3. Join the room (FREE)
4. Complete all tasks

**What you'll learn:**
- OSI Model practical application
- Network terminology
- How to use networking tools

**Questions to Answer:**
- What layer does HTTP operate at?
- What does TCP stand for?
- What port does HTTPS use?
- What is an IP address?

**✅ Checklist:**
- [ ] Room completed
- [ ] All questions answered correctly
- [ ] Took notes on key concepts

---

### Lab 2: OSI Model Practice (30 min)

**Exercise 1: Layer Identification**

For each scenario, identify which OSI layer:

1. You click a link in your browser
   - Answer: Layer 7 (Application)

2. Router decides which path to send data
   - Answer: Layer 3 (Network)

3. TCP breaks data into segments
   - Answer: Layer 4 (Transport)

4. Ethernet cable transmits electrical signals
   - Answer: Layer 1 (Physical)

5. SSL encrypts your data
   - Answer: Layer 6 (Presentation)

**Exercise 2: Protocol Matching**

Match protocol to layer:
```
HTTP     → Layer 7
TCP      → Layer 4
IP       → Layer 3
Ethernet → Layer 2
DNS      → Layer 7
ARP      → Layer 2
ICMP     → Layer 3
```

---

### Lab 3: Wireshark Basics (Optional - 20 min)

If you have Wireshark installed:

**Steps:**
1. Open Wireshark
2. Start capture on your active network interface
3. Visit www.google.com in browser
4. Stop capture
5. Analyze the packets

**Look for:**
- DNS query (Layer 7)
- TCP handshake (SYN, SYN-ACK, ACK)
- HTTP/HTTPS traffic
- IP addresses (Source & Destination)

**Don't worry if confusing - we'll deep dive into Wireshark on Day 5!**

---

## 📝 Assignment

### 1. Create OSI Model Diagram

Draw the OSI model with:
- All 7 layers
- Key protocols at each layer
- Common ports
- Security attacks possible

**Tools:**
- Hand-drawn and scan
- Draw.io (free online tool)
- Excalidraw
- Or any drawing tool

**Save as:** `day02-osi-diagram.png`

---

### 2. Write Layer Explanations

In your learning journal, explain each layer in **your own words**:

```markdown
# Day 2: OSI Model & TCP/IP

## Layer 7 - Application:
[Your explanation in simple words]
Example: जसे की...
Security concern: 

## Layer 6 - Presentation:
[Your explanation]

... (continue for all 7 layers)
```

---

### 3. Port Scanning Research

Research these questions:

1. What is a port number?
2. How many total ports are there? (Hint: 0-65535)
3. What are well-known ports? (0-1023)
4. Why do hackers scan ports?
5. What tool is commonly used? (Hint: Nmap)

**Write answers in your journal**

---

### 4. Real-World Application

Think of 3 real-world scenarios where understanding OSI model helps security:

Example:
```
1. SQL Injection happens at Layer 7 (Application)
   - I need to test web application inputs
   - Tools: Burp Suite, SQLmap
   
2. Port scanning happens at Layer 4 (Transport)
   - I need to find open services
   - Tool: Nmap

3. [Your scenario]
```

---

## 📖 Additional Reading (Optional)

### Must Read Articles:

1. **"OSI Model for Penetration Testing"**
   - Link: Search on Medium
   - Time: 10 minutes

2. **"How TCP/IP Works"**
   - Link: HowStuffWorks or CloudFlare
   - Time: 15 minutes

3. **"Common Network Ports Cheat Sheet"**
   - Link: Search "network ports cheat sheet PDF"
   - Download and save for reference

---

## 🧠 Quick Quiz (Test Yourself!)

**Question 1:** What layer does a router operate at?
<details>
<summary>Answer</summary>
Layer 3 (Network) - Routers use IP addresses
</details>

**Question 2:** Which protocol is connectionless?
<details>
<summary>Answer</summary>
UDP - No handshake, no guarantee of delivery
</details>

**Question 3:** What port does SSH use?
<details>
<summary>Answer</summary>
Port 22
</details>

**Question 4:** HTTP operates at which layer?
<details>
<summary>Answer</summary>
Layer 7 (Application)
</details>

**Question 5:** What does the "three-way handshake" do?
<details>
<summary>Answer</summary>
Establishes a TCP connection: SYN → SYN-ACK → ACK
</details>

**Question 6:** At which layer does ARP spoofing occur?
<details>
<summary>Answer</summary>
Layer 2 (Data Link) - ARP maps IP to MAC
</details>

**Question 7:** What layer handles encryption?
<details>
<summary>Answer</summary>
Layer 6 (Presentation) - SSL/TLS encryption
</details>

**Question 8:** HTTPS uses which port?
<details>
<summary>Answer</summary>
Port 443
</details>

---

## 🎯 Practical Security Application

### Why This Matters for AppSec:

**Layer 7 (Application):**
```
Security Testing Focus:
- Web application vulnerabilities
- API security issues
- Business logic flaws
- 90% of your testing happens here!

Tools you'll use:
- Burp Suite
- OWASP ZAP
- Postman (APIs)
```

**Layer 4 (Transport):**
```
Security Testing Focus:
- Port scanning to find services
- Service enumeration
- Firewall testing

Tools you'll use:
- Nmap
- Masscan
```

**Layer 3 (Network):**
```
Security Testing Focus:
- Network reconnaissance
- IP spoofing detection
- Routing analysis

Tools you'll use:
- Traceroute
- Ping
- Wireshark
```

---

## 🔍 Common Mnemonics

### Remember OSI Layers (Top to Bottom):

**English:**
- **A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing
- **P**lease **D**o **N**ot **T**hrow **S**ausage **P**izza **A**way

**Marathi (मराठी):**
- **आ**पण **प**ाहतो **सं**गणक **ती**व्र **ने**हमी **डे**टा **प्र**ोसेस करतो

### TCP Three-Way Handshake:
```
SYN:     "Can we talk?"
SYN-ACK: "Yes! Can you hear me?"
ACK:     "Yes, I can hear you. Let's talk!"
```

---

## ✅ End of Day Checklist

**Learning:**
- [ ] Watched all 4 videos
- [ ] Understand all 7 OSI layers
- [ ] Know difference between TCP and UDP
- [ ] Can explain three-way handshake
- [ ] Know common port numbers

**Practice:**
- [ ] Completed TryHackMe Networking room
- [ ] Drew OSI model diagram
- [ ] Completed layer identification exercises
- [ ] Answered all quiz questions

**Documentation:**
- [ ] Updated learning journal
- [ ] Added notes on each layer
- [ ] Created OSI diagram
- [ ] Wrote down key ports and protocols

**Time Spent:** _____ hours

**Difficulty Rating:** ⭐⭐⭐ (1-5)

---

## 💭 Reflection Questions

1. Which layer was most confusing? Why?
2. How does understanding OSI help in security testing?
3. What real-world example can you think of for each layer?
4. Which layer will you focus most on as an AppSec engineer?

**Write answers in journal!**

---

## 🎯 Tomorrow Preview

**Day 3: HTTP/HTTPS Deep Dive**

You'll learn:
- HTTP methods (GET, POST, PUT, DELETE)
- HTTP status codes (200, 404, 500)
- Headers and Cookies
- How HTTPS encryption works
- Man-in-the-middle attacks
- Using Burp Suite to intercept traffic

**Preparation:**
- Make sure Burp Suite is installed (comes with Kali)
- Review today's HTTP/HTTPS concepts
- Be ready for hands-on web traffic analysis

---

## 🆘 Troubleshooting

**Problem:** OSI Model is confusing
**Solution:** 
- Watch videos again
- Draw it out yourself
- Teach it to someone else
- Use real-world examples

**Problem:** Don't understand TCP vs UDP
**Solution:**
- Think: TCP = Phone call (connected)
- UDP = Shouting across room (no confirmation)

**Problem:** Too many protocols to remember
**Solution:**
- Don't memorize all at once
- Focus on common ones (HTTP, TCP, IP)
- Will naturally remember with practice

---

## 📌 Key Takeaways

**Top 5 Things to Remember:**

1. **OSI has 7 layers** - Please Do Not Throw Sausage Pizza Away
2. **TCP = Reliable**, UDP = Fast (no guarantee)
3. **Layer 7 (Application)** - Where most web attacks happen
4. **Layer 4 (Transport)** - Port numbers live here
5. **HTTP = Port 80**, HTTPS = Port 443

---

## 🤝 Share Your Progress!

**LinkedIn Post:**
```
🔐 Day 2/365 - OSI Model Mastered!

Today I learned:
✅ All 7 layers of OSI Model
✅ TCP vs UDP protocols
✅ Common network ports
✅ How data travels on internet

The foundation is getting stronger! 💪

#365DaysOfAppSec #Networking #CyberSecurity #LearningInPublic
```

**Twitter:**
```
Day 2/365 ✅

Conquered the OSI Model today!
7 layers, countless protocols, infinite possibilities 🌐

Transport layer attacks, here I come! 🎯

#365DaysOfAppSec #InfoSec
```

---

## 📚 Resources Used Today

**Videos:**
- Professor Messer - OSI Model
- NetworkChuck - TCP/IP
- PowerCert - TCP vs UDP

**Labs:**
- TryHackMe - Introductory Networking

**Tools:**
- Wireshark (optional)

**Reading:**
- This README
- Additional articles (optional)

---

## 🎉 Congratulations!

You completed Day 2! 🎊

**You now understand:**
- How internet works at fundamental level
- Where security attacks happen
- Which tools work at which layer
- Essential networking concepts

**Progress:** 2/365 days (0.5% complete!) 📈

**Keep the momentum! See you on Day 3!** 🚀

---

## 📌 Quick Links

- [← Day 1](../Day-01/README.md)
- [Day 3 →](../Day-03/README.md)
- [Week 1 Overview](../README.md)
- [Main Roadmap](../../../ROADMAP.md)
- [Resources](../../../RESOURCES.md)
- [Progress Tracker](../../../PROGRESS.md)

---

**Created by:** 365 Days AppSec Community  
**Last Updated:** January 2026  
**Difficulty:** ⭐⭐ Beginner-Intermediate  
**Estimated Time:** 3-4 hours

---

**मराठी मध्ये:** दिवस २ पूर्ण! OSI Model आता तुमच्या बोटावर! 🎯  
**Remember:** आज शिकलेल्या layers आयुष्यभर काम येतील! 💪
