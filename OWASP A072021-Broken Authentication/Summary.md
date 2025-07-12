## 🔒 Summary of Broken Authentication Vulnerabilities (Completed Labs)

This section summarizes all Broken Authentication attacks you have practiced, grouped by type, including explanation, impact, and lab examples.

---

### 1️⃣ Username Enumeration

- **Description**: The application reveals whether a username is valid based on response differences.
- **Impact**: Enables attackers to build a list of valid usernames for targeted attacks.
- **Detection**: Compare server responses for valid vs invalid usernames.
- **Lab Completed**:
  - ✅ *Username enumeration via different responses*  
  - ✅ *Username enumeration via account lock*

---

### 2️⃣ Two-Factor Authentication (2FA) Bypass

- **Description**: The attacker bypasses 2FA due to incorrect or missing logic validation.
- **Impact**: Allows access to protected accounts without completing the second factor.
- **Technique**: Reuse valid session/cookie, missing 2FA enforcement.
- **Lab Completed**:
  - ✅ *2FA simple bypass*

---

### 3️⃣ Password Reset Logic Flaws

- **Description**: The password reset process allows attackers to reset another user’s password without proper token validation.
- **Impact**: Account takeover without email access.
- **Technique**: Remove or manipulate token in reset request, or change target username.
- **Lab Completed**:
  - ✅ *Password reset broken logic*

---

### 4️⃣ Password Brute-force via Password Change Functionality

- **Description**: The attacker brute-forces a user's current password using the password change form.
- **Impact**: Unauthorized password change and account takeover.
- **Technique**: Form leaks whether current password is correct (response-based side channel).
- **Lab Completed**:
  - ✅ *Password brute-force via password change*

---

### 5️⃣ Credential Stuffing

- **Description**: The attacker tries a known leaked password with many usernames (reused credentials).
- **Impact**: Login to user accounts if the same password is reused.
- **Technique**: Same password + multiple usernames + no lockout or protection.
- **Lab Completed**:
  - ✅ *Credential stuffing*

---

## ✅ Summary Table

| # | Attack Type                         | Key Technique                        | Lab Example                                          |
|---|-------------------------------------|--------------------------------------|------------------------------------------------------|
| 1 | Username Enumeration                | Response discrepancy                 | `Username enumeration via response`                  |
|   |                                     | Account lock-based error messages    | `Username enumeration via account lock`              |
| 2 | 2FA Bypass                          | Missing validation                   | `2FA simple bypass`                                  |
| 3 | Password Reset Logic Flaws         | No token enforcement                 | `Password reset broken logic`                        |
| 4 | Password Brute-force via Change    | Guess current password via response  | `Password brute-force via password change`           |
| 5 | Credential Stuffing                | One leaked password + many users     | `Credential stuffing`                                |

---

## 📁 Related Topic Folders

- `T1-username-enumeration/`
- `T2-password-brute-force/`
- `T3-2fa-bypass/`
- `T4-password-reset-logic-flaws/`

> 🛠️ You can use this section as a checklist of completed labs and vulnerabilities explored in the Broken Authentication category.
