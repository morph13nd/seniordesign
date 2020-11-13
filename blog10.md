## Blog Ten: Gathering information from open sources using Windows command line utilities 

![Image](https://themaverick.github.io/seniordesign/gifs/recon.gif)

### Reconaissance could mean the success or failure of a pentest
Reconnaissance is the collection of information about a target. 
It has its roots in military operations where it refers to enemy intelligence gathering missions. Gathering information is the first step in any attack on information systems. This helps the attackers reduce their effort and helps them choose their attack weapon. Attackers use the target's information to create a diagram or trace of an organization to help them choose the most effective strategy for compromising system and network security. 

Similarly assessing the security of a system or network begins with target recognition and fingerprinting Ethical hackers and penetration testers pens must gather sufficient information about the purpose of the evaluation before proceeding with the evaluation. Ethical hackers and penetration testers should model all the steps an attacker would normally take to gain a clear understanding of the target organization's security posture.

### The technical item list
```
 A live webserver you spin up
 An IP address of the webserver
 Ping command
 Tracert command
 Identify the maximum frame size for the network
```
 
![Image](https://i.imgur.com/ermkHNc.png)

### Running the ping command

Type ping 10.10.10.16 in the command prompt window and press Enter to find out its IP address. The response displayed should be similar to the one shown in the screenshotNote the IP address of the destination domain in the output above 10.10.10.16. The ```-t``` flag is meant to perform a non-stop ping regardless of the response back from ICMP, which is the protocol that ping uses.


### Frame sizing 

Ping 10.10.10.16 -f -l 1500 and press Enter Answer the packet should be fragmented but setting DF means that the frame is too large to fit on the network and should be fragmented. The f option sets the Do Not Fragment bit in the ping packet. By default the ping packet is fragmented Because we used the f option with the ping command the packet was not sent and the ping command returned this error. 


![Image](https://i.imgur.com/6nsd9nb.png)

In the ping command, the –l option means to send the buffer size.

### Playing around with DF and frame sizes.

Type ping 10.10.10.16 –f –l 1474 and press Enter.
The command replies with Packet needs to be fragmented but DF set.

![Image](https://i.imgur.com/OyKM8sz.png)


The command replies with a successful ping. 
The maximum frame size will differ depending upon on the target network.

![Image](https://i.imgur.com/rnQpYH1.png)

We have now used the ping utility to emulate the tracert (traceroute) command. 

### Tracert command

![Image](https://i.imgur.com/tbFIHaa.png)

This command traces the network configuration information for the target domain. In this demo the command finds the target website in one hop because it is hosted locally on a Windows Server 2016 machine. 
