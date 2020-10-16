## Blog Six

![Image](https://themaverick.github.io/seniordesign/gifs/XSS.gif)

### Red Teaming: Cross Site Scripting Attacks
XSS attack exploits vulnerabilities that occur while processing input parameters of the end users and the
server responses in a web application. Today I will work on performing a XSS attack with a webserver and live website. Within the OWASP Top 10, A7 is Cross Site scripting as the #7 threat to websites. XSS flaws occur whenever an application includes untrusted data in a new web page without proper validation or escaping, or it updates an existing web page with user supplied data using a browser API that can create JavaScript. XSS allows attackers to execute scripts in the victim's browser which can hijack user sessions, deface web sites, or redirect the user to malicious sites. This can be used to bypass a Web Application Firewall (WAF). 

### The technical item list
```
Web parameter tampering
Performing a cross site scripting attack on a Windows Webserver
Local Area Network: MovieScope
```
 
![Image](https://themaverick.github.io/seniordesign/media/firefox_FE03vorwgR.png)

### Threats of XSS

Malicious script execution can occur which can create or leverage legitimate components on the website to give further access or persistence to an attacker. Session hijacking can be used to steal a user's active session and hijack the account without the password. Redirecting to a malicious server would be dangerous since it can automatically exploit a visiting user or phish them.


### Logging in with the default credentials for the webserver

Here I will log in with the user John. 

![Image](https://themaverick.github.io/seniordesign/media/firefox_KLVE4UbbTW.png)


### Viewing John's Profile

![Image](https://themaverick.github.io/seniordesign/media\firefox_0OWzUW2VLm.png)


### Attempting to view Sam's profile without logging in

Here I can change the profile ID value to 1 to see Sam's personal information. This allows us to access it via HTTP WEB 1.1 without having us hack the database directly.

![Image](https://themaverick.github.io/seniordesign/media\firefox_eseuwQwXZo.png)

![Image](https://themaverick.github.io/seniordesign/media\firefox_Py3BooLJOQ.png)

### XSS Attack on the Contacts page

This is where we insert a script via JavaScript on the page to do the XSS attack. The `<script>` tag is where we insert our payload. Here I have inserted a fun little cheesy line. Click the Submit Comment.

```
The Maverick <script>alert("You are PWND")</script
```

![Image](https://themaverick.github.io/seniordesign/media\firefox_dpkUELpxEP.png)

Google Chrome attempts to warn the user about the XSS attack, but, it fails anyways! These security measures must sanitize HTML inputs from the client side and server side (preferrably to prevent these).

![Image](https://themaverick.github.io/seniordesign/media\firefox_QFlwGJckg8.png)

### Persistent XSS Attack Demo Sucessful!

Now if I log in as another user, steve, I will receive the XSS attack message. The XSS attack has been successful, and can run scripts unauthorized on the user's end.

![Image](https://themaverick.github.io/seniordesign/media\firefox_LOEfM4MQtj.png)

![Image](https://themaverick.github.io/seniordesign/media\firefox_PqYwXVhP20.png)