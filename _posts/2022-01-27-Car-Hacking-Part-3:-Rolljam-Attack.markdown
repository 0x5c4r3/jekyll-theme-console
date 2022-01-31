# <span style="color:red;font-size:17px;"><ins><b>RF Hacking Part 3: Rolljam Attack</b></ins></span>

&nbsp;

And now the fun part. As explained in the <a href="https://scare.rocks/2022/01/14/Car-Hacking-Part-1-Intro.html" style="color:red;">Intro</a>, rolling code algorithms implement an array of ordered single-use codes, which expire after being used once. Also, the list works in a way that if we are at a certain level - let's say we are at code at position 123 in the list -, all the other codes that precede that one are considered already expired and not usable. This means that if we click the keyfob 10 times away from the car (so that the car does not receive anything) and we intercept all these 10 signals, the only code that will be usable to open the car is the 10th (the last signal that the keyfob sent).    
This method is safe against replay attacks, but there is still a way to bypass it, using a bit of social engineerig and technical skills.

&nbsp;

<ins style="color:red;">Attack Approach - Theory</ins>

&nbsp;

In order to achieve the goal of opening the car remotely, we need a little bit of social engineering. I'll try to explain the approach using the next ascii pictures. Let's say the owner of the car is represented by the key, while we are the skull (obviously). The owner needs to hurry to a dentist appointment, so he'll open the car remotely, as he usually does. We'll intercept the signal sent from the keyfob, stop it and store it, so that the car do not receive it.
<p>                  
      __                              .-.                          ______
     /o \_____         1             (0.0)                        /|_||_\`.__
     \__/-="="` --------------->   '=.|m|.='                     (   _    _ _\
                                   .='`"``=.                     =`-(_)--(_)-' 
 
</p>

The owner, who obviously is a muggle and does not know the dark magic we are using, will think that the car did not pick up the signal he just sent, so he'll press the keyfob again. This time we will intercept the second signal he sent, store it and immediately send the first one, so that he'll think that this time, his pressing the keyfob worked.


<p>                  
      __                              .-.                          ______
     /o \_____         2             (0.0)           1            /|_||_\`.__
     \__/-="="` --------------->   '=.|m|.='  --------------->   (   _    _ _\
                                   .='`"``=.                     =`-(_)--(_)-' 
 
</p>

This way we still have the second signal he just sent and with that, we'll be able to remotely open the car once the owner will have left.

<p>                  
      __                              .-.                          ______
     /o \_____                       (0.0)           2            /|_||_\`.__
     \__/-="="`                    '=.|m|.='  --------------->   (   _    _ _\
                                   .='`"``=.                     =`-(_)--(_)-' 
 
</p>

&nbsp;

<ins style="color:red;">Attack Approach - Practice</ins>

&nbsp;

In order to perform such attack, we need to introduction to <b>jamming</b>: jamming is basically sending a very strong signal, close to the one we are interested in, so that all the devices listening for that frequency (i.e. a car) won't be able to receive the signal.

&nbsp;

<img src="/img/Car_Hacking_Part_3/jamming.png" style="width:50%;height:50%;display:block;margin-left:auto;margin-right:auto;" alt="jamming Pic">

&nbsp;

<img src="/img/Car_Hacking_Part_1/receive.png" style="width:80%;height:80%;display:block;margin-left:auto;margin-right:auto;" alt="GNU_Receive Pic">
  
&nbsp;

<img src="/img/Car_Hacking_Part_1/send.png" style="width:80%;height:80%;display:block;margin-left:auto;margin-right:auto;" alt="GNU_Send Pic">
  
&nbsp;
