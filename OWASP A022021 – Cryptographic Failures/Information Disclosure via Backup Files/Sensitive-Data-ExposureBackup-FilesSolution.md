\# Solution – Source Code Disclosure via Backup Files



\## Lab title

Source code disclosure via backup files

(PortSwigger Web Security Academy)



\## Step 1: Identify the main page

Visit the site and inspect the main functionality, like `/product?productId=1`.

View source code or URL paths to find file names, e.g., `product.js`, `login.php`.







\## Step 2: Try guessing backup file names

Try accessing common backup extensions:

/product.js.bak

/login.php.bak

/index.php~

/admin.old



Try these in the browser or Burp Intruder.





\## Step 3: Find a valid backup file

If you find a backup file (e.g., `/admin.bak`), download it.



Open and analyze the contents. Look for:

\- Hidden admin URLs

\- Credentials

\- SQL queries



\## Step 4: Use leaked info to complete the lab



If the file reveals an admin panel at `/admin-panel`, go there.



Use credentials or logic found in code to gain unauthorized access.



==> Lab solved



Once you access hidden content based on information in the leaked file, the lab marks as solved.

