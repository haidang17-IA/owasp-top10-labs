# 🧪 Lab: 2FA Simple Bypass

---

## 🎯 Goal

Bypass a broken multi-factor authentication (2FA) mechanism and access the account of user `carlos`.

---

## 🔍 Vulnerability Summary

This application implements a 2-step login process:

1. Step 1: Enter username and password (`POST /login`)
2. Step 2: Enter 2FA code (OTP) (`POST /login2`)

However, the application **does not enforce** the second step (2FA) correctly.

---

## 🧠 How the Flaw Works

After submitting a valid username and password, the application:

- Creates a session and sets a login cookie
- Redirects to `/login2` to ask for a 2FA code
- **But does not actually require 2FA confirmation to access authenticated pages**

By skipping the `/login2` step and directly visiting `/my-account`, the attacker is logged in without ever completing 2FA.

---

## 🔄 Authentication Flow Comparison

### ✅ Normal / Secure 2FA Flow

```mermaid
sequenceDiagram
  participant User
  participant Server

  User->>Server: POST /login (username + password)
  Server-->>User: 302 Redirect to /login2 (sets session, flags 2FA incomplete)

  User->>Server: POST /login2 (OTP)
  Server-->>User: 302 Redirect to /my-account (marks 2FA complete)

  User->>Server: GET /my-account
  Server-->>User: ✅ Access granted


❌ Vulnerable 2FA Flow (Broken Logic)
sequenceDiagram
  participant User
  participant Server

  User->>Server: POST /login (username + password)
  Server-->>User: 302 Redirect to /login2 (sets session)

  User->>Server: GET /my-account
  Server-->>User: ✅ Access granted without checking 2FA
