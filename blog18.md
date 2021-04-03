## Blog Seventeen: Beginners Footprinting


## Footprinting


When it comes to penetration testing and target fingerprints, the goal is to determine what information is publicly available on your target. This is information that is available on the Internet, e.g. B. network architecture, operating systems, applications or users. This is passive in that, as a pen tester, you have tried every possible way to find hosts or networks. It could be one of them, but you should collect as much information as you can in every possible way. possible before proceeding to the next stageIf you find sensitive information on a publicly accessible website or location, that information should be reported to the organization in your report. When you find information that you think is critical and you think you shouldn't wait a month. or even a week before submitting the full report, you want to notify your emergency contact immediately. This stage of the attack should help prevent information leaks and assist you with social engineering attempts. Let's see the details.The first thing you can do is get the right clearance, and it will be whoever is in charge. It may or may not include system administrators.

## Utilities to perform footprinting

Companies often need to know how their system administrators behave. After going through this process, you need to make sure that you define the area. The prerequisite is the restriction of the scope of the penetration test. When you go through this phase, you will be able to configure the list of items to be tested. For example; What are the IP ranges or subnet ranges of the systems or what are their limitations? Now that you've defined your area, you need to use your discovery tools to plan and collect information about that area.Engines like Google, Bing or Yahoo whatever you need to use to see what information is currently available. You can also check some other specific websites like social media sites like Facebook and see if there is a Facebook Page or Twitter account. . for the company. Next, you need to see who is friends with this company as you can find existing employees there and see if you can step down from there. After you've scoured the search engines, it is a good idea to try to see if you can hack them from Google.You can do this by using additional tools that give you a graphical user interface like SiteDigger or Google's Hacking Database. Google hacking can help you find resources that have been crawled by the Google search engine that businesses may not know are listed there. B. Printers or cameras that can give you an idea of ​​what IP addresses are available or what machine they have. The next step after the Google hack is to search for social networks like Facebook, Twitter or LinkedIn. on the social media level to keep your guardsIt's easy to see what people are talking about, but initial conversations with users or staff can be a great way to gather info.
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
