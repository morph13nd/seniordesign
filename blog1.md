## Blog One

![Image](https://themaverick.github.io/seniordesign/gifs/neowhat.gif)

### What?
Just the other day I was asked by someone in the cybersec industry for some PowerShell advice to locate a file on Windows using only native langauges. He was curious as to how I could do this in a one liner, or even better, a PowerShell script. His issue was locating a file given a file hash of a video he needs to edit without knowing the file name. I tried writing it in under 10 minutes, and it was a great success! Here is what I did.

### Starting Features
```markdown
1. Obtain listing of all objects in the local disk where the dcript is run
2. Hash each object and obtain full file path, suppress other files that do not match 
3. Immediately check the hash of the object and compare it with the sought after hash
4. Return file location, hash, and name
```


## Obtain input of hash

![Image](https://themaverick.github.io/seniordesign/gifs/b01.png)

So I have a four loop that I'm going to use to call back the menu anytime that the menu is finished or a process has finished a selection item so that way people can resume their work on the menu screen . It also helps keep the software consistent to stop someone starting to deviate from the original intent of the program. I know I'm using the words software program and possibly the word script interchangeably so please bear with me. I have the full permission from @1ncryption to continue with using his skeleton function code.  

## Manage the Windows Firewall

Managing the windows firewall is sometimes quite difficult so I figured that each of these options would prepare us for using another component of the firewall. I was thinking of adding an nmap feature to this so that way I can check if the ports are actually open using one of the special nmap flags and this way we would know for sure what would happen - If the script actually works the way it is intended . I want to whitelist and make sure that it is confirmed to work. 

The first step is to try and obtain all of the IP address is required and the direction of these never channels are supposed to be communicated, Then specify what protocol and port needs to be communicated as well so that way it can be opened and everything else can be closed or at least it can appear closed to other attackers . This way we are mitigating risk while maintaining our availability and confidentiality . 

## Run on at least PowerShell 5 (Windows 8 and beyond)
```markdown
powershell.exe -Version 5.0 .\<ScriptName>.ps1
``` 
This should allow us to run with PowerShell version 5 without having any other conflicts in programming a PowerShell script. Unfortunately this is only OK with Windows 8 and beyond and PowerShell 5 is slightly more difficult to install on a Windows 7 unpatched version professional ultimate or any other edition for that matter. That would be the next challenge is to attempt to script a Automatic PowerShell updater. This might be a project in itself.