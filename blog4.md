## Blog Four

![Image](https://themaverick.github.io/seniordesign/gifs/morph.gif)

### Windows and Backup images... let's face the reality.
In this blog I will discuss how I prefer to backup windows and the most successful method I've had in terms of backing up windows in a full disk image without destroying the image itself and having a very high success rate (100%) so far, compared to other imaging softwares that might cost a lot of money. Windows used to have a system image backup utility in Windows 7. 

![Image](win7bu.png)

### Out with the old, in with the new.
This is what it usually looked like in Windows 7 when you're trying to create a system image backup. In my experience the feature has been lacking and I have moved on to third party softwares and I prefer the macrium reflect software because it is free and it is constantly updated , also fantastic for home and personal use . They also work on releasing a windows RM feature boot into a drive and perform a restore.  Windows has used the volume shadow copy service VSS service to continually use our system restore functionality and for the backup and restore functionality, and it is concerning to continue using something since Windows 7 and in my experience in using the functionality to backup images via the windows backup and restore function, it has failed about 50% of the time after an approximate 2 hour image creation time. That's a lot of overhead. 

![Image](https://themaverick.github.io/seniordesign/media/explorer_HNFPbqbgcB.png)

### The technical item list
```
1. Download and install <a href="https://www.macrium.com/reflectfree" target="_blank" rel="noopener noreferrer">Macrium Reflect.</a>
2. Backup desired system configuration to create a golden image
3. 
```

### Starting up Kali

![Image](https://themaverick.github.io/seniordesign/media/vmware_1.png)

It is now time to start the pentest and launch up the Kali OS. Logging in is always fun.
(Especially when you're using someone else's password.) But, still is just my password.
You can choose whatever Type 1 virtualization software you would like to use, I prefer my copy of VMWare Workstation 16 (which was just released!) I prefer the plenty more RAM for the Nessus vulnerability scans since it can take a very long time otherwise.

![Image](https://themaverick.github.io/seniordesign/media/vmware_l4DCtNyif1.png)

### Launching metasploit and performing beginner reconaissance

Now that I have entered my lab network where the vulnerable machine is, I have to decipher which private IP address is it really located on.
Knowing how virtual adapters work, the tap0 is likely our target network. I used grep to shorten the output and get to the point.

### Some innocent scanning after basic reconaissance

We have to audit and locate our network topology under the network `192.168.99.0/24` and identify our target machine. We are `192.168.99.100` as indicated in the screenshot above which places us directly on the same network as our target machine. To hide our tracks and make it more difficult to trace, we launch a specific nmap scan. In this instance, there could or could not be a firewall to block sequenced scans. We are doing a ping sweep to see who lives on the network. It seems it is only us two, me and .12.

![Image](https://themaverick.github.io/seniordesign/media/vmware_6Dr7HgkZ3A.png)

Let's see some verbose output with that!

![Image](vmware_voSMMC0AaM.png)

Now we can see the host is responding to pings and we can now perform a vulnerability scan upon the host machine, which is typically loud and obvious on a network which can be shown in the network logs but it is industry standard practice. 

### The vulnerability scan. Wake up, Windows XP.

![Image](https://themaverick.github.io/seniordesign/media/vmware_J0nvBz7EQX.png)

As we startup Nessus within Kali and access it via web browser from our locally hosted virtual machine we can begin our scan. In the event we do not have a nessus instance available we can still run using `nmap -T4 -v sV 192.168.99.12` and add vulnerability scanning scripts that come with the nmap package on some operating systems. The scan could take up to 15 minutes, as I am typing the blog, Nessus has found 3 vulnerabilities already.

![Image](https://themaverick.github.io/seniordesign/media/vmware_UGn8d9xGTL.png)

There are plenty of Server Message Block protocol vulnerabilities present on this machine. Let's see if we can run with an eternal blue MS-17-010 exploitation and see where it takes us.  

![Image](https://themaverick.github.io/seniordesign/media/vmware_mon6BRKoIz.png)

It would seem that we have copies of the python based CVEs within our Metasploit arsenal, and our Nessus scan has shown that is possible to exploit.

![Image](https://themaverick.github.io/seniordesign/media/vmware_FWUq1dUQAQ.png)

Let us exploit this now and see where it takes us. We will receive a reverse TCP tunnel based shell meaning we will connect back to the computer from our computer from within the exploited service's TCP tunnel.

![Image](https://themaverick.github.io/seniordesign/media/vmware_FWUq1dUQAQ.png)

Our shell attempt seems to have failed after hanging on the above section. 
Let us result to other methods since we know the service is exploitable. By knowing some Windows command line ninjitsu, we can launch our exploit even more sneakingly by running commands remotely on the target system with a lesser likelyhood of crashing the system due to the tendancy of MS-17 as shown below.

![Image](https://themaverick.github.io/seniordesign/media/vmware_SMlzQ0LcWh.png)

![Image](https://themaverick.github.io/seniordesign/media/vmware_3Gk7HzVspg.png)

![Image](https://themaverick.github.io/seniordesign/media/vmware_Pb12GbfIWl.png)

The three options within Metasploit are the options we want to set to target our beloved Windows server. RHOST is the remote host, RPORT is the remote port, and COMMAND will follow the command which brings us the magic we are looking for: Administrator access.

This one liner should allow me to get Administrator access in a matter of a minute now. It enables the default highest-privilege account that has a Logon UI known as the Administrator account built-in and cannot be deleted from Windows. It is painful to secure and can be often overlooked by some security teams. The command also changes the password so I can log in to it. Let's take a look at what happens.

### Successful Administrator Access Granted


<a href="https://themaverick.github.io/seniordesign/media/finaldemo.gif" target="_blank" rel="noopener noreferrer">Click here to view the demonstration.</a>

Clearly we can see that I have Administrator access here and I have verified it by running `qwinsta` to show our Remote Desktop Protocol session is active and it is indeed me on Windows XP. I hope you enjoyed this demonstration of my penetration testing adventure in preparation for another certification. Mission success.




