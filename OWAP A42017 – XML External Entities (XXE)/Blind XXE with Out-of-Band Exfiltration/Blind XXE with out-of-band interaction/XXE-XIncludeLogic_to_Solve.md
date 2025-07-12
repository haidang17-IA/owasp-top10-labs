\# Logic to Solve – XXE with XInclude



\## Lab title

Exploiting XInclude to retrieve files  

(PortSwigger Web Security Academy)



\## Goal

Use XInclude instead of DOCTYPE to read a file on the server (for example `/etc/passwd`).



\## What is the vulnerability?

\- The application builds XML internally using data sent by the client.

\- The attacker cannot modify the full XML payload (no DOCTYPE access).

\- BUT the server processes XInclude tags, allowing external content inclusion.



\## Why this works

\- XInclude lets you reference external content from within XML.

\- Even if DOCTYPE is not allowed, XInclude can still load remote or local resources.

\- When included, the file content appears in the processed XML output.



\## Technical details

\- Add `xmlns:xi="http://www.w3.org/2001/XInclude"` at the root.

\- Insert `<xi:include parse="text" href="file:///etc/passwd"/>` in a tag that gets reflected.

\- The server includes the file contents during XML processing.



\## Impact

\- Attacker can read critical files without using DOCTYPE at all.

\- Common in apps embedding user data into internal XML, like SOAP or integrations.



