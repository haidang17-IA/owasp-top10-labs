\# Lab: Access control depends on HTTP method



\## Description

The application restricts some actions (like deleting users) only through POST requests, but forgets to enforce authentication.



\## Vulnerability Logic

An attacker can send a forged POST request to perform actions intended only for admins.



\## Goal

Craft a malicious POST request to delete Carlos.



