# OWASP Top 10 Labs & Knowledge Summary

This repository is a personal knowledge base and lab documentation for understanding and practicing the OWASP Top 10 web application security risks.  
Each section includes:
-  Summary of theory
-  Step-by-step lab walkthroughs (e.g., PortSwigger Academy, DVWA)
-  Exploitation techniques and mitigation
-  Timeline of progress

---

## 📅 Timeline of Lab Progress

| Topic | Completion Date |
|-------|-----------------|
|  Injection | Jun 28, 2025 |
|  Broken Authentication | Jul 5, 2025 |
|  Sensitive Data Exposure | Upcoming |
|  XML External Entities (XXE) | Jul 12, 2025 |
|  Broken Access Control | Upcoming |
|  Security Misconfiguration | Upcoming |
|  Cross-Site Scripting (XSS) | Upcoming |
|  Insecure Deserialization | Upcoming |
|  Using Components with Known Vulnerabilities | Upcoming |
|  Insufficient Logging and Monitoring | Upcoming |

---

##  Topics Covered

### 1. **Injection**
- SQL Injection (Retrieving hidden data, UNION attacks, Blind SQLi)
- Command Injection
- Second-order Injection  

### 2. **Broken Authentication**
- Credential Stuffing
- Brute-force login
- Session token issues
- Bypassing 2FA  

### 3. **Sensitive Data Exposure** *(aka Cryptographic Failures)*
- Insecure TLS/SSL
- Data leakage in transit or at rest

### 4. **XML External Entities (XXE)**
- External entity injection
- File disclosure, SSRF via XML payload

### 5. **Broken Access Control**
- IDOR
- Forced browsing
- Privilege escalation

### 6. **Security Misconfiguration**
- Exposed admin panels
- Misconfigured headers
- Directory listing

### 7. **Cross-Site Scripting (XSS)**
- Reflected, Stored, DOM-based XSS
- Context-aware escaping and CSP

### 8. **Insecure Deserialization**
- Remote code execution via object injection

### 9. **Using Components with Known Vulnerabilities**
- Dependency scanning
- Exploiting outdated libraries

### 10. **Insufficient Logging and Monitoring**
- Missed detection of attacks
- Lack of alerting and audit trails

---

##  Tools Used

- Kali Linux
- Burp Suite (Community & Pro)
- DVWA: [github.com/digininja/DVWA](https://github.com/digininja/DVWA)
- PortSwigger Web Security Academy

---

##  Notes

- Each folder in this repository corresponds to one OWASP risk category.
- Payloads, writeups, screenshots, and mitigation tips included.

---





