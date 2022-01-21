<span style="background-color:white;color:black;">**RF Hacking Part 1: Reply Attack**</span>
\
I recently researched on Radio Signals and how they are implemented in modern cars and keyfobs algorithms.
This Blogpost is the first of a series of posts that will explain the path I followed, from the basic Reply attack to the most advanced Rolljam, using different hardware and methodologies.
\
I won’t go in depth on certain topics and I will assume that the reader has a general background in basic signals theory and is comfortable with terms like radio frequencies, gain, filters… 
\
**Algorithms**
There are 2 main algorithms implemented in modern cars:
- _Single Code_: a single string of code is sent from the keyfob to the car. This is the exact same code every time the owner of the car clicks the button on the keyfob. This implementation is obviously lacking of security since whoever intercepts, clones and repeats the signal sent from the keyfob is basically able to get in the car./
- Rolling Code: this algorithm is a little more secure than the Single Code, since it's based on a long array of one-time codes. This avoid 
