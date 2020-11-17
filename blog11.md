## Blog Eleven: How to join vCenter 6.7 build 8170087 and Windows Server 2016 Active Directory configuration 

![Image](https://i.imgur.com/hA8kbZm.png)

![Image](https://i.imgur.com/Y1GFh0C.png)

![Image](https://themaverick.github.io/seniordesign/gifs/doyou.gif)

### Multiple sysadmins need multiple permissions to do multiple things

This integration works with both the Windows and appliance version of vCenter Server. In the case of vCenter Server 6.7, what we are actually adding to AD is the Platform Services Controller component. This is true regardless of whether the PSC is implemented as integrated or standalone. The reason for this is that PSC is the component that handles the authentication and SSO tasks.

It is very important to seperate privileges for vCenter from a security standpoint. The subject should only be granted the minimum required rights to access a resource and they should be in effect for the shortest time necessary remember to relinquish privileges. Granting a user permissions beyond the scope of the necessary rights of an action may allow that user to obtain or change information in unwanted ways.
Therefore, careful delegation of access rights can prevent attackers from damaging a system.

### The technical item list
```
 A writable domain controller
 SSO Identity Source
 An instance of vCenter
 A fully qualified domain name must be used for vCenter when adding it to AD
 Proper clocks
 Proper firewall
 Proper DNS
 Local account on vCenter
```

### Access vCenter and browse to the Administration section

![Image](https://i.imgur.com/oly6WGZ.png)

I am accessing my personal laboratory. 

![Image](https://i.imgur.com/akHJuna.png)

![Image](https://i.imgur.com/ypNZw3k.png)

![Image](https://i.imgur.com/jdxNH6a.png)

![Image](https://i.imgur.com/PDCbGun.png)

![Image](https://i.imgur.com/kL2yWeT.png)

### Reboot vCenter

As per usual, ensure no virtual machines are running or services that depend on this vCenter instance.

I am stopping the relevant vCenter services and then rebooting my Windows Server 2016 in this instance.

Try stopping the services as below and then restarting Windows. This process may take a few minutes.

![Image](https://i.imgur.com/pw7U3Ll.png)

Verifying that vCenter is going down.

![Image](https://i.imgur.com/0lJxh2Q.png)

![Image](https://i.imgur.com/cqtPxtf.png)

Ensure the services are down, then reboot.

![Image](https://i.imgur.com/bdKX8mX.png)


### Post reboot checking services 

![Image](https://i.imgur.com/UzKzvvW.png)
