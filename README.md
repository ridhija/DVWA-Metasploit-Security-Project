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



###🔍 Part 1 — DVWA Vulnerability Assessment

DVWA (Damn Vulnerable Web Application) was used to practice different categories of web application vulnerabilities.

The following vulnerabilities were tested in the controlled environment:

Command Injection
File Inclusion
SQL Injection
Reflected XSS
Stored XSS
DOM XSS
File Upload
Weak Session IDs
Open HTTP Redirect
Cryptography Problems
JavaScript Attacks
CSP Bypass
Blind SQL Injection
Authorisation Bypass

🔹 Command Injection

Command Injection testing was performed through the DVWA Command Injection module.

A test input was used to demonstrate that operating-system commands could be executed through the vulnerable application.

Example:

127.0.0.1; whoami

The response demonstrated command execution in the web-server context.

Evidence:

###🔹 Other DVWA Findings
File Inclusion

The File Inclusion module was tested by accessing a local system file such as:

/etc/passwd

###SQL Injection

SQL Injection was demonstrated using a test input that altered the intended SQL query and returned multiple records.

Example:

1' OR '1'='1

###Cross-Site Scripting

The following XSS categories were tested:

Reflected XSS
Stored XSS
DOM XSS

Browser alert evidence was used to verify successful execution.

File Upload

The File Upload functionality was tested to understand insecure upload behavior.

Weak Session IDs

Session identifiers were generated and inspected to understand weaknesses in predictable session management.

Open HTTP Redirect

The application was tested for redirection to an external destination.

Cryptography Problems

The cryptography functionality was tested using plaintext and encoded output.

JavaScript Attacks

Client-side JavaScript behavior was analyzed through the vulnerable module.

CSP Bypass

Content Security Policy behavior was tested and browser-side execution was observed.

Blind SQL Injection

Boolean-style responses were used to determine whether a supplied condition was true or false.

Authorisation Bypass

The application was tested to understand whether restricted functionality could be accessed or modified without appropriate authorization.

🌐 Part 2 — Network Enumeration

After the DVWA assessment, Docker containers and exposed services were examined.

Nmap was used for network and service enumeration.

Example:

nmap -sV 127.0.0.1

The exposed web service was identified and further testing was performed inside the controlled Docker environment.

Evidence:

💻 Part 3 — DistCC Vulnerability Assessment

Metasploitable2 was deployed as an intentionally vulnerable target.

The DistCC service was found running on:

TCP 3632

Connectivity was verified using Netcat:

nc -vz -w 3 172.19.0.2 3632

The port was confirmed to be open.

⚡ Part 4 — Metasploit DistCC Testing

The Metasploit Framework was used to validate the vulnerable DistCC service.

The following module was selected:

exploit/unix/misc/distcc_exec

The target was then configured with the appropriate laboratory network parameters.

Configuration
RHOSTS = 172.19.0.2
RPORT  = 3632
LHOST  = 172.19.0.3
LPORT  = 4444

The vulnerability check confirmed that the target was vulnerable.

Evidence:

🔐 Part 5 — Remote Code Execution

An initial reverse Bash payload was tested but failed because the target environment did not support the required /dev/tcp functionality.

The payload was changed to:

cmd/unix/reverse_perl

The revised payload successfully established a command shell in the controlled laboratory environment.

✅ Shell Verification

After obtaining the shell, basic commands were executed to verify access.

Command
whoami

Result:

daemon
Command
id

The command confirmed the user and group information of the shell.

Command
hostname

The target hostname was displayed.

Evidence:

📊 Results

The project successfully demonstrated:

Multiple DVWA web application vulnerabilities.
Network and service enumeration.
Identification of the DistCC service.
Validation of DistCC vulnerability using Metasploit.
Successful Remote Code Execution in the controlled lab.
Establishment of a command shell.
Verification of shell access using whoami, id, and hostname.
🧠 Key Learning Outcomes

Through this project, I learned:

How vulnerable web applications can be tested safely.
How to perform basic network enumeration.
How Docker can be used to create isolated cybersecurity labs.
How Metasploit modules are selected and configured.
How payload compatibility affects exploitation.
How to troubleshoot failed payloads.
How to verify a successful remote shell.
The importance of authorization and controlled environments during security testing.
⚠️ Challenges Faced

Some challenges encountered during the project included:

DVWA initially displayed a CSRF-related login/setup issue.
The first reverse Bash payload failed because of target environment limitations.
A compatible Perl-based reverse payload was required.
Docker networking and container IP addresses had to be verified.
Metasploit sessions required correct backgrounding and interaction.
Port connectivity had to be verified before exploitation.

These issues helped improve troubleshooting and practical cybersecurity skills.

📚 References
Metasploit Framework Documentation
DVWA Documentation / Repository
OWASP Web Security Resources
Nmap Documentation
NVD — CVE-2004-2687
DistCC Security Information
👩‍💻 Author

Ridhi Jain

Domain: Cyber Security / Ethical Hacking & Pentration Testing

Project: DVWA Vulnerability Assessment and DistCC Remote Code Execution using Metasploit

⭐ Conclusion

This project provided practical experience in vulnerability assessment, network enumeration, exploitation methodology, payload selection, troubleshooting, and remote shell verification.

The complete work was performed in a controlled Docker laboratory environment to understand cybersecurity concepts safely and ethically.
