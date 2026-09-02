# DVWA-Metasploit-Security-Project
A hands-on cybersecurity project demonstrating DVWA vulnerability assessment and DistCC Remote Code Execution using Metasploit in a controlled Docker lab environment.
# DVWA Vulnerability Assessment and DistCC Remote Code Execution using Metasploit

## 📌 Project Overview

This project demonstrates hands-on cybersecurity testing in a controlled Docker-based laboratory environment.

The project is divided into two major parts:

1. **DVWA Vulnerability Assessment**
2. **DistCC Remote Code Execution using Metasploit**

The objective is to understand common web application vulnerabilities, perform basic security testing, identify vulnerable services, and demonstrate controlled remote command execution using the Metasploit Framework.

> ⚠️ **Disclaimer:** All testing in this project was performed in a controlled and isolated laboratory environment for educational purposes. No unauthorized systems were targeted.

---

## 🎯 Objectives

- Understand common web application vulnerabilities.
- Perform vulnerability assessment using DVWA.
- Practice security testing using Kali Linux.
- Perform network and service enumeration using Nmap.
- Understand vulnerable services in a controlled environment.
- Identify the vulnerable DistCC service.
- Use Metasploit Framework to validate the DistCC vulnerability.
- Demonstrate Remote Code Execution (RCE) in a controlled lab.
- Verify the obtained remote shell using basic Linux commands.

---

## 🛠️ Tools & Technologies

| Tool / Technology | Purpose |
|---|---|
| Kali Linux | Security testing environment |
| Docker | Isolated laboratory environment |
| DVWA | Vulnerable web application |
| Metasploitable2 | Intentionally vulnerable target |
| Metasploit Framework | Exploitation and vulnerability validation |
| Nmap | Network and service enumeration |
| Netcat | Network connectivity verification |
| Apache | Web server used by DVWA |
| DistCC | Vulnerable distributed compiler service |

---

## 🧪 Laboratory Environment

The project was performed using Docker containers connected through an isolated Docker network.

### Main Components

- **Attacker / Testing Machine:** Kali Linux
- **Web Application:** DVWA
- **Target Machine:** Metasploitable2
- **Exploitation Framework:** Metasploit Framework

### Network

The Metasploit and Metasploitable2 containers were connected through a custom Docker bridge network.

Example lab addresses:

```text
Metasploitable2 : 172.19.0.2
Metasploit      : 172.19.0.3
DistCC Port     : 3632
