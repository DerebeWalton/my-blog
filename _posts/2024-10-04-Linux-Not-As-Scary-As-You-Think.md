---
layout: post
title:  "Linux: Not as Scary as You Think"
description: Guide for installing Ubuntu on Windows devices
image: /assets/img/setupcomplete.jpg
---
<p class="intro"><span class="dropcap">L</span>inux! Did I scare you? For many, the idea of using, much less installing, any linux distribution sounds both daunting and potentially dangerous. This guide will hopefully ease you in and help you along so you too can enjoy the efficiency that is Ubuntu. </p>

## Why Linux?

Now, you may be thinking, "Why would I even want to install Linux?" There are many reasons. Here are a few:

1. Microsoft is killing Windows 10 on October 14, 2025. Now this does not mean your computer will suddenly stop working, but it does mean it will be vulnerable to potential malware. For many, we would love to upgrade to Windows 11, but our computers simply do not have the ability to run it.

2. Ubuntu and most Linux distros (distributions) are much less bloated and resource heavy than Windows, and even some Apple products. 

3. Most Linux distros are free and open source!

4. It feels very similar to, and even can be customized to act just like, Windows and MacOS.

5. It is sad to let a good computer go to waste, so give new life to an old computer with a safe, secure, and simple operating system.

For those who are afraid of potentially messing up your computer, no need to worry. Linux is safe, and relatively easy to install. And, although you can lose data if you don't back things up (like with any system), you are unlikely to break your computer by replacing the operating system. 
*That being said, I must clarify this now: I am not responsible for any problems, issues, damage, stress, or other negativity that may occur during this process. I am providing my best understanding to help provide both options and joy in Linux.*

---
---


# The Plan

I usually feel more prepared when an outline is provided, so here are the major steps in the installation process we will cover:

1. Getting Ready
2. Booting Up Into Ubuntu
3. Installation Options
4. Personalization
5. Install!
6. Troubleshooting

As issues can depend on your specific computer, feel free to skip to troubleshooting if anything goes wrong. Now, lets get started!

---
---

## Getting Ready

First, you must gather some critical things:
1) A computer with at least 25 GB of space.
2) A USB drive. It is recommended to be least 12 GB big.
Yeah, you don't need much.

