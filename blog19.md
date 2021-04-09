## Blog Eighteen: Performing MITM with SSLStrip Tool

![Image](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fblog.checkpoint.com%2Fwp-content%2Fuploads%2F2016%2F03%2FSSL-Stripping-2.png&f=1&nofb=1)

## Rogue Access Points

We will utilize rogue access points to manipulate SSL traffic.To complete this attack, you need a USB network adapter that supports both monitor and master modes. If you don't have a USB network adapter that supports these network modes, the network adapter I recommend is the Alpha I discussed earlier. It only costs around $ 50, and you can buy one on Amazon as well as a few other places. The attack works.For the sake of illustration, let me provide a high-level overview of how this attack works. The main components include the victim, the attacker, the rogue access point, and an internet-connected router. The attacker is connected The attacker shares this Internet connection through a USB network adapter that acts as an unwanted access point. If someone connects to this rogue access point, they can access the internet.Let me guide you through this process. The first thing that will happen is that the victim connects to the spoofed access point and the victim's internet traffic is routed through the spoofed access point to the attacker. 

## Toolbox for Rogue APs

As soon as the attacker has received the victim's internet traffic, the attacker manipulates and logs the victim's internet traffic with an SSL strip. This allows the attacker to force the victim to use HTTP, which allows the attacker to capture any username. After the SSL strip processes and records the victim's internet traffic, the attacker forwards the victim's internet traffic to the router. Finally, the router forwards the victim's internet traffic to the website that the victim wants to communicate with. What we are doing here is that we put ourselves between the victim and the internet Website so that we can subsequently see what interaction is taking place between the victim and the website, and this is also known as a man-in-the-middle attack. This concludes the declaration. So let's get started. The first thing we need to do is connect to the internet. We achieve this by sharing the internet connection of our host operating system with our Kali Linux virtual machine. This is essentially a bridged or wired network connection and I chose this method to eliminate the need for a second USB network adapter.Note, however, that you can use a second USB network adapter to connect to the Internet directly from your Kali Linux virtual machine. Instead, I will read up on the method that I will share with you. Log into our host operating system. It doesn't matter what type of computer your Kali Linux virtual machine is running on, as long as you can use it to connect to the internet. First, open the network settings or the network management application used by your operating system.I can access mine from the top menu bar and then find a wireless network to connect to. Note that you can connect to any network you want as long as you have an internet connection. If you're mobile, you can have a connection to your Android or iPhone using a 4G USB modem, mobile hotspot, or any connection to the internet. Once you've connected to the internet on your host operating system, you'll need to share it with our Kali Linux virtual machine. Go ahead and switch to our Kali Linux virtual machine. In the top menu bar you need to open the virtual machine menu and thenExpand the Network Adapters menu. Here you need to make sure that we have configured our network adapter to use automatic bridge detection. This allows us to get an IP address and an internet connection from the router that our operating system is connected to. As soon as you have made these settings, you can hide the menu of the virtual machine. Now we can use this virtual network to connect to the internet. Next we open our network manager. By the way, you can use any network manager you have and this is where you should find the option that says"Wired Network," then click "Connect."

## Social engineering as part of the footprinting process

If you are the use of the default community supervisor you have to be connected
automatically, however in case you are not, you can want to reboot your virtual
gadget and also you have to receive a connection.
If you are nevertheless experiencing issues, I suggest putting in the “Wicd”
community supervisor. Moving on, now that we've a web connection, we
want to discover our gateway IP deal with and make notice of it.
Let's pass beforehand and near the community supervisor, and let's open a terminal
wherein you want to type:
“path space –n”
after which press ENTER, and pass beforehand and discover your gateway IP deal with. In
my setup it's far 192.168.zero.1, and we want to make notice of this due to the fact we're
going to apply it in a destiny command.
You can open a notepad or in case you need you may use a chunk of paper whatever
is handy for you and write down your gateway IP deal with. Now that
we have got made notice of our gateway IP deal with, we want to put in DHCP server.
Back into the Kali terminal, we are going to type;
“apt-get set up dhcp3-server”
after which press ENTER. Just be affected person and permit it sufficient time to finish
putting in the DHCP server, and as soon as the set up is entire we want to
configure our DHCP server.
Back to the terminal, let's type;
“nano /etc/dhcpd.conf”
after which press input, and also you have to have a clean DHCP D configuration
file. If it is not clean for a few reason, simply pass beforehand and delete all of the
contents and while you are prepared let's begin including our settings.
First we want to type:
“authoritative;
after which press ENTER and pass down a line, after which type;
“default-lease-time 600;
after which press ENTER to transport down a line, and type;
“max-lease-time 7200;”
after which press ENTER to transport down a line, after which type;
“subnet 192.168.1.zero netmask 255.255.255.zero ahead dealing with curly bracket” after which press
ENTER, and pass down a line after which type;
option routers 192.168.1.1;
after which press ENTER to transport down a line and type;
“option subnet-masks 255.255.255.zero;”
Then press ENTER and pass down a line, and type;
“option domain-name “freewifi”;
Then press ENTER and pass down a line and type;
“choice domain-name-servers 192.168.1.1;
after which press ENTER and pass down a line and type;
“variety 192.168.1.2 192.168.1.30;
}
after which press ENTER to transport down a line after which input a backwardsfacing
curly bracket. That's the whole thing we want to input. Once again, your
configuration have to appear to be this:
authoritative;
default-lease-time 600;
max-lease-time 7200;
subnet 192.168.1.zero netmask 255.255.255.zero {
option routers 192.168.1.1;
option subnet-masks 255.255.255.zero;
option domain-name “freewifi”;
option domain-name-servers 192.168.1.1;
range 192.168.1.2 192.168.1.30;
}

Thank you!
