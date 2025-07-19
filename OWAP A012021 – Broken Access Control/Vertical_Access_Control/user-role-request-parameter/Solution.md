\# Solution: User role controlled by request parameter



1\. Log in as a normal user.

2\. Intercept a request where `role=user`.

3\. Change the parameter to:

role=admin

4\. Forward the request. You should now have access to the admin panel.

5\. Delete the user `carlos` to solve the lab.



