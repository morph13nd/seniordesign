## Blog Four

![Image](https://themaverick.github.io/seniordesign/gifs/morph.gif)

### Windows and Backup images... let's face the reality.
In this blog I will discuss how I prefer to backup windows and the most successful method I've had in terms of backing up windows in a full disk image without destroying the image itself and having a very high success rate (100%) so far, compared to other imaging softwares that might cost a lot of money. Windows used to have a system image backup utility in Windows 7. 

![Image](win7bu.png)

### Out with the old, in with the new.
This is what it usually looked like in Windows 7 when you're trying to create a system image backup. In my experience the feature has been lacking and I have moved on to third party softwares and I prefer the macrium reflect software because it is free and it is constantly updated , also fantastic for home and personal use . They also work on releasing a windows RM feature boot into a drive and perform a restore.  Windows has used the volume shadow copy service VSS service to continually use our system restore functionality and for the backup and restore functionality, and it is concerning to continue using something since Windows 7 and in my experience in using the functionality to backup images via the windows backup and restore function, it has failed about 50% of the time after an approximate 2 hour image creation time. That's a lot of overhead. Macrium reflect takes an hour or less, depending on drive type and drive space.

![Image](https://themaverick.github.io/seniordesign/media/explorer_HNFPbqbgcB.png)

### The technical item list
```
1. Download and install Macrium Reflect.
2. Backup desired system configuration to create a golden image
3. Create bootable media drive
4. Attempt to restore your golden image!
```

### Macrium Reflect setup

<a href="https://www.macrium.com/reflectfree" target="_blank" rel="noopener noreferrer">Click here to download Macrium Reflect.</a> 

In my experience Macrium Reflect is pretty great, it is free software and you do not have to register for anything other than the first time by providing them an email address. You can use a burner email address if you'd like to that's your choice, you will then get a download link too a client downloader software to officially pull the latest version of macrium reflect from their servers. After you download it that, you will launch the installer and you walk through the installation wizard. 

![Image](https://themaverick.github.io/seniordesign/media/reflect-free-screen.png)

### Backup desired system configuration to create a golden image

![Image](https://themaverick.github.io/seniordesign/media/gold.png)

Now in my experience, and in any general information technology experience, there should always be some sort of backup solution for any kind of system whether that is development or production. There should also be routine backups with either full incremental or schedules involved. Personally, for me, I like to create a full back up every six months since I do not keep any important information on my local hard drive and I am strictly running software and critical files are stored otherwise. I am also very big on performance so it also depends on what kind of system you want. If you want to have a system that is very fast and lightweight and only has software that you want to use with specific tweaks , set your system up as such from scratch and use that as your Golden image so that way when you have to restore back to your system either for performance improvements as systems get laggy overtime , or just because you need a recovery and something crashed and the system is unrecoverable, this is definitely the way to go. Of course, everybody has their own system usages, so it is best for you to decide your own desired system configuration and call it your Golden image. I have heard this term used within the industry and I like it because it reminds me of Charlie and the Chocolate Factory.

![Image](https://themaverick.github.io/seniordesign/media/firefox_OOiWgXZnV3.png)

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




