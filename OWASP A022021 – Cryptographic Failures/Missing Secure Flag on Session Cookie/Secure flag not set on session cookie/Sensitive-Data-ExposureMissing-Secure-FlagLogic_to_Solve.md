\# Logic to Solve – Missing Secure Flag on Session Cookie



\## Lab title

Secure flag not set on session cookie  

(PortSwigger Web Security Academy)



\## Goal

Capture the session cookie by exploiting the fact that it is transmitted over HTTP, not HTTPS.



\## Vulnerability

\- The app issues a session cookie without the `Secure` flag.

\- All cookies without `Secure` can be sent over an unencrypted channel.

\- An attacker can intercept the cookie via a man-in-the-middle attack.



\## Why this works

\- Without `Secure`, cookies are included in HTTP requests.

\- On an insecure network, attacker can sniff traffic and steal the session ID.

\- They can use the stolen cookie to impersonate the user.



\## Impact

\- Session hijacking and user account takeover.

\- Access to private data or elevated privileges.



