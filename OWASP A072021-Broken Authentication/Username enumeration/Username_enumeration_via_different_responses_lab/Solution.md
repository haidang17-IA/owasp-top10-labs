# 🧪 Lab: Username Enumeration via Different Responses

## 🧠 Summary
This lab demonstrates how different login responses can reveal whether a username exists.

## 🔍 Vulnerability
- Error messages differ:
  - `Invalid username` → username doesn't exist
  - `Incorrect password` → username is valid

## 🛠 Tools
- Burp Suite Community
- FoxyProxy
- PortSwigger Lab instance

## 🚀 Steps
1. Submit login form with Burp running
2. Intercept and send request to Repeater
3. Compare responses with different usernames
4. Use Intruder to brute-force valid username
5. Use Intruder again to find correct password
6. Log in successfully and solve the lab

## ✅ Result
- Valid username: "ad"
- Password: (from brute-force) : "987654321"
- Lab marked as solved
