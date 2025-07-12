# 🧪 Lab: Password brute-force via password change

---

## 🎯 Goal

- Find the **current password of user `carlos`**
- Change it to a new one
- Log in as `carlos`

---

## ⚠️ Vulnerability Explained

The password change functionality **does not protect against brute-force**.

Key issues:

- The form leaks whether the `current-password` is correct:
  - If wrong → `Incorrect current password`
  - If correct → no error
- The attacker can **send requests for another user** (e.g. `carlos`)
- No rate limiting or CAPTCHA

➡️ This allows an attacker to **brute-force the current password of any user** via the change password function.

---

## 🔄 Password Change Logic (Correct vs Broken)

### ✅ Expected Secure Flow

```mermaid
sequenceDiagram
    participant User
    participant Server

    User->>Server: Submit old and new password
    Server->>Server: Check session = current user
    Server->>Server: Verify old password
    Server-->>User: Success or fail (silent on detail)
