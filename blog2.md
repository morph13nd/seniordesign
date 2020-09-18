## Blog Two

![Image](https://themaverick.github.io/seniordesign/gifs/neowhip.gif)

### Windows Firewall Wizard Updates
The next part of the agenda is to analyze services that are required by Active Directory to function normally within an Active Directory environment such as remote procedure protocol and group policy and authentication services such as Kerberos and shomba protocol. I've taken The Liberty of doing research into the protocols that are required and baked into the script all of the necessary ports to properly secure Active Directory using the PowerShell script at the firewall level , the application firewall level to be specific. Not only that but I've also baked in my personal strategy in performing an IP whitelist which allows us to block unwanted IP addresses that are not on the list.

### Construction
```markdown
1. Analyze Active Directory Services
2. Identify ports required
3. Pass user-input into the script of IP addresses
```

## The DNS friendly script

    ```New-NetFirewallRule -DisplayName "Allow DNS Outbound" -Direction Outbound -Program "C:\Windows\System32\dns.exe" -RemoteAddress $IP -Action Allow -Enabled True -InterfaceType Any -Profile Any -RemotePort Any -Protocol UDP -LocalPort 53
    New-NetFirewallRule -DisplayName "Allow DNS Inbound" -Direction Inbound -Program "C:\Windows\System32\dns.exe" -RemoteAddress $IP -Action Allow -Enabled True -InterfaceType Any -Profile Any -RemotePort Any -Protocol UDP -LocalPort 53```


The domain name server is important for all communications within a given network to resolve addresses from octet IP addresses to full English name IP addresses for top level domain names and other domain names including subdomains. Therefore this is an example rule of a rule that creates an application specific rule that dictates DNS can only be communicated via a specific port through a specific application to a specific IP address to minimize and mitigate risk of the DNS executable Being compromised and sending out malicious information and ensuring that any requests open on port 53 must be handled by the dns.exe application. Otherwise all requests would fail , so if there were to be an exploit for the dns.exe application, it would work if dns.exe is vulnerable. If the exploit is delivered on port 53 and intended for another application running on port 53 like a backdoor, this would be blocked and mitigate C2 connections. 

###Next steps
Moving forward with the script, it would be more applicable to have input where an IP address is whitelisted and it is dependent upon its belonging as an IT system. If it is a server , it will have appropriate measures an appropriate fire rules implemented. If it is a client it will also have appropriate measures implemented. The script is meant for going into an environment where you do not know much about what is occurring, nor much of the address pool used. there should also be some flexibility in allowing or whitelisting subnets and CIDR notation.