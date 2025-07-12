# 🧪 Lab: Credential Stuffing

---

## 🎯 Goal

- Log in to the account of user `carlos` using **valid credentials**
- The password is reused from another known user (public leaked credentials)

---

## ⚠️ Vulnerability Explained

This lab simulates a **credential stuffing** attack:
- Users often **reuse passwords** across sites
- If a site leaks credentials, attackers try them on other services
- The login form here **does not protect against this type of attack**

---

## 🔍 What You Know

- You have a list of usernames:
carlos
wiener
peter
bob
...
- You also have a **single known leaked password**, e.g. `peter`

> Your goal is to **try that one password against every user** and see if any reuse it

---

## 🔄 Credential Stuffing Logic

### ❌ Broken Login Flow

```mermaid
sequenceDiagram
  participant Attacker
  participant Server

  loop For each username
      Attacker->>Server: POST /login (username, leaked_password)
      Server-->>Attacker: Valid or invalid login
  end
