## Blog Zero

![Image](https://themaverick.github.io/seniordesign/matrixhasyou.gif)

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

```markdown
function Show-WFW-Menu {
    param (
        [string]$Title = 'WFW Menu'
    )
    title "Windows Firewall Wizard by @1ncryption"
    Clear-Host
    Write-Host "=|=|=|=|=|=|=|=|=|=|=|=|=|=|=|=| $Title |=|=|=|=|=|=|=|=|=|=|=|=|=|=|=|="
    Write-Host "1. Troubleshoot inactive / disabled Firewall"
    Write-Host "2. Auto Identify existing GPO firewall rules"
    Write-Host "3. Active Directory Domain Controller"
    Write-Host "4. Read Only Active Directory Domain Controller"
    Write-Host "5. Workstation with no services"
    Write-Host "6. Server"
    Write-Host "Q: Press 'Q' (case sensitive) to quit."
}```
