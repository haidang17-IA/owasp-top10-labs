# 💉 PortSwigger Academy – Injection Labs (OWASP Top 10)

> A personal knowledge base and lab documentation project focusing on the **Injection** vulnerability from the [OWASP Top 10](https://owasp.org/www-project-top-ten/), with hands-on labs from [PortSwigger Web Security Academy](https://portswigger.net/web-security/sql-injection).  
> This repository includes theoretical explanations, lab walkthroughs, payloads used, screenshots, and personal insights.

---

## 🎯 Objectives

- ✅ Understand how different types of **SQL Injection** attacks work
- ✅ Practice exploiting real-world-like scenarios via PortSwigger Labs
- ✅ Record step-by-step solutions with payloads and responses
- ✅ Organize knowledge by attack technique/topic

---

## 📂 Lab Topics

| Topic | Description | 
|-------|-------------|
| [Retrieving hidden data](./Retrieving-hidden-data/) | Extract hidden content by manipulating WHERE clause logic | 
| [Subverting application logic](./Subverting-application-logic/) | Bypass business logic (e.g. authentication, logic flow) | 
|[Retrieving data from other tables](./Retrieving-data-from-other-tables/) | Access sensitive data stored in other tables | 
| [Examining the database](./Examining-the-database/) | Extract schema or database structure | 
| [Blind SQL injection](./Blind-SQL-injection/) | Exploit SQLi when no direct data is returned |
| [Second-order SQL injection](./Second-order-SQL-injection/) | Exploit injected data stored and executed later | 
---

## 📘 What's Included in Each Lab

- 🔍 Lab title & description
- 🔗 Link to the live lab (PortSwigger)
- 📌 Payloads used
- 🧠 Explanation of how the exploit works
- 📸 Screenshots showing success
- ✅ Key takeaways and personal notes

---

## 🧠 What is SQL Injection?

**SQL Injection** is a vulnerability that occurs when an application incorporates unsanitized user input directly into SQL queries. This can allow attackers to **read, modify, or delete data** from the backend database.

> Example basic payload: `' OR 1=1--`  
> This forces the query to always return true, revealing hidden data or bypassing login systems.

---

## 📚 References

- [PortSwigger Web Security Academy](https://portswigger.net/web-security)
- [OWASP SQL Injection Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html)
- [OWASP Top 10 – Injection](https://owasp.org/Top10/A03_2021-Injection/)

---

## 📜 License

This repository is created for **educational and ethical purposes only**. Content and lab challenges belong to PortSwigger. Please do not use this knowledge to perform unauthorized testing.

---


