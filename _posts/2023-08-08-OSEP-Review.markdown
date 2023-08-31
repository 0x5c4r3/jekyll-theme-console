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

<ins style="color:red;">Preparation</ins>
I subscribed to the LEARN ONE, which basically gives you access to the labs and documentation for a whole year. It costs more, but I believe it's the best type of subscription for someone that works in cybersec 9-to-5 and would like to keep having a normal life (I'm talking to you mate, get some friends, go swimming I don't know...). I started in December and I was basically done with the theory mid May. Ngl, I did do some of the exercises of the course, but most of the time I was just following step-by-step what the documentation explained, doing exactly what was described and trying to understand how everything worked. I used <a href="https://obsidian.md/" style="color:red;">Obsidian</a> to take notes instead of CherryTree and I must say I kinda liked it, very handy and good looking.
The notes taking is really crucial, the course fully explains how to build several C# exploits, but often the only necessary part is the final script (this is a very important tip on how to take notes: since there is a lot of theory to go through, make sure to highlight the final/best scripts to then reuse those in other situations! Theory will describe every exploit from the simple ones to the more complicated - if you have the possibility, always use the sophisticated ones first, as they have more chances of working and not being detected by AVs).
&nbsp;








> - *Single Code*: a single string of code is sent from the keyfob to the car. This is the exact same code every time the owner of the car clicks the button on the keyfob. This implementation is obviously lacking of security since whoever intercepts, clones and repeats the signal sent from the keyfob is basically able to open the car.
<p>                  
      __                            ______
     /o \_____        ABC          /|_||_\`.__
     \__/-="="` --------------->  (   _    _ _\
                                  =`-(_)--(_)-' 
 
</p>
> - *Rolling Code*: this algorithm is a little more secure than the Single Code, since it's based on an iteration through a long array of single-use codes. This avoids a string of code to be used twice or more times, protecting the car from simple replay attacks.
<p>
                      <del> ABC </del>
                --------------->
                      <del> DEF </del>
      __        --------------->    ______
     /o \_____         GHI         /|_||_\`.__
     \__/-="="` --------------->  (   _    _ _\
                                  =`-(_)--(_)-' 
 
</p>

<ins style="color:red;">Tools Used</ins>
There are many interesting tools, both hardware and software, that can be used for such purpose. I tried the majority of them, to have a better understanding of which is the best.

<b>Hardware:<b>
> - *Yard Stick One*: Cheapest and quite versatile half-duplex radio dongle able to receive or transmit signals below 1GHz. Perfect to jam the signal (we'll talk later about it), honestly I did not really like the interface, but it did its job.

> - *HackRF*: the most famous SDR on the market, half-duplex, range from 1MHz to 6GHz (quite impressive tbh). Different ways for operating it. Not sure what to say about this one, it's the standard.

> - *BladeRF*: expensive, but probably the best interface around. Full-duplex, 2 RX and 2 TX Antennas with 2x2 MIMO, 47MHz to 6GHz... I mean, it's definitely my favourite toy.

<b>Software:<b>
> - *GNU Radio*: block-based tool used to play with radio signals, not easy at first impact, not really something a hacker would put hands on without knowing signals theory. With time, it became my best friend.
      
> - *CLIs*: Each hardware interface has it's own CLI, unfortunately quite messy and not always working. The HackRF one works fine, the BladeRF one is kinda messy, a little too much, mostly when dealing with full-duplex stuff, sending and receiving simultaneously.
      
> - *Python Libraries*: Really handy, I liked it. I only used the HackRF one and works fine, I imagine the one from Nuand for the BladeRF might have the same issues as the CLI.
      
> - *GQRX and others*: there are several other tools such as GQRX or URH (Universal Radio Hacker) that allows you to analyse the radio signals. These are great to understand what is going on at a low level, printing the actual signal and trying to dunp the data transmitted. As you can imagine, it's quite tricky to find out the modulation and the structure of the data the signal is sending, but still it is quite interesting to check it out.
      
&nbsp;

<ins style="color:red;">Analysing the Signal</ins>
Let's now try to plot the signal that a keyfob is sending using GQRX and a BladeRF:
      
&nbsp;
      
<img src="/img/Car_Hacking_Part_1/Gif_Signal.gif" style="width:80%;height:80%;display:block;margin-left:auto;margin-right:auto;" alt="Signal_Plotter Pic">
      
&nbsp;
 
As we can see from the figure above, the interface is receiving the signal and printing it around 433.92MHz, since the keyfob works at that frequency (there always will be a some offset/noise when receiving the signal, so it won't be at exactly 433.92MHz, but close enough). We can clearly see the pick  every time I click the button on the keyfob.
This tool allows us to see the frequency of the signal, but let's get deeper and let's use URH to actually check the data the signal carries:
      
&nbsp;
      
<img src="/img/Car_Hacking_Part_1/urh_dump.png" style="width:80%;height:80%;display:block;margin-left:auto;margin-right:auto;" alt="Data_Plotter Pic">
      
&nbsp;
 
In this case, URH prints the actual waveform of the signal, trying to automatically detect the modulation and other parameters used and dumping the relative data transmitted.
      
With this basic understanding, we can now pass onto analysing the various attack against these mechanisms, starting from the easiest <a href="https://scare.rocks/2022/01/17/Car-Hacking-Part-2-Replay-Attack.html" style="color:red;">Replay Attack</a>.

