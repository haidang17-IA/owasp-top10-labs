\# Lab: Insecure direct object references



\## Description

The application uses predictable identifiers to access sensitive resources. No access control is enforced.



\## Vulnerability Logic

Direct access to object references like files or user data is possible by manipulating predictable values.



\## Goal

Download another user's file by changing the object ID.



