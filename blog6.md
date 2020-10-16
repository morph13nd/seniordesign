## Blog Six

![Image](https://themaverick.github.io/seniordesign/gifs/XSS.gif)

### Red Teaming: Cross Site Scripting Attacks
XSS attack exploits vulnerabilities that occur while processing input parameters of the end users and the
server responses in a web application. Today I will work on performing a XSS attack with a webserver and live website. Within the OWASP Top 10, A7 is Cross Site scripting as the #7 threat to websites. XSS flaws occur whenever an application includes untrusted data in a new web page without proper validation or escaping, or it updates an existing web page with user supplied data using a browser API that can create JavaScript. XSS allows attackers to execute scripts in the victim's browser which can hijack user sessions, deface web sites, or redirect the user to malicious sites. This can be used to bypass a Web Application Firewall (WAF). 

### The technical item list
```
Performing a cross site scripting attack on a Windows Webserver
Local Area Network: MovieScope
```
 
![Image](https://themaverick.github.io/seniordesign/media/firefox_FE03vorwgR.png)

### Threats of XSS

Malicious script execution can occur which can create or leverage legitimate components on the website to give further access or persistence to an attacker. Session hijacking can be used to steal a user's active session and hijack the account without the password. Redirecting to a malicious server would be dangerous since it can automatically exploit a visiting user or phish them.


### Logging in with the default credentials for the webserver

![Image](https://themaverick.github.io/seniordesign/media/firefox_KLVE4UbbTW.png)


### Viewing John's Profile

![Image](https://themaverick.github.io/seniordesign/media\firefox_0OWzUW2VLm.png)


### Attempting to view Sam's profile without logging in

![Image](https://themaverick.github.io/seniordesign/media\firefox_3GGODLvRvW.png)

Surprisingly, those windows updates that destroy your computer every time, are actually still very important for your computer to have. Those operating system updates are what keep the gears that operate all of the applications that run on top of it in top shape and Patch major security vulnerabilities that hackers and script kiddies can use to exploit the operating system. Operating system patches are more relevant than ever and must be applied more frequently and as frequently as they are released in a production environment this may usually require some sort of testing period unfortunately, in home environments, there is no such thing as testing without a home lab. I highly encourage people who are windows enthusiasts and NIX based enthusiasts to have a home lab to test their updates prior to having them released in their production environment which may or may not be someones gaming PC . In hive storm the competition, updates are absolutely low hanging fruits and a no brainer and should always be performed for local hardening. 