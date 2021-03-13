## Blog Fifteen: Ethical Hacking - Windows Privilege Escalation (PE)


## Windows PE introduction

We will try to understand how to use privileges to access your Windows device in a special way step by step and how to handle this attack. We will attempt to practice and implement local techniques for elevating privilege and mitigation on Windows systems.

### The technical goal list
```
VirtualBox/VMWare
Windows 7 (pre-installed)
Windows 7 installer file compressed
Windows 10 (extra)
Familiarity with the Windows environment and processes
```

## Mount the OS first

First, we will work with repair tools, and open the CMD for later use.
Use a Windows OS CD to boot Windows 7 over the existing Windows 7 OS.
Mount the ISO via the Devices tab from the menu. Open the optical drives selection and select Choose/Create a disk image. 

![Image](https://i.imgur.com/eHSGyPA.png)

## Begin breaking into the system
Press any key to start the installation. Instead of installing the system, open the command prompt. 
Click Next on the first screen. 

Choose Repair Your Computer. 

![Image](https://i.imgur.com/yNfG2Fv.png)

On the next screen, click Next to select your Windows 7 operating system. 


![Image](https://i.imgur.com/YEBsWKl.png)


![Image](https://i.imgur.com/JmWgrtN.png)

Choose Command Prompt.

![Image](https://i.imgur.com/ewHq64w.png)

## Swap out files

Look for the local disks.
Make a backup and replace sethc.exe with cmd.exe in Windows\system32.

Using the following command in CMD to find the local disk:
```
logicaldisk wmic get name
```

![Image](https://i.imgur.com/i7SuF0L.png)

![Image](https://i.imgur.com/i7SuF0L.png)

## Manipulate the file system

To get to D:\windows\system32, type D: and press Enter.

Make a copy of the original sethc.exe file before renaming it, as follows:

sethc.exe should be copied.

![Image](https://i.imgur.com/VvC8gQ4.png)

sethc2.exe copies the sethc.exe-named CMD file.

To overwrite, select copy cmd.exe sethc.exe and “yes.”
![Image](https://i.imgur.com/58eVeyr.png)

From the command prompt, restart the virtual machine and run sethc.exe from the Windows logon panel.
It's worth noting that cmd.exe is a command-line program. 

It's worth noting that cmd.exe, rather than sethc.exe, runs with NT privileges.

![Image](https://i.imgur.com/CdXMXJ9.png)

Remove the installation iso picture from your device. To unmount the disk file, go to the devices tab. 
To restart, type shutdown -r at the command prompt. 
![Image](https://i.imgur.com/0NV14xx.png)

Click Shift five times after the system has restarted.
Instead of sethc.exe, Cmd.exe can be used. 

## Witnessing the PWNAGE

When you type "whoami," you'll notice that it says "nt authority\system," which is the most privileged person. 

![Image](https://i.imgur.com/g1GANq4.png)

Thank you!
