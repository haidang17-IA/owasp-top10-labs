# 🔐 Broken Authentication Labs – PortSwigger Web Security Academy

This repository contains solutions, writeups, and payloads for **Broken Authentication** labs from [PortSwigger Web Security Academy](https://portswigger.net/web-security/all-topics). Each lab demonstrates a different vulnerability related to authentication flaws such as username enumeration, brute-forcing, and logic bypasses.

---

## 📘 What is Broken Authentication?

**Broken Authentication** refers to security flaws that allow attackers to:
- Compromise user credentials (username/password)
- Bypass login mechanisms
- Impersonate other users
- Hijack sessions or abuse flawed logic in authentication flows

### 🔍 Common issues include:
- Predictable or weak passwords
- Improper credential validation
- Information leakage in login responses
- Logic flaws in password reset or 2FA
- Session ID exposed or not rotated after login

Broken Authentication is ranked in the [OWASP Top 10](https://owasp.org/Top10/) as a **critical vulnerability category** that can lead to **account takeover** and **privilege escalation**.

---

## 📚 Topics Covered

- Username enumeration via different responses
- Brute-forcing valid users
- 2FA bypass
- Password reset logic flaws
- Account lockout vulnerabilities

Each lab folder contains:
- Writeup (`.md`) explaining the logic and exploitation steps
- Payloads used
- Screenshots (optional)

---

## 🛠 Tools Required

| Tool            | Description                              |
|-----------------|------------------------------------------|
| [Burp Suite](https://portswigger.net/burp) | Web proxy to intercept and modify HTTP/HTTPS requests |
| [FoxyProxy](https://getfoxyproxy.org)     | Browser extension to route traffic to Burp            |
| Web browser     | Chrome / Firefox                         |

---

## ⚙️ Setup Guide

### 🔸 1. Install Burp Suite (Community Edition)

- Download from: https://portswigger.net/burp/communitydownload
- Install like a regular app

> ✅ No need for Pro version.

---

### 🔸 2. Install FoxyProxy Extension

#### For Chrome:
- [FoxyProxy for Chrome](https://chrome.google.com/webstore/detail/foxyproxy-standard/gcknhkkoolaabfmlnjonogaaifnjlfnp)

#### For Firefox:
- [FoxyProxy for Firefox](https://addons.mozilla.org/en-US/firefox/addon/foxyproxy-standard/)

---

### 🔸 3. Configure FoxyProxy to Route Traffic to Burp

| Setting   | Value        |
|-----------|--------------|
| Hostname  | 127.0.0.1    |
| Port      | 8080         |
| Type      | HTTP         |

After saving, enable the proxy profile in your browser.

---

### 🔸 4. Install Burp’s CA Certificate to Avoid HTTPS Errors

1. Enable FoxyProxy (route traffic through Burp)
2. Visit `http://burp` in the browser
3. Download the **CA Certificate (`cacert.der`)**
4. Import it into the browser's **Authorities** certificate store:
   - **Chrome**: `chrome://settings/security` → Manage Certificates → Authorities
   - **Firefox**: Settings → Privacy & Security → Certificates → View Certificates

✅ Trust the certificate for identifying websites.

---

### 🔸 5. Ready to Go!

- Make sure **Intercept is OFF** in Burp unless you want to capture a request
- Access labs directly from PortSwigger
- Use **Burp Repeater** and **Intruder** to analyze and exploit

---

## 📁 Repository Structure

broken-authentication/
├── README.md
├── username-enum-diff-response/
│ ├── username-enum-diff-response.md
│ ├── payloads.txt
│ └── screenshots/
├── brute-force-valid-user/
│ └── ...
└── ...

---

## 🔗 References

- [OWASP Top 10: Broken Authentication](https://owasp.org/Top10/A07_2021-Identification_and_Authentication_Failures/)
- [PortSwigger: Authentication vulnerabilities](https://portswigger.net/web-security/authentication)
- [OWASP Cheat Sheet: Authentication](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html)

---

## ✍️ Author

- Created by Hai Dang
- For educational and ethical testing purposes only.

---


