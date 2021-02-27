## Blog Fourteen: Digital Forensics & Incident Response - Detecting Startup Programs


### Detecting startup software introduction

Let's look for clues about the programs running on your PC at startup. You need a basic understanding of the components of the Windows operating system, such as the registry. 
### The technical goal list
```
Live Windows VM
Sysinternals
```

### What are startup programs?

The startup locations are configured as startup applications, as well as the full list of file system and registry locations available for startup settings. Startup locations include login entries, Explorer add-ons, and Internet Explorer add-ons, including Browser Helper Objects (BHO). ), Appinit DLLs, image hijacks, boot run images, Winlogon notification DLLs, Windows and Winsock layered service providers, media codecs and more. 
The autoruns app is excellent for this purpose.
![Image](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwww.maketecheasier.com%2Fassets%2Fuploads%2F2015%2F03%2Fstartup-managers-autoruns.png&f=1&nofb=1)


### The Autoruns application

![Image](https://i.imgur.com/GenzZ3j.png)

Try to find clues about persistent programs using the Autoruns application included in the Sysinternals Toolkit. Download and install Autoruns from here: https://docs.microsoft.com/en-us/sysinternals/downloads/autoruns You must absolutely install Autoruns. The executable can be run directly by double-clicking the "Run Now From" link. Autoruns divides the view into several tabs. Use the All tab for a simple search. 


### Why are you running? WHY ARE YOU RUNNING?

![Image](https://i.imgur.com/0oejmjz.png)

Use autorun to find programs that are marked to run but are no longer installed. If a program is registered to run in the registry at startup, but has been removed without removing the key, the computer will keep trying to run it. These programs are highlighted in yellow. Note that the programs shown in the example may be different for each new system you use. 
Look for registry keys that contain startup locations (at least three keys). In Autoruns, switch to the Login tab, which lists all the programs activated by the login service. Note that this must be done to filter the output. Triggers can also make programs run automatically. Common registry keys on every computer include 
### Some critical startup keys:
```HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Run
HKLM\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Run
HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\
```

### Find folders in startup locations.
The Login tab lists information about the programs that the login service activates. In this case, look at the folders. Most Windows versions include: Look for "Not Reviewed" in the Publisher column for each application. During automatic runs, the software labeled "Not Checked" is displayed in red. These are software applications whose publisher is unknown. While unverified software is not necessarily malicious, it should still be verified. 

- C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Startup
- C:\Users\JohnD\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup

![Image](https://i.imgur.com/HusS7pB.png)


Thank you!
