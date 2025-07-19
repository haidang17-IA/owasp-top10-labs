\# Lab: User role controlled by request parameter



\## Description

The user's role (e.g., user or admin) is defined client-side via a request parameter. An attacker can escalate privileges by modifying this value.



\## Vulnerability Logic

The application trusts a role parameter in the request. This is inherently insecure as it can be modified by a malicious user.



\## Goal

Access the admin panel by changing the `role` parameter to `admin`.



