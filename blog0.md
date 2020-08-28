## Blog Zero

![Image](https://themaverick.github.io/seniordesign/gifs/matrixhasyou.gif)

### What?
This blog will continue my IT Security/insert cybersecurity buzzword journey starting with my PowerShell adventure and attempting to get this darn script I have fully matured and developed. It initially begins with having the end goal in mind since I am not starting with any sort of SDLC formalities or anything of that sort. The script is to have a menu where the user and select actions to complete, it must have a log of all items in the terminal, and finally actually function properly.

### Starting Features
```markdown
1. A user menu to select options
2. Manage the Windows Firewall
3. Run on at least PowerShell 5 (Windows 8 and beyond)
```
I'll be trying to get these features to work as soon as I can while juggling work around so let's see where it takes me. 
The user menu is important to have because it gives people the option to select something instead of automatically performing a bunch of tasks because environments are varied and have lots of different variables within them . I feel like this script is supposed to help simplify the firewalling process at least at a local level which can help with individual computers that might be air gapped on a network . Sometimes computers are not linked to any sort of domain or other computer systems on the same network. Since my main focus is Microsoft Windows, I will stick to using PowerShell as the native language and improve upon this depending on having the ability 2 automatically update PowerShell or install PowerShell which I think is a feature that could be used for various other purposes . As of now it is very complicated to install PowerShell on legacy systems since it requires a Patch and a framework to be installed and finally the actual PowerShell package itself if we are trying to update to PowerShell seven. 

## A user menu to select options

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