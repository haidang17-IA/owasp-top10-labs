\# Logic to Solve – Source Code Disclosure via Backup Files



\## Lab title

Source code disclosure via backup files  

(PortSwigger Web Security Academy)



\## Goal

Discover a backup file accidentally left on the web server and use it to read source code.



\## What is the vulnerability?

\- Developers sometimes leave backup or temporary versions of files on the server.

\- These might have extensions like `.bak`, `.old`, `~`, or even `.zip`.

\- If accessible over HTTP, attackers can download and view sensitive source code.



\## Why this works

\- There’s no access control preventing access to backup files.

\- If you know the file structure or naming convention, it’s easy to guess the backup name.

\- Source code may reveal credentials, logic, or hidden endpoints.



\## Impact

\- Reveal authentication logic

\- Bypass hidden paths or access controls

\- Leak hardcoded passwords or database details



