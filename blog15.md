## Blog Fourteen: Digital Forensics & Incident Response - Performing Basic Malware Analysis


### Detecting potentially malicious startup software introduction

Our goal is to operate a malware detection system with a malware application model.

### The technical goal list
```
Basic knowledge of performing malware analysis using the tools described here
A piece of malware (custom coded for this blog)
http://wjradburn.com/software/PEview.zip
http://www.angusj.com/resourcehacker/
```

### What is malware?

Malware is a common term for malicious code that is designed to interfere with or damage the daily operation of a user's computer, mobile phone, tablet or any other device. There are many types of malware, including but not limited to worms, Trojans, spyware, and keyloggers.

![Image](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwww.dreamhost.com%2Fblog%2Fwp-content%2Fuploads%2F2018%2F06%2FMalware-Guide-DreamHost.jpg&f=1&nofb=1)

### Begin Investigating

Then search for the malware file to find all available information about the file. 
We will use PEView for this process.

After opening the malware file using PeView, we notice that the file contains five sections:
```
• .text
• .data
• .rdata
• .bss
• .idata
```

![Image](https://i.imgur.com/EqK6YfC.png)

### Technique Explanation

Start searching the file system using PEview. Using PEview, you can see the machine type with "IMAGE_FILE_HEADER". IMAGE_FILE_MACHINE_I386 This indicates that the file is based on x86 (32 bits).


![Image](https://i.imgur.com/ezMOTam.png)
![Image](https://i.imgur.com/w75rzmb.png)

Find the exact time stamp of the file to determine if it is valid. PEview has a value of IMAGE_FILE_HEADER. This value contains a minimum value called "DateTimeStamp" that contains a timestamp of Monday, January 01, 2035 00:00:00 UTC.

### Resource Hacker

![Image](https://i.imgur.com/wTIx6EC.png)

In all, Resource Hacker, is able to perform the Windows 7 and Windows 95 with Windows 95 with a synchronization files (.res) use use. This windows 10 using one of our favorite windows programs to organize different systems like DLL, can change the appearance of Windows 10. For example, you can change the appearance of many words, menus, and so on. You can also create the resource files (* .res) from scratches, and the new version provides a list of text samples for this easily. In 2002, the author said he had no plan to continue to develop. 

![Image](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fcdn.afterdawn.fi%2Fscreenshots%2Fnormal%2F14755.jpg&f=1&nofb=1)


Thank you!
