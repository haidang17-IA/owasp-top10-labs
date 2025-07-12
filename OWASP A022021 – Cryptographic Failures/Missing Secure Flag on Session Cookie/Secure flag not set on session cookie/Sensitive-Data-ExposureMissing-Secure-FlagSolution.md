\# Solution – Missing Secure Flag on Session Cookie



\## Lab title

Secure flag not set on session cookie  

(PortSwigger Web Security Academy)



\## Step 1: Log in as test user



Use valid credentials to log in. The server returns a session cookie, e.g.:

Set-Cookie: session=ABC123; HttpOnly; Path=/

Notice: `Secure` flag is missing.





\## Step 2: Intercept the cookie over HTTP

Use Burp Proxy. The login request is unencrypted (HTTP).

Grab the cookie:

session=ABC123



\## Step 3: Replay the stolen session



In a new request (HTTP), set:

Cookie: session=ABC123

Load a restricted page to verify access is granted.



\## Step 4: Fix and verify mitigation

When `Secure` is added:

Set-Cookie: session=ABC123; HttpOnly; Secure; Path=/



The browser only sends the cookie over HTTPS, protecting it from theft on HTTP.

\## ✅ Lab solved

Once you can access user data with the stolen cookie, the lab is marked as complete.