If you ever get lost or need additional info, please refer to the [Ubuntu official guide](https://ubuntu.com/tutorials/install-ubuntu-desktop) for more details on Ubuntu and the installation process.

### Back Everything up!
As mentioned above, your data is your responsibility. So, back up your files! These days, you can get quality 512 GB flash drives for under $40, so no excuse if you lose your data.

### Download an ISO
What is an ISO, you ask? That is a file system standard published by the International Organization for Standardization (ISO). Basically, it is a format for things like bootable software.

![Ubuntu Download Page]({{site.url}}/{{site.baseurl}}/assets/img/Ubuntu download page.png)

You should go to the [official website](https://ubuntu.com/download/desktop) and download the ISO there. You can also access past versions on [this page](https://ubuntu.com/download/alternative-downloads)

### Make a Bootable Drive
The next step is using the ISO and making the USB flash drive into a bootable USB drive. To do so, you will need to use a program that does it for you. Canonical, the company behind Ubuntu, recommends [balenaEtcher](https://etcher.balena.io/)

![Figure]({{site.url}}/{{site.baseurl}}/assets/img/balenaEtcher home.png)

## Booting Up Into Ubuntu
Now comes the fun part of actually playing with the bios and using Ubuntu.

### Boot from the USB
Plug the now-bootable USB into the computer. 

Once done, you should look up how to access the boot menu for your computer. For my old Sony Vaio Ultrabook, I had to press the "ASSIST" button. For an old HP Pavilion, it was F12. For the HP ProDesk I got for this post, it was ESC. Many computers use F12, F2, F8, F10, or ESC.

Now that you know what button to press, power on the computer and press that button until you get to the bios and/or boot menu.

![Figure]({{site.url}}/{{site.baseurl}}/assets/img/bios_home.jpg)

Feel free to look around your bios, but I warn that it is usually best to leave things alone unless you know what you are doing. Find the option that sounds similar to "Boot from USB" and select.

![Figure]({{site.url}}/{{site.baseurl}}/assets/img/bios_boot.jpg)

### Install or try Ubuntu
After some loading, you should see a few options, including one that says, "Try or Install Ubuntu." This is the one we want. 

After it loads up, it should look more like an OS that you are used to and allow you to click around. You should go through the options, including connecting to the internet if you would like. 

![Figure]({{site.url}}/{{site.baseurl}}/assets/img/try_ubuntu_web.png)

Once you reach the "Install Ubuntu" or "Try Ubuntu" take your pick. I would recommend trying Ubuntu if you have no experience with it yet. You can explore and look around as though it were installed. In reality, Ubuntu is currently running off of the USB drive. When you are ready, click "Install Ubuntu 24.04.1 LTS" to continue with the installation process.

## Installation Options
These options provide you with some customization as to how your Ubuntu OS will work. This includes having additional programs already installed when the installation completes and having proprietary software available.

### Interactive Installation
For most of us who are not scaling Ubuntu installation, go with the **Interactive Installation**. The other option is more for commercial use or having more than just a few computers.

![Figure]({{site.url}}/{{site.baseurl}}/assets/img/interactive_installation.png)

### Extended Selection
You can choose how much you have pre-installed in this next step. If you just want the basics, go with **Default Selection**. If you would like some additional apps, like some office tools similar to Word and Excel, go with **Extended Selection**. I found the Extended Selection was helpful for me as I didn’t want to go through the hassel of choosing a bunch myself.

![Figure]({{site.url}}/{{site.baseurl}}/assets/img/ubuntu_extended.png)

### Proprietary Software
It is recommended to check both boxes to allow for certain drivers, such as for Nvidia graphics cards, and media formats, such as MP4.

![Figure]({{site.url}}/{{site.baseurl}}/assets/img/ubuntu_proprietary_soft.png)

### Erase or Dual Boot
For many people, the next step would be simple as we choose whether to erase the disk and install Ubuntu (removing whatever OS you previously had, so likely Windows) or manually choose where to install it. Erasing the disk is easiest, but advanced users can have the option to dual-boot to have both Ubuntu and the original OS or manually partition the space. For my purposes so far, I was mostly replacing Windows 7 and Windows 8 machines, so I did not care for keeping Windows.

![Figure]({{site.url}}/{{site.baseurl}}/assets/img/ubuntu_erase_disk.png)

## Personalization
This part simply allows you to customize a few details about your computer

### Create Login Credentials
You get to choose what to name your computer! And a username and password for your local account.

![Figure]({{site.url}}/{{site.baseurl}}/assets/img/ubuntu_create_login.png)

### Choose Time Zone
I hope you know your time zone. Mine was MST.

![Figure]({{site.url}}/{{site.baseurl}}/assets/img/timezones.png)

## Install!
The time has come. Now we install Ubuntu onto the computer!

### Follow the prompts
Go through the options and choose what you prefer for each of the prompts. Once you review your choices, you can hit the "Install" button. 

![Figure]({{site.url}}/{{site.baseurl}}/assets/img/review_and_install.png)

Be aware it might take a while for Ubuntu to install, especially if you have a Hard Disk Drive (HDD).

### You installed Linux!

![Figure]({{site.url}}/{{site.baseurl}}/assets/img/installed.png)

Now that Ubuntu is officially installed, make sure to complete any updates that may be needed. And, of course, make it your own! One of the first things I did was change the background to a picture of my wife and me. The other was move the app dock from the side to the bottom of the screen. I am still not sure if I like it on the bottom or side more, though.


---
---

## Troubleshooting
*Did you try turning it off and back on again?*

### Computers are complicated
As with any complex system, things can go wrong. Computers are both complex and varied, so you may see an issue that I never heard of. As I said towards the beginning, it is best to check the [Ubuntu official guide](https://ubuntu.com/tutorials/install-ubuntu-desktop) for additional details, and that includes errors, bugs, and general troubleshooting. If the solution is not there, then feel free to look up your specific issue online. With some searching and troubleshooting myself, I found workarounds for both issues I faced in my initial installations.

### Issues I faced
Speaking of my issues, here is what I experienced and had to figure out:
1. My very first installation of Ubuntu was on a old Sony Vaio laptop running Windows 8.1 gifted to me by my father-in-law. It became quite an adventure when the option to erase the old OS was never an option. The installation skipped that step and directly went to have me manually partition drives. I had no idea what the drives meant and, even with some research, I was not able to change any from that menu or even from within Windows. Eventually, what worked was I partitioned space from within the "Try Ubuntu" system. Now, that computer is my daily driver. I even am using it to write this post.

2. Now the second was a doozy. Apparently, certain HP Pavilion laptops have issues booting from USB. So, I had to get a DVD that would fit an Ubuntu ISO on it and use that to boot and install. For your reference, it took a long time.

### Issues Canonical mentioned
In the main guide provided by Ubuntu, they also have a few issues mentioned. For your convenience, here are the main ones I noticed:

1. Intel RST (Rapid Storage Technology) is not supported by Ubuntu, so must be disabled.

2. TPM-backed full disk encryption is a new, highly experimental feature. So it's probably best to wait and not mess with it just yet.

3. If you select LVM or ZFS based encryption, you will have to make an encryption key. Don't lose your encryption key. That would be sad.

4. Windows Bitlocker should be disabled if you are dual-booting your computer.

## Now What?
Install Ubuntu yourself if you have not already! You have the steps and, hopefully, the confidence. I believe in you!

You can also try other Linux distros, like Mint or Pop!_OS. Find the best fit for you, as there are plenty out there for your specific needs.

Tell me what you enjoyed, what went wrong, or maybe your favorite operating system. If it is Windows XP, then extra respect! Just, please do not connect any Windows XP device to the internet. Thats like jumping in a lake of pirhanas with a steak.