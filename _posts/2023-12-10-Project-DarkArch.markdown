---
layout:     post
author:     0x5c4r3
image: /img/darkArch/windows3.png
---
# <span style="color:red;font-size:17px;"><ins><b>Project darkArch</b></ins></span>

&nbsp;
So I recently changed workplace as I received a nice offer from a big company, so with the moving and all the burocratic stuff I ended up with 2 weeks of boring nothingness waiting to start with the new job, therefore the nerd in me saw the opportunity to resume a project I started some years ago: an Arch testing machine using i3 that looks badass and works like magic.
I had an old Macbook Pro (late 2012) that I wasn't really using anymore, so I just wiped that and started building like crazy because why not and I gotta say I'm quite happy with the result, looks sick and works fine. 

TLTR: Yeh I got it working, it looks sick, references for the tools I installed down below.

&nbsp;
Here's a quick view:
&nbsp;
<img src="/img/darkArch/desktop.png" style="width:50%;height:50%;display:block;margin-left:auto;margin-right:auto;" alt="Desktop_Pic">
&nbsp;

<ins style="color:red;">Configuration</ins>
I started the project flashing the usual <a href="https://archlinux.org/download/" style="color:red;">Arch Kernel</a> on live USB to then proceed with the minimal installation, connecting the laptop to an ethernet cable (with like 17 dongles because it's a Mac with 2 VERY USEFUL THUNDERBOLT PORTS and an SD PORT but no Ethernet because Tim was drunk when he chose the design) and proceeding with the installation on local disk. Now, since the Apple sensed that I had plenty of time, it immediately started fucking around with the Network drivers so that once booted in the actual installed Arch, no interface apart from 127.0.0.1 was detected. I wasted some time figuring out what the problem was and it turned out the driver I needed was the <a href="https://wiki.archlinux.org/title/broadcom_wireless" style="color:red;">Broadcom-wl</a>, as b43 and brcm80211 were not working because otherwise it would have been to easy.
&nbsp;
So with that done I had the minimal installation working and connected to the internet, so I started having fun trying different configurations and I ended up with using <a href="https://wiki.archlinux.org/title/xorg" style="color:red;">Xorg</a>, <a href="https://wiki.archlinux.org/title/LightDM" style="color:red;">LightDM</a> and <a href="https://i3wm.org/" style="color:red;">i3</a>, because who wants a mouse nowadays. I configured it to have some gaps because it looks cool and I installed the main tools to properly test (Burp, nmap and so on...), creating keybinds to open the tools just using the keyboard i.e. Burp is CTRL+B, pretty easy to remember.
&nbsp;

