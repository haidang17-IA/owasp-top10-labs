\# Lab: User ID controlled by request parameter



\## Description

User profiles are accessed using a `id` parameter in the query string. An attacker can change this to access another user's data.



\## Vulnerability Logic

The application does not validate that the requested ID belongs to the current user, leading to Insecure Direct Object References (IDOR).



\## Goal

Access Carlos's account page by modifying the ID.



