🚀 Steps to Solve the Lab (Simple English)
1.Go to the login page

URL: /login


2.Send a POST request in Burp Repeater:
POST /login
Content-Type: application/x-www-form-urlencoded
username=carlos
password=peter
Try same password with different usernames

3.Use Burp Repeater or Intruder to test:

carlos:peter
wiener:peter
bob:peter
...

4 .Look for a response without "Invalid username or password"

When login is successful, you’ll be redirected to my-account

5.✅ Log in as that user

You’ve now logged in with reused credentials

The lab is marked as solved
