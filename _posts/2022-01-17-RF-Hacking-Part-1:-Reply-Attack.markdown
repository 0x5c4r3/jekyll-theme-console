# <span style="color:red;font-size:17px;"><ins><b>RF Hacking Part 1: Reply Attack</b></ins></span>

&nbsp;

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
<div style="  padding-left: 15px;padding-right: 15px;">In this blogpost I'll explain the basics of car hacking and how to hack a car implementing a *Single Code Algorithm*. If you're interested in bypassing *Rolling Code Algorithms*, check <a href="https://scare.rocks/2022/01/27/RF-Hacking-Part-2-Rolljam-Attack.html">Rf Hacking Part 2: Rolljam Attack</a>.</div>
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 

## <ins style="color:red;"><b>Intro</b></ins>
I recently researched on Radio Signals and how they are implemented in modern cars and keyfobs algorithms.
This Blogpost is the first of a series of posts that will explain the path I followed, from the basic Reply attack to the most advanced Rolljam, using different hardware and methodologies.

&nbsp;

I won’t go in depth on certain topics and I will assume that the reader has a general background in basic signals theory and is comfortable with terms like radio frequencies, gain, filters… 

## <ins style="color:red;"><b>Algorithms and Frequencies</b></ins>
Car Opening mechanisms (keyfobs, if you want) work at default frequencies: 315MHz, 433.92MHz or 868MHz. This allow us to easily find out the exact frequency of the keyfob operates at and - in this case - reply it.
Also, if we exclude the algorithms implementing both Radio Signals and Bluetooth, there are 2 main algorithms implemented in modern cars:
&nbsp;

> - *Single Code*: a single string of code is sent from the keyfob to the car. This is the exact same code every time the owner of the car clicks the button on the keyfob. This implementation is obviously lacking of security since whoever intercepts, clones and repeats the signal sent from the keyfob is basically able to get in the car.
<p>                  
      __                            ______
     /o \_____        ABC          /|_||_\`.__
     \__/-="="` --------------->  (   _    _ _\
                                  =`-(_)--(_)-' 
 
</p>
> - *Rolling Code*: this algorithm is a little more secure than the Single Code, since it's based on an iteration through a long array of one-time codes. This avoids a single code - that has been already used - to be used again, protecting the car from simple reply attacks.
<p>
                       <del>ABC</del>
                --------------->
                       <del>DEF</del>
      __        --------------->    ______
     /o \_____         GHI         /|_||_\`.__
     \__/-="="` --------------->  (   _    _ _\
                                  =`-(_)--(_)-' 
 
</p>

## <ins style="color:red;"><b>Tools Used</b></ins>
There are many interesting tools, both hardware and software, that can be used for such purpose. I tried the majority of them, to have a better understanding of which is the best.

<b>Hardware:<b>
> - *Yard Stick One*: Cheapest and quite versatile half-duplex radio dongle able to receive or transmit signals below 1GHz. Perfect to jam the signal (we'll talk later about it), honestly I did not really like the interface, but it did its job.

> - *HackRF*: the most famous SDR on the market, half-duplex, range from 1MHz to 6GHz (quite impressive tbh). Different ways for operating it. Not sure what to say about this one, it's the standard.

> - *BladeRF*: expensive, but probably the best interface around. Full-duplex, 2 RX and 2 TX Antennas with 2x2 MIMO, 47MHz to 6GHz... I mean, it's definitely my favourite toy.

<b>Software:<b>
> - *GNU Radio*: block-based tool used to play with radio signals, not easy at first impact, not really something a hacker would put hands on without knowing signals theory. With time, it became my best friend.
      
> - *CLIs: Each hardware interface has it's own CLI, unfortunately quite messy and not always working. The HackRF one works fine, the BladeRF one is kinda messy, a little too much, mostly when dealing with full-duplex stuff, sending and receiving simultaneously.
      
> - *Python Libraries*: Really handy, I liked it. I only used the HackRF one and works fine, I imagine the one from Nuand for the BladeRF might have the same issues as the CLI.


