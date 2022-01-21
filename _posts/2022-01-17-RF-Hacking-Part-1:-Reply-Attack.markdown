# <span style="color:red;"><ins><b>RF Hacking Part 1: Reply Attack</b></ins></span>
&nbsp;
I recently researched on Radio Signals and how they are implemented in modern cars and keyfobs algorithms.
This Blogpost is the first of a series of posts that will explain the path I followed, from the basic Reply attack to the most advanced Rolljam, using different hardware and methodologies.
&nbsp;
I won’t go in depth on certain topics and I will assume that the reader has a general background in basic signals theory and is comfortable with terms like radio frequencies, gain, filters… 
&nbsp;
## <ins><b>Algorithms</b></ins>
There are 2 main algorithms implemented in modern cars:
- *Single Code*: a single string of code is sent from the keyfob to the car. This is the exact same code every time the owner of the car clicks the button on the keyfob. This implementation is obviously lacking of security since whoever intercepts, clones and repeats the signal sent from the keyfob is basically able to get in the car.
<p>                  
 __                            ______
/o \_____        ABC          /|_||_\`.__
\__/-="="` --------------->  (   _    _ _\
                             =`-(_)--(_)-' 
 
</p>
- *Rolling Code*: this algorithm is a little more secure than the Single Code, since it's based on an iteration through a long array of one-time codes. This avoids a single code - that has been already used - to be used again, protecting the car from simple reply attacks.
<p>
                  <del>ABC</del>
           --------------->
                  <del>DEF</del>
 __        --------------->    ______
/o \_____         GHI         /|_||_\`.__
\__/-="="` --------------->  (   _    _ _\
                             =`-(_)--(_)-' 
 
</p>
