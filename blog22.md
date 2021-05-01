## Blog Twenty Two: The Principles of Penetration Testing

![Image](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwww.proicttraining.com%2Fwp-content%2Fuploads%2F2019%2F07%2Fcomptia-pentest.jpg&f=1&nofb=1)

## Setup Airmon-NG

The different methods of performing penetration testing depend on the method you choose. There are a lot of standards out there. We'll cover a few of these so you can figure out which one will best suit your needs. Let's start with the OSSTMM, the acronym for Open Source SecurityTesting Methodology Manual. This standard set of penetration tests tries to achieve a high security matrix.There is another one called OWASP which stands for Open WebApplication Security Project. OWASP is an open source method that has numerous tools that can be of great help and a knowledge base, as well as a tool called ZAPP or Zed Attack Proxy Project. ZAPP is a tool with which you can automatically find vulnerabilities in web applications. ZAPP is designed for web developers, but pen testers can also use this tool.There is also another framework called ISSAF, the Information System Security Assessment Framework. ISSAF is also an open source project for performing a penetration test. ISSAF is supported by a group called the Public Information Systems Security Group. This is called NIST, which stands for National Institute of Standards and Technology. When it comes to NIST, you should know that the federal technology agency works with industryDevelopment and application of technologies, measures and standards. We also have LPT, which stands for EC-Councils License PenetrationTester. This is a proprietary method and there is another one from McAfee called Foundstone and we also have ISS, IBM. When it comes to IBM, they run your tests for you. They also had a function-based product called Proventia that is now being discontinued.It was a multifunctional security appliance and offered many different services for protecting or testing your network environment. The same applies to McAfee and Foundstone. Technically owned by Intel. With EC councils, LPT requires the auditor to follow many different steps, similar to CEHs.

## SSL Strip

Now its time to begin the SSL strip, so we could kind;
“sslstrip -f -p -ok 10000”
after which press input. Last however now no longer least, we want to begin edit app so we could open
a brand new terminal however do now no longer near the terminal that have been strolling an SSL strip
in. In the brand new terminal have been going to kind;
“ettercap -p -U -T -q -i at0”
after which press Enter. Now that we've SSL strip and ettercap strolling, we
are completed putting in the attack. Now we will simulate a sufferer so we will
use our faux get right of entry to factor to seize a few usernames and passwords.
So now in case you leap over to the sufferer’s computer, the primary aspect you may do
is connect with the faux get right of entry to factor. Open the community manager, and scan
close by wi-fi networks, and also you need to see there our faux get right of entry to factor
called “freewifi”
Go in advance and connect with it and assuming that we set the entirety up correctly
you need to have a web connection. Check and spot when you have an
assigned IP cope with from the DHCP pool that we've created before.
In the instance I actually have provided, we've created a DHCP server that can
assign IP addresses to linked devices, and we've created a variety
among 192.168.1.2 to 192.168.1.30 with the command
“variety 192.168.1.2 192.168.1.30”
Under the DHCP configuration. So your sufferers IP cope with need to be within
that variety. As a sufferer, you may log into your Facebook web page and you'll
discover if SSL strip is operating or now no longer.
You can use both Firefox, or Google Chrome, and you'll see that both if
you attempt to kind withinside the browser https://www.facebook .com, it'll extrade the
cope with to www.facebook.com
This way that the SSL strip is operating and in case you study the pinnacle left tab in
the browser, youll note a lock icon.
This is an icon that SSL strip locations there to feature a bit legitimacy and this
prevents the sufferer from turning into too suspicious, due to the fact they see this lock
and robotically assumed it ought to be secure.
So, subsequent move in advance and input an e mail and a password into facebook. You use
use a fictitious username and password such as “testuser” and use the
password “password123”.
It doesn’t count number what username or password you use, as you the factor is now no longer
in an effort to go browsing to facebook, however the truth that we will seize each the
username and password credentials.
Before you click on login, move again over to the attacker gadget and we could monitor
on the ettercap terminal. Now you may move in advance and click on login on facebook,
and in case you study the ettercap terminal, you need to see statistics coming through.

## SSLStrip Results

You must word each the username subsequent to the field “USER” and the
password subsequent to the filed “PASS”.
If you will attempt the instance with an internet banking website, it's miles highly
probably that the username and password isn't going to seem withinside the ettercap
terminal, however it's going to seem withinside the SSL strip logs.
You can attempt to log into bills and you may now no longer see the username and
password withinside the terminal, however SSL strip will seize them and putting them into
a log.
So, move in advance and flow returned over to the attacker pc, and right here you
want to open a brand new terminal and type;
“cat sslstrip.log”
after which press Enter. Now, you must see each username and password.
The person information will seem withinside the logs as “userId=username” and the
password will seem as “auth_passwd=password”
Those are all of the examples that I desired to proportion with you however preserve in mind
that this assault is expandable.
For instance there's a device called “karma” and what this does is whilst a
pc is seeking out a wi-fi community to connect with specially a
wi-fi community this is linked to withinside the past, it sends out probe requests.
Well, we are able to create some thing with a purpose to permit us to simply accept the ones probe
requests after which spoof the wi-fi community that the man or woman is seeking out.
When it responds, theyre going to assume that they discovered that wi-fi community
and their pc goes to routinely connect. There are many things
you could do with this however for now its time to transport directly to the subsequent assault.
You can near the terminal that we use to view the SSL strip log. Then to prevent
ettercap, you'll should press the ctrl and C Keys after which you could near
that terminal.
Then to prevent the SSL strip you could press ctrl + C to shut terminal. To prevent
your faux get admission to point, additionally press ctrl + C withinside the kali window, after which near
the terminal.
All the ones iptables policies that we've created, they'll routinely be
restored returned to the default while you reboot your digital machine.
Please ensure you've got got written authorization earlier than the use of SSLstrip,
inclusive of any versions associated with this device. If you're handiest working towards in your
domestic lab, in a non manufacturing environment, that must motive no trouble to
anyone; nonetheless I might advise you switch off your

