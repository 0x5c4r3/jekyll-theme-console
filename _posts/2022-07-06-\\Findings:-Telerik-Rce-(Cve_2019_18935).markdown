---
layout:     post
author:     0x5c4r3
image: /img/Car_Hacking_Part_1/twitter_banner.png
---
# <span style="color:red;font-size:17px;"><ins><b>\\\findings: Telerik RCE (CVE-2019-18935)</b></ins></span>

&nbsp;

<ins style="color:red;">Enumeration & Detection</ins>

&nbsp;

I was recently working on a pentest for a really big company, huge scope, quite a lot of different IPs and hosts from all over the world. Focusing on one IP, I was checking the various endpoints of its web servers and while scanning and enumerating the website to have a general map of the structure, I noticed that one of the passive extentions that I have on Burp found an outdated Telerik version implemented:

&nbsp;

<img src="/img/Telerik_RCE/detection_telerik.png" style="width:80%;height:80%;display:block;margin-left:auto;margin-right:auto;" alt="Burp_Detection">

&nbsp;

The pic clearly show that the _default.aspx_ endpoint had something to deal with Telerik, so I went checking the HTTP History and I found the actual endopoint:

&nbsp;

<img src="/img/Telerik_RCE/detection2.png" style="width:60%;height:60%;display:block;margin-left:auto;margin-right:auto;" alt="Burp_Detection">

&nbsp;

&nbsp;

<ins style="color:red;">Exploitation</ins>

