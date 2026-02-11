# 365 DAYS DETAILED ROADMAP
## Application Security Engineer - Day by Day Plan

---

## 📋 How to Use This Roadmap

- Each day has specific learning objectives
- Complete tasks in order
- Track progress daily
- Don't skip fundamentals
- Practice beats theory

---

# PHASE 1: FOUNDATION (Days 1-90)

## 🎯 Phase 1 Goals
- Setup security lab environment
- Master Linux and networking basics
- Learn Python for security
- Understand web technologies
- Complete 30 TryHackMe rooms

---

## Week 1: Networking Fundamentals (Days 1-7)

### Day 1: Introduction & Setup
**Learning Objectives:**
- Understand cybersecurity career paths
- Setup your learning environment
- Create GitHub account
- Join TryHackMe/HTB

**Resources:**
- 📺 [NetworkChuck - Getting Started in Cybersecurity](https://youtube.com)
- 📺 [What is Application Security?](https://youtube.com)
- 📄 [OWASP Foundation Overview](https://owasp.org)

**Hands-on:**
- Create GitHub profile
- Setup TryHackMe account
- Complete "Welcome" room on TryHackMe

**Time:** 2-3 hours

---

### Day 2: OSI Model & TCP/IP
**Theory:**
- 7 layers of OSI model
- TCP/IP protocol suite
- How data travels on internet

**Resources:**
- 📺 [Professor Messer - OSI Model](https://youtube.com)
- 📄 [OSI Model Explained](https://cloudflare.com)

**Hands-on:**
- TryHackMe: "Introductory Networking" room
- Draw OSI model from memory

**Time:** 2-3 hours

---

### Day 3: HTTP/HTTPS Deep Dive
**Theory:**
- HTTP methods (GET, POST, PUT, DELETE)
- HTTP status codes
- Headers and cookies
- HTTPS and TLS/SSL

**Resources:**
- 📺 [HTTP Crash Course](https://youtube.com)
- 📄 [MDN Web Docs - HTTP](https://developer.mozilla.org)

**Hands-on:**
- Use Burp Suite to intercept HTTP requests
- Analyze HTTP traffic with browser DevTools

**Time:** 3 hours

---

### Day 4: DNS & Domain Names
**Theory:**
- How DNS works
- DNS record types (A, CNAME, MX, TXT)
- DNS enumeration basics

**Resources:**
- 📺 [DNS Explained](https://youtube.com)
- 🔧 Practice: `nslookup`, `dig`, `host` commands

**Hands-on:**
- TryHackMe: "DNS in Detail" room
- Query DNS records of popular websites

**Time:** 2-3 hours

---

### Day 5: Wireshark & Packet Analysis
**Theory:**
- Network packet structure
- Protocol analysis
- Traffic filtering

**Resources:**
- 📺 [Wireshark Tutorial for Beginners](https://youtube.com)
- 🔧 Download Wireshark

**Hands-on:**
- Capture your own network traffic
- Filter HTTP traffic
- Identify different protocols

**Time:** 3-4 hours

---

### Day 6: Common Ports & Services
**Theory:**
- Well-known ports (21, 22, 23, 25, 53, 80, 443, 3306, 3389)
- Service identification
- Banner grabbing

**Resources:**
- 📄 [Common Ports Cheatsheet](https://packetlife.net)

**Hands-on:**
- Use `nmap` to scan ports
- Identify services running
- TryHackMe: "Nmap" room

**Time:** 2-3 hours

---

### Day 7: Week 1 Review & Project
**Review:**
- Revise all Week 1 concepts
- Complete any pending labs

**Project:**
- Create network diagram of your home network
- Document all protocols learned
- Write blog post about Week 1

**Time:** 3-4 hours

---

## Week 2: Linux Fundamentals (Days 8-14)

### Day 8: Linux Installation & Basics
**Setup:**
- Install VirtualBox
- Install Kali Linux VM
- Basic navigation commands

**Commands to Learn:**
```bash
ls, cd, pwd, mkdir, rm, cp, mv
cat, more, less, head, tail
man, --help
```

**Resources:**
- 📺 [Linux for Beginners - Full Course](https://youtube.com)

**Hands-on:**
- TryHackMe: "Linux Fundamentals Part 1"
- Practice all basic commands

**Time:** 3-4 hours

---

### Day 9: File System & Permissions
**Theory:**
- Linux file system structure
- File permissions (rwx)
- chmod, chown, chgrp

**Commands:**
```bash
chmod, chown, chgrp
ls -la
stat
```

**Hands-on:**
- TryHackMe: "Linux Fundamentals Part 2"
- Create users, set permissions
- Practice permission scenarios

**Time:** 2-3 hours

---

### Day 10: Text Processing & Grep
**Commands to Master:**
```bash
grep, awk, sed
cut, sort, uniq
wc, tr
```

**Hands-on:**
- Parse log files
- Extract specific information
- Create custom grep patterns

**Time:** 3 hours

---

### Day 11: Bash Scripting Basics
**Theory:**
- Shell scripting fundamentals
- Variables and loops
- If statements

**First Scripts:**
```bash
#!/bin/bash
# Port scanner
# File organizer
# Log analyzer
```

**Hands-on:**
- Write 3 simple bash scripts
- Automate repetitive tasks

**Time:** 3-4 hours

---

### Day 12: Users & Groups Management
**Commands:**
```bash
useradd, usermod, userdel
groupadd, groupmod
passwd, su, sudo
```

**Hands-on:**
- Create multiple users
- Manage sudo access
- Practice privilege escalation scenarios

**Time:** 2-3 hours

---

### Day 13: Process Management & Services
**Commands:**
```bash
ps, top, htop
kill, killall
systemctl, service
cron, crontab
```

**Hands-on:**
- Monitor running processes
- Schedule tasks with cron
- Manage services

**Time:** 3 hours

---

### Day 14: Week 2 Review & Linux Project
**Project:**
- Create bash script to:
  - Scan network for live hosts
  - Identify open ports
  - Log findings to file
  - Email summary

**Review:**
- TryHackMe: "Linux Fundamentals Part 3"
- Complete all Linux exercises

**Time:** 4 hours

---

## Week 3: Web Technologies (Days 15-21)

### Day 15: HTML & DOM
**Theory:**
- HTML structure
- DOM manipulation
- Forms and inputs

**Resources:**
- 📺 [HTML Crash Course](https://youtube.com)
- 🔧 [W3Schools HTML](https://w3schools.com)

**Hands-on:**
- Build simple HTML page
- Inspect DOM with DevTools
- Understand XSS injection points

**Time:** 3 hours

---

### Day 16: CSS & JavaScript Basics
**Theory:**
- CSS selectors
- JavaScript fundamentals
- Event handlers

**Resources:**
- 📺 [JavaScript for Hackers](https://youtube.com)

**Hands-on:**
- Create interactive web page
- Understand client-side security

**Time:** 3-4 hours

---

### Day 17: Cookies, Sessions & Local Storage
**Theory:**
- How cookies work
- Session management
- Local/session storage
- Security implications

**Hands-on:**
- Inspect cookies in browser
- Modify cookie values
- Understand session hijacking basics

**Time:** 2-3 hours

---

### Day 18: Same-Origin Policy & CORS
**Theory:**
- Same-Origin Policy
- CORS mechanism
- Security implications

**Hands-on:**
- Test CORS configurations
- Understand bypass techniques

**Time:** 2-3 hours

---

### Day 19: Web Servers & Databases
**Theory:**
- Apache vs Nginx
- SQL databases (MySQL, PostgreSQL)
- NoSQL basics (MongoDB)

**Hands-on:**
- Setup local web server
- Create database
- Connect web app to database

**Time:** 3-4 hours

---

### Day 20: REST APIs
**Theory:**
- RESTful architecture
- API endpoints
- Authentication (Bearer, API keys)

**Hands-on:**
- Use Postman to test APIs
- Analyze API requests
- Identify insecure endpoints

**Time:** 3 hours

---

### Day 21: Week 3 Review & Web Project
**Project:**
- Build vulnerable web application with:
  - Login form
  - Database connection
  - Cookie-based session
  - REST API endpoints

**Time:** 4-5 hours

---

## Weeks 4-13: [CONTINUES WITH SAME DETAIL LEVEL]

*Due to length, showing structure for remaining weeks*

### Week 4: Python Basics (Days 22-28)
### Week 5: Python for Security (Days 29-35)
### Week 6: Burp Suite Mastery (Days 36-42)
### Week 7: SQL Injection Deep Dive (Days 43-49)
### Week 8: XSS & CSRF (Days 50-56)
### Week 9: Authentication Attacks (Days 57-63)
### Week 10: Authorization & IDOR (Days 64-70)
### Week 11: File Upload Vulnerabilities (Days 71-77)
### Week 12: XXE & SSRF (Days 78-84)
### Week 13: Phase 1 Project & Security+ Prep (Days 85-90)

---

# PHASE 2: CORE SECURITY (Days 91-180)

## 🎯 Phase 2 Goals
- Master OWASP Top 10
- Complete PortSwigger Academy
- Pass Security+ certification
- Find first real vulnerabilities
- Start bug bounty

---

## Week 14-26: [DETAILED DAY-BY-DAY CONTINUES]

---

# PHASE 3: ADVANCED SKILLS (Days 181-270)

## 🎯 Phase 3 Goals
- Root 20 Hack The Box machines
- Pass eJPT certification
- Advanced exploitation techniques
- Mobile & Cloud security basics

---

# PHASE 4: MASTERY & OSCP (Days 271-365)

## 🎯 Phase 4 Goals
- Pass OSCP certification
- Professional bug bounty hunter
- Land first AppSec job
- Build strong portfolio

---

## 📊 Monthly Milestones

| Month | Milestone | Proof |
|-------|-----------|-------|
| 1 | Lab setup complete | Screenshot |
| 2 | 20 TryHackMe rooms | Profile badge |
| 3 | Security+ certified | Certificate |
| 4 | First 5 vulnerabilities | Write-ups |
| 5 | PortSwigger 50% | Progress screenshot |
| 6 | eJPT certified | Certificate |
| 7 | Root 5 HTB machines | Proof.txt |
| 8 | Bug bounty submission | Submission proof |
| 9 | CEH (optional) | Certificate |
| 10 | Root 10 more HTB boxes | Screenshots |
| 11 | OSCP lab time starts | Invoice |
| 12 | OSCP certified | Certificate |

---

## 📚 Daily Study Template

```markdown
# Day X: [Topic]

## Morning (1 hour)
- [ ] Watch video tutorial
- [ ] Read documentation
- [ ] Take notes

## Afternoon (2 hours)
- [ ] Hands-on lab
- [ ] Practice exercises
- [ ] Troubleshoot issues

## Evening (1 hour)
- [ ] Review day's learning
- [ ] Update progress tracker
- [ ] Prepare for tomorrow

## Notes:
[Your learnings]

## Challenges Faced:
[Problems encountered]

## Resources Used:
- [Link 1]
- [Link 2]
```

---

## ⏰ Time Management

### Weekdays (3 hours):
- 6:00-7:00 AM: Theory
- 8:00-10:00 PM: Practice labs

### Weekends (6 hours):
- 9:00 AM-12:00 PM: Deep practice
- 2:00-5:00 PM: Projects & review

---

## 🎯 Success Metrics

Track these weekly:
- [ ] Hours studied
- [ ] Labs completed
- [ ] Concepts mastered
- [ ] Blog posts written
- [ ] GitHub commits
- [ ] LinkedIn posts

---

**Next:** [RESOURCES.md](RESOURCES.md) - All study materials  
**Track:** [PROGRESS.md](PROGRESS.md) - Your journey log

---

**Remember:** Consistency > Intensity!  
**आठवा:** नियमितता > तीव्रता!
