## Blog Sixteen: Ethical Hacking - Building Your Own HTTP Server


## HTTP Servers! What?


We will become familiar with HTTP headers, Apache service control, configuration files, and a web development inspector tool. 

## What is HTTP?

HTTP is the basis of data communication for the World Wide Web, where hypertext documents contain hyperlinks to other resources that can be easily accessed by the user, e.g.  For example, by clicking the mouse or tapping the screen in a web browser. HTTP is a protocol that enables resources such as HTML documents to be retrieved. It is the basis for all data exchange on the web and a client-server protocol. This means that the requests are initiated from the recipient, usually from the web browser. A complete document is reconstructed from the various sub-documents obtained, e.g. B. Text, design description, images, videos, scripts and more.

## What is Apache?
Apache is an excellent application software. It is the most widely used web server application in the world. Apache is the most widely used web server application on Unix-like operating systems. It is a web server application based on a modular process that can create a new thread through each simultaneous connection. Multiple functions are supported; many of them are compiled into separate modules and their core functions are expanded. They provide everything from server-side programming language support to authentication mechanisms. This is an activity of the Apache Software Foundation. Some well-known companies that use Apache are Cisco, IBM, Salesforce, General Electric, Adobe, VMware, Xerox, LinkedIn, Facebook, Hewlett-Packard, AT&T, Siemens, eBay and many other older servers (source) are using 1995 today many cPanel hosts Apache. Like other web servers, Apache handles the hidden aspects of sharing your website's files with visitors. Because Apache doesn't do as well on some benchmarks, especially static or high-traffic websites, Kinsta uses the NGINX web server instead of Apache. Although NGINX first did so with Apache, its popularity and market share has grown rapidly since its launch in 2004.

### The technical goal list
```
Knowledge of Kali NIX
Basic understanding of networks
Basic understanding of HTTP
Environment & Tools
VirtualBox
Kali Linux
Apache2
Browser 
```

## Configure Apache

In this task, you will perform user-defined basic configuration for the Apache web server and change its standard monitoring port. Start the Kali computer.
Make sure that the Apache service has been installed on the computer. 
Start the Apache service.
Make sure that the service status is, and make sure it is active.
Open the Apache port configuration file.
Change 80 to 9191, and save the file to apply the changes.
Restart the service. notes. 
Every configuration change requires a restart. Server and make sure it is active

![Image](https://www.edustorage.net/files/LinuxLiteOS/linux-lite-status-apache2.png?7a1452def0)

## Enable HTTP Headers
In this task, you will enable the use of HTTP headers and create a custom header for the server. 
Open the inspector in the browser.
Enter the network information window. 
Click on the first GET request and look at the header to get the response. 
What is the content type? 
Enable the HTTP header in the terminal, and then restart the service. Note: Use a2enmod.

![Image](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fi.stack.imgur.com%2Fiv9N3.png&f=1&nofb=1)

Thank you!
