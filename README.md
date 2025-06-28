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
| [Retrieving hidden data and filter bypass](./Retrieving-hidden-data/) | Extract hidden content by manipulating SQL logic or bypassing input filters |
| [Authentication and logic bypass](./Authentication-and-logic-bypass/) | Bypass login or application logic using SQL injection |
| [Database information enumeration](./Database-information-enumeration/) | Discover DBMS type, version, and schema details |
| [Listing database contents](./Listing-database-contents/) | Enumerate tables, columns, and stored data via SQL injection |
| [UNION-based SQL injection](./UNION-based-SQL-injection/) | Use `UNION SELECT` to extract data from other tables |
| [Blind SQL injection](./Blind-SQL-injection/) | Infer data through true/false logic, time delays, or error messages |
| [Out-of-band SQL injection](./Out-of-band-SQL-injection/) | Use external interactions (e.g., DNS, HTTP) to exfiltrate data |

--

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


