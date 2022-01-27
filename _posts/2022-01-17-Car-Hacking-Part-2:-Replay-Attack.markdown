# <span style="color:red;font-size:17px;"><ins><b>RF Hacking Part 2: Replay Attack</b></ins></span>

&nbsp;

Before getting into more advanced methodologies, it's always better to understand how the process works. In order to do that, I started hacking simple devices such as radio doorbells, remotes, iot devices and so on. Note that most of these devices, if bought recently, implement Rolling Code algorithms. If you want to find a device that still uses the single code approach, you can find an old/cheap one online.

In my case, I used radio doorbell.

&nbsp;
<p>
              ________
             / ______ \                                <>
             || _  _ ||                                ||
             ||| || |||                                ||
             |||_||_|||               ABC              ||
             || _  _o|| (o)   ------------------>     /  \
             ||| || |||                              |#   |
             |||_||_|||                              /    \
             ||______||                             '-....-'
                                                        U
</p>
&nbsp;

The doorbell has a remote to stick outside the door that, when clicked, sends a signal to the actual doorbell that, once received the signal, playes a sound. Very simple, very cheap.

&nbsp;
<ins style="color:red;">Recording the signal</ins>
As explained in the <a href="https://scare.rocks/2022/01/17/Car-Hacking-Part-1-Intro.html" style="color:red;">Introduction</a>, devices that implement single code are very easy to hack, since we only need to intercept, store and replay the signal.
  I will explain asd
<img src="/img/Car_Hacking_Part_1/receive.png" style="width:80%;height:80%;display:block;margin-left:auto;margin-right:auto;" alt="GNU_Receive Pic">
&nbsp;
<img src="/img/Car_Hacking_Part_1/send.png" style="width:80%;height:80%;display:block;margin-left:auto;margin-right:auto;" alt="GNU_Send Pic">
&nbsp;
