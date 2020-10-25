## Blog Eight

![Image](https://themaverick.github.io/seniordesign/gifs/XSS.gif)

### Incident Management: Vulnerability Analysis
Attackers perform vulnerability analysis to identify security loopholes in the target organization's
network, communication infrastructure, and end systems. The identified vulnerabilities are used
by the attackers to perform further exploitation on that target network. 

On the other hand, vulnerability assessment plays a major role in providing security to any
organization's resources and infrastructure from various internal and external threats. To secure
a network, an administrator needs to perform patch management, install proper antivirus
software, check configurations, solve known issues in third party applications, and troubleshoot
hardware with default configurations. All these activities together constitute vulnerability
assessment.


### The technical item list
```
Kali Linux
Webserver of your choice (LAN http://www.goodshopping.com)
CGI Scanning with Nikto
```
 
![Image](https://themaverick.github.io/seniordesign/media/firefox_FE03vorwgR.png)

### Threats of CGI files

CGI files are important for servers to execute on a console at the end of the server on the server side and the server can determine what the script is executing. These can also be manipulated by attackers to gain a foothold on a given server or network. Nikto will help us scan and detect any outdated versions of CJ files and check other miscellaneous server configuration files such as having numerous indexes, HTTP server options and it will try and footprint the server. 


### Beginning to analyze the webserver

Here we start a scan off with ` nikto -h http://www.goodshopping.com -Tuning 1`. 

![Image](https://themaverick.github.io/seniordesign/media/nikto.png)

Some interesting items that we can see include part of the footprint of the server being a Microsoft Internet Information Services server running version 10 and that the anti clickjacking extreme options header is not being used which could present opportunity. We can also see all of the public HTTP methods that are allowed on the server and see that there are no CGI directories found. 

### Multiple hosts attempted scan via Nikto

By calculating your IP address of your host, you can attempt to scan multiple hosts with Nikto in an IP address list.


![Image](https://themaverick.github.io/seniordesign/media\ipcalc.png)

Next we will use our `10.10.10.0/24` network as our basis, and it looks like we have some hits. 

![Image](https://themaverick.github.io/seniordesign/media\nmapo.png)

### Creating an IP address list based on output

Run `cat themaverick | awk '/Up$/{print $2}' |  cat > webserverList.txt` to get a list of the IP addresses.

Here I can see all the IPs of webservers I might want to hit, assuming they run on port 80 for this demonstration.

![Image](https://themaverick.github.io/seniordesign/media\victims.png)


### Executing Nikto on the final output of IPs

And finally the fireworks of Nikto scanning our IPs successfully via `\n` delimitted list.

![Image](https://themaverick.github.io/seniordesign/media\nn.png)