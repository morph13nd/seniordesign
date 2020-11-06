## Blog Nine

![Image](https://themaverick.github.io/seniordesign/gifs/DDoS.gif)

### Heavy Taffic on VLAN 405: Denial of Service Attacks
Denial of Service (DoS) is an attack on a computer or network that prevents legitimate use of its resources. In a DoS attack, attackers flood a victim’s system with illegitimate service requests or traffic to overload its resources and prevent it from performing intended tasks.

In a DoS assault, attackers flood a victim’s machine with nonlegitimate network requests or visitors to overload its resources, bringing the machine down, main to unavailability of the victim’s internet site or as a minimum substantially slowing the victim’s machine or network performance. The intention of a DoS assault isn't always to gain unauthorized access to a machine or to deprave data; it's for an attacker to render the valid customers having a machine slow machine or experience.

Perpetrators of DoS attacks normally target sites or services hosted on high-profile internet servers inclusive of banks, credit-card payment gateways, or even root nameservers.

### The technical item list
```
    Wireshark
    Metasploit
    Kali Linux x64
    Windows 10 (or an IPv4 enabled host)
    Perform a SPOOFED DoS attack by sending a large number of SYN packets continuously
    Perform a HTTP flooding attack
```
 
![Image](https://i.imgur.com/CI7jNog.png)

### Running Wireshark

Installing and running wireshark on the host is essential. This is the host where we will attempt a DDoS attack. Select the ethernet adapter. 


### Beginning to the DDoS Attack

I will SYN flood the Windows 10 machine on port 21. We then determine if port 21 is open or not. We will use nmap to determine the port status. Type nmap -p 21 [Windows 10 IP Address/other host] and press Enter.


![Image](https://i.imgur.com/8ig9vNs.png)

Now, type msfconsole and press Enter to start msfconsole.

### Starting up msfconsole

In msfconsole type use auxiliary / dos / tcp / synflood and hit Enter. This launches the synflood module.

![Image](https://i.imgur.com/xNidj2h.png)

Let's determine what module options need to be configured to start the DoS attack. So, type show options and hit Enter. This displays all the options associated with the plug-in. Here, we will SYN flood on port 21 of the Windows 10 machine by spoofing the IP address of Kali Linux with that of the Windows Server 2016 machine.

Issue the following commands:

Type set RHOST [Windows 10 IP Address] and press Enter 
Type set RPORT 21 and press Enter Type SHOST [Windows Server 2016 IP Address] and press 
Enter Type set TIMEOUT 20000 and press Enter
When setting the SHOST option in [Windows Server 2016 IP Address], is spoofing the IP address of the Kali Linux machine with that of Windows Server 2016.

![Image](https://i.imgur.com/iS0JIAf.png)
![Image](https://i.imgur.com/9OIjJzY.png)

### Wireshark Output

![Image](https://i.imgur.com/q6twWTY.png)

Wireshark shows the traffic coming from the machine, as shown in the screenshot. In the filter field, type tcp.port == 21 and click Apply this filter string to screen or press Enter button to view tcp packages. Here, you can see that the source IP address is that of the Windows Server 2016 machine. This implies that the Kali Linux IP address has been spoofed.

![Image](https://i.imgur.com/f4W0IXg.png)

### Viewing the results of the spoofed DoS attack

Open the task manager on the machine and click on the Performance tab. Wait 10-15 seconds; you will notice that the CPU usage has increased dramatically, which implies that the DoS attack is in progress on the machine. Nobody likes spiked CPU usage. Do you? Yes? You're the exception.

If the attack continues for some time, the machine's resources will be completely exhausted and it will stop responding.

Close all windows that were opened on Windows 10 machine and then go back to Kali Linux machine.

![Image](https://i.imgur.com/NE6Hj7w.png)

![Image](https://i.imgur.com/yQTaAfi.png)
