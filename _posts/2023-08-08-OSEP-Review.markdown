---
layout:     post
author:     0x5c4r3
image: /img/Car_Hacking_Part_1/twitter_banner.png
---
# <span style="color:red;font-size:17px;"><ins><b>OSEP Review</b></ins></span>

&nbsp;

Since my knowledge on red teaming was relatively zero - apart from a couple machines on HTB, I decided to get into ADs from 0 to 100 subscribing to <a href="https://www.offsec.com/courses/pen-300/" style="color:red;">Evasion Techniques and Breaching Defenses (PEN-300)</a>, which is the course ending up with the OSEP exam.

&nbsp;

Here's what it's been for me.
&nbsp;

<p>                  
   ,   ,                        
  /////|                        .----.
 ///// |            .---------. | == |
|~~~|  |            |.-"""""-.| |----|
|===|  |  ------->  ||<span style="color:red;">$</span>        || | == | -------> EXAM
|j  |  |            |'-.....-'| |::::|
| g |  |            `"")---(""` |___.|
|  s| /            /:::::::::::\    
|===|/            /:::=======:::\ \"\
'---'               

</p>

<ins style="color:red;">Preparation</ins>
I subscribed to the LEARN ONE, which basically gives you access to the labs and documentation for a whole year. It costs more, but I believe it's the best type of subscription for someone that works in cybersec 9-to-5 and would like to keep having a normal life (I'm talking to you mate, get some friends, go swimming I don't know...). I started in December and I was basically done with the theory mid May. Ngl, I did do some of the exercises of the course, but most of the time I was just following step-by-step what the documentation explained, doing exactly what was described and trying to understand how everything worked. I used <a href="https://obsidian.md/" style="color:red;">Obsidian</a> to take notes instead of CherryTree and I must say I kinda liked it, very handy and good looking.
The notes taking is really crucial, the course fully explains how to build several C# exploits, but often the only necessary part is the final script (this is a very important tip on how to take notes: since there is a lot of theory to go through, make sure to highlight the final/best scripts to then reuse those in other situations! Theory will describe every exploit from the simple ones to the more complicated - if you have the possibility, always use the sophisticated ones first, as they have more chances of working and not being detected by AVs).
&nbsp;

<ins style="color:red;">Challenges</ins>
The course comes with 6 very well done challenges which, in my opinion, are more then enough to get prepared for the exam. Each single challenge covers different course topics to a good extent.
I just did those for a couple times each, deeply understood how each exploit worked - clearly using the exploits that have been explained during the course.
Also: exploiting ADs, there are usually 2 ways of hacking something, remotely (from Kali) and Locally (from the pwned machine). It's fundamental to understand and be able to do both as - during both the exam and the challenges - it might happen that one of the two ways is not viable because of configurations/AVs/firewalls...


