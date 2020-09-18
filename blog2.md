## Blog Two

![Image](https://themaverick.github.io/seniordesign/gifs/neowhip.gif)

### Windows Firewall Wizard Updates
The next part of the agenda is to analyze services that are required by Active Directory to function normally within they give an Active Directory environment such as remote procedure protocol and group policy and authentication services such as Kerberos and shomba protocol. I've taken The Liberty of doing research into the protocols that are required and baked into the script all of the necessary ports to properly secure Active Directory using the PowerShell script at the firewall level , the application firewall level to be specific. Not only that but I've also baked in my personal strategy in performing an IP whitelist which allows us to block unwanted IP addresses that are not on the list.

### Construction
```markdown
1. Analyze Active Directory Services
2. Identify ports required
3. Pass user-input into the script of IP addresses
```

## Standby

    ````New-NetFirewallRule -DisplayName "Allow DNS Outbound" -Direction Outbound -Program "C:\Windows\System32\dns.exe" -RemoteAddress $IP -Action Allow -Enabled True -InterfaceType Any -Profile Any -RemotePort Any -Protocol UDP -LocalPort 53
    New-NetFirewallRule -DisplayName "Allow DNS Inbound" -Direction Inbound -Program "C:\Windows\System32\dns.exe" -RemoteAddress $IP -Action Allow -Enabled True -InterfaceType Any -Profile Any -RemotePort Any -Protocol UDP -LocalPort 53```

The needle in the haystack (all the hard drive files we are searching for) is our desired hash. To find this hash we store it into a variable so this way the system can know what to look for in memory.  

## The one liner

The glory of the one liner is that the code is condensed into one line and does not have multiple lines while still completing the job of the script. It is mostly to show off a condensed script. PowerShell one liners have been a thing for quite some time now in industry!

Here is what I wrote:

```
Get-ChildItem -Path C: -recurse | Group-Object Length | Select-Object -ExpandProperty group | ForEach-Object -Parallel  {get-filehash -literalpath $_.fullname} | Where-Object { $_.Hash -eq $needle } -ErrorAction SilentlyContinue
```

Get-ChildItem will obtain a directory listing of the C: drive, which can be converted to a variable to obtain a listing of a drive letter supplied by the user. By we begin to group objects by their length and choosing an object to final their file name which supplies us with their literal paths (full directory path) to a given file. We use the ForEach-Object running in Parallel processing for faster hashing and overrall consuming less time than tpyical without ![parallel processing](https://devblogs.microsoft.com/powershell/powershell-foreach-object-parallel-feature/). Get-FileHash will obtain a hash of each file in the default SHA-256 algorithm. 

Of course, the algorithm can also be changed with the `-Algorithm` flag and other hashing is supported such as MD5 or other variations of SHA. Finally, we will examine each object for our desired needle (the inputted hash by the user). At the end of the script, upon error, we suppress these since there can be access issues to more sensitive system files. 

I believe he was quite happy with the result and was able to locate the file. Fun times!

Download link to script: https://themaverick.github.io/seniordesign/scripts/ps1/File-Identification.ps1

Please credit this blog for any use of this script and @1ncryption.