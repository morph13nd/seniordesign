## Blog Five

![Image](https://themaverick.github.io/seniordesign/gifs/emmorph.gif)

### Hivestorm sounds very familiar... University Cyber Patriot?
After working in a team with the collegiate cyber defense competition, it was time to sharpen our skills further and expand our skills with the Hivestorm competition which helps grow our skills as a team and individual members in specifically hardening infrastructure at a local level. this includes your user permissions, your user security policies and computer security policies. To remain compliant with the competition I will keep everything at a very high level but explained well enough to not be considered releasing answers for the competition and maintain integrity. 

### The technical item list
```
Password changes
Updating software that is not the operating system
Updating the operating system 
```
![Image](https://themaverick.github.io/seniordesign/media/firefox_E4900NG1sF.png))

### Password changes


![Image](https://themaverick.github.io/seniordesign/media/explorer_HNFPbqbgcB.png)

Password changes are very important because if you do not change passwords the hashes that are left behind from passwords that are old can be cracked through vulnerabilities such as pass the hash and local security authority vulnerabilities that include mimikatz based attacks. Therefore within the hives from competition, one of the requirements is that we do change our passwords and it is not all the time easy to change passwords on many accounts , which we have a script written ready to go but that won't be published here. Instead, we change our passwords manually and log everything. Passwords are everything and multifactor authentication is unfortunately beyond the scope of the competition, albeit, an important concept.

### Updating software that is not the operating system

![Image](https://themaverick.github.io/seniordesign/media/firefox_hHBzxQNyom.png)

One underlooked facet of information security is the different kinds of components in computers that are never managed essentially and are left in the developers hands, which are third party software an application that do not belong to the operating system. This is 1 component in hive storm that is analyzed heavily and can lead thoards assisting a team. Since these updates are managed strictly by the application vendor more often than not, and not by Microsoft, For Windows based operating systems at least, it is up to the user to be responsible for these low hanging fruit and to ensure that there software remains up-to-date . Most people do not pay attention to software updates until they notice something has broken on their end and that is too late. 


### Updating the actual operating system

![Image](https://themaverick.github.io/seniordesign/media/firefox_jKhP8bMPNu.png)

Surprisingly, those windows updates that destroy your computer every time, are actually still very important for your computer to have. Those operating system updates are what keep the gears that operate all of the applications that run on top of it in top shape and Patch major security vulnerabilities that hackers and script kiddies can use to exploit the operating system. Operating system patches are more relevant than ever and must be applied more frequently and as frequently as they are released in a production environment this may usually require some sort of testing period unfortunately, in home environments, there is no such thing as testing without a home lab. I highly encourage people who are windows enthusiasts and NIX based enthusiasts to have a home lab to test their updates prior to having them released in their production environment which may or may not be someones gaming PC . In hive storm the competition, updates are absolutely low hanging fruits and a no brainer and should always be performed for local hardening. 