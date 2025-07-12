# 🧪 Lab: Password Reset Broken Logic

---

## 🎯 Goal

Reset the password of user `carlos` by exploiting flawed password reset logic and log in to their account.

---

## 🧠 Vulnerability Summary

The password reset functionality lacks proper verification. The server:

- Allows password reset using only the username
- Does **not validate the requester** (e.g., token, email, or session ownership)
- Immediately allows password change without authentication or verification step

> 🔥 This means an attacker can directly trigger a password change for **any user** (e.g., `carlos`), thus gaining full access.

---

## 🔄 Flow Comparison: Secure vs Broken

### ✅ Correct Password Reset Flow

```mermaid
sequenceDiagram
  participant User
  participant Server
  User->>Server: POST /forgot-password (username/email)
  Server-->>User: Email sent with secure token

  User->>Server: GET /reset-password?token=XYZ
  Server-->>User: Show reset form

  User->>Server: POST new password with valid token
  Server-->>User: ✅ Password updated


❌ Broken Logic Flow in This Lab

  participant Attacker
  participant Server

  Attacker->>Server: POST /forgot-password (username=carlos)
  Server-->>Attacker: Show password reset form (no verification)

  Attacker->>Server: POST /forgot-password?username=carlos&new-password=hacked123
  Server-->>Attacker: ✅ Password updated (no email/token/session check)

