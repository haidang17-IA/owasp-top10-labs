\# Lab: Unprotected admin functionality



\## Description

This lab contains an unprotected admin panel that is not properly restricted. Normal users can access administrative functionalities by directly visiting the admin URL.



\## Vulnerability Logic

The application lacks proper access controls for the `/admin` endpoint. It assumes that only admins will visit this URL and does not enforce authorization on the backend.



\## Goal

Delete the user `carlos` using the unprotected admin functionality.



