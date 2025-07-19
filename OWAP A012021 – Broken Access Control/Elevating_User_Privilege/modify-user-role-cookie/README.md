\# Lab: Privilege escalation via cookie manipulation



\## Description

User roles are stored client-side inside a cookie. Attackers can edit the cookie to change their privileges.



\## Vulnerability Logic

Trusting client-side storage for sensitive values like roles is dangerous. Cookies can be easily modified.



\## Goal

Change your role to admin via the cookie and delete Carlos.



