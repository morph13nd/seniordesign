## Blog Four

![Image](https://themaverick.github.io/seniordesign/gifs/morph.gif)

### Windows and Backup images... let's face the reality.
In this blog I will discuss how I prefer to backup windows and the most successful method I've had in terms of backing up windows in a full disk image without destroying the image itself and having a very high success rate (100%) so far, compared to other imaging softwares that might cost a lot of money. Windows used to have a system image backup utility in Windows 7. 

![Image](win7bu.png)

### Out with the old, in with the new.
This is what it usually looked like in Windows 7 when you're trying to create a system image backup. In my experience the feature has been lacking and I have moved on to third party softwares and I prefer the macrium reflect software because it is free and it is constantly updated , also fantastic for home and personal use . They also work on releasing a windows RM feature boot into a drive and perform a restore.  Windows has used the volume shadow copy service VSS service to continually use our system restore functionality and for the backup and restore functionality, and it is concerning to continue using something since Windows 7 and in my experience in using the functionality to backup images via the windows backup and restore function, it has failed about 50% of the time after an approximate 2 hour image creation time. That's a lot of overhead. Macrium reflect takes an hour or less, depending on drive type and drive space.

![Image](https://themaverick.github.io/seniordesign/media/explorer_HNFPbqbgcB.png)

### The technical item list
```
1. Download and install Macrium Reflect.
2. Backup desired system configuration to create a golden image
3. Create bootable media drive
4. Attempt to restore your golden image!
```

### Macrium Reflect setup

<a href="https://www.macrium.com/reflectfree" target="_blank" rel="noopener noreferrer">Click here to download Macrium Reflect.</a> 

In my experience Macrium Reflect is pretty great, it is free software and you do not have to register for anything other than the first time by providing them an email address. You can use a burner email address if you'd like to that's your choice, you will then get a download link too a client downloader software to officially pull the latest version of macrium reflect from their servers. After you download it that, you will launch the installer and you walk through the installation wizard. 

![Image](https://themaverick.github.io/seniordesign/media/reflect-free-screen.png)

### Backup desired system configuration to create a golden image

![Image](https://themaverick.github.io/seniordesign/media/gold.png)

Now in my experience, and in any general information technology experience, there should always be some sort of backup solution for any kind of system whether that is development or production. There should also be routine backups with either full incremental or schedules involved. Personally, for me, I like to create a full back up every six months since I do not keep any important information on my local hard drive and I am strictly running software and critical files are stored otherwise. I am also very big on performance so it also depends on what kind of system you want. If you want to have a system that is very fast and lightweight and only has software that you want to use with specific tweaks , set your system up as such from scratch and use that as your Golden image so that way when you have to restore back to your system either for performance improvements as systems get laggy overtime , or just because you need a recovery and something crashed and the system is unrecoverable, this is definitely the way to go. Of course, everybody has their own system usages, so it is best for you to decide your own desired system configuration and call it your Golden image. I have heard this term used within the industry and I like it because it reminds me of Charlie and the Chocolate Factory. You can take a backup of a system while it is running live, which is a glorious bonus to this process.

![Image](https://themaverick.github.io/seniordesign/media/firefox_OOiWgXZnV3.png)

### Create a bootable backup media for Macrium Reflect

You need to create rescue medium so we can boot into this and restore a system in the event that is has crashed and you cannot access the Desktop. The boot media lets you access everything on the drive through a Windows 10 minimal UI desktop experience. Why is this better? This way the computer is accessed while the hard disk drive is offline and the original operating system's issues will not interfere with the bootable rescue Macrium Reflect medium. I like to check off the UEFI option since I typically work with newer systems, legacy systems should work typically as well and UEFI is a BIOS standard.

![Image](https://themaverick.github.io/seniordesign/media/backup.png)

### Attempt to restore the original image

Now it is the time to restore the original image of the computer system by booting into your drive and selecting your USB flash drive that holds the macrium rescue media. After booting in, a Windows desktop environment would load. This environment is accessible like a Windows 10 UI desktop and has Desktop icons. 

![Image](https://themaverick.github.io/seniordesign/media/restore.png)

Select the restore image option to restore your golden image backup. The golden image backup must be stored on an external drive with enough storage, and is not to be stored on the target operating system we are trying to image. Doing so is dangerous and will be counterproductive to the whole process. There is the option to verify the process, which is recommended if time allows. It can add another 30 minutes maximum to the process of course depending on your hardware, performance, and storage used.


![Image](https://themaverick.github.io/seniordesign/media/drag.png)

### Complete

After restoring the image, you can reboot the system and see that your computer is restored to as if nothing had ever happened. I find this is great for working against some very odd hardware failures and to rule out the operating system is not the issue if you have a backup prior to having an issue that begins occuring.