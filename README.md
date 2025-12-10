# PSLVA
Personal Security Lab and Vulnerability Assessments (PSLVA) A foundational cybersecurity micro-project for learning analysis, ethical exploitation, and structured reporting.

---

## 📌 Project Overview
This project establishes a **contained virtual security lab**, performs a **baseline network and service assessment**, and documents the safe exploitation of a known vulnerability in a deliberately insecure application (OWASP Juice Shop).

The goal is to develop practical experience with:
- Virtualized attack/defense environments  
- Reconnaissance tooling (Nmap, Wireshark)  
- Web application testing (Burp Suite)  
- Root cause analysis & remediation planning  
- Secure documentation and reproducible workflows  

---

## 🧪 Lab Architecture

**Tools Used**
- **VirtualBox** – virtualization platform  
- **Kali Linux** – attacker machine  
- **OWASP Juice Shop** – vulnerable web application  
- **Nmap** – network scanning  
- **Wireshark** – packet capture  
- **Burp Suite (Community Edition)** – web traffic interception  
- **Browser** – for testing interaction with target  

**Network Configuration**
- All VMs configured with **Host-Only Adapter**  
- No external internet exposure  
- Isolated environment for safe learning  

+------------------+ +------------------------+
| Kali Linux | <----> | OWASP Juice Shop |
| (Attacker VM) | | (Vulnerable Target VM) |
+------------------+ +------------------------+
| (Host-Only Network)
