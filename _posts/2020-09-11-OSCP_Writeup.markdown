
 <h1>OSCP Writeup - Scarecrow's Experience</h1>

<body>

Eyo kiddies,
yea I did it. I passed the OSCP exam.

For those of you who do not know what the OSCP is, it's the Offensive security Certified Professional, a really fucked up certification that basically leads you to shot yourself in the knee.
It's the N.1 certification for Penetration testers: during this journey, you basically learn all the foundamentals to perform a good penetration test against different structures, platforms, OS... ending with the notorious 24h exam.
But I am not here to describe you what the OSCP is, so if you want, google it ffs.

<h2># INIT</h2>

My journey started back in May 2020, in full Lockdown, nothing to do apart from working, no parties, no meetings.. So I decided to commit suicide and enroll in the PWK course (Penetration testing with Kali Linux, it's the course you need to follow to prepare for the OSCP) and attempting its final exam.
My background was quite good in terms of Computer Science and general Cyber Security, plus I was in HTB since half a year approximately. Indeed, I already knew the majority of the stuff explained in the course. So I've been reading the whole course documentation in 2 weeks and I jumped into the LAB (basically you have 1/2/3 payable months to get a vpn access to a lab to test your skills) and here we have the real shit. 

<h2># THE LAB</h2>

The Lab part is the worst, meaning that it's completly messed up, no guideline, no walkthrough or writeups, a disaster. I was constantly in contact with the Staff Chat to ask some questions about the machines - since I payed for it and I wanna learn as much as I can - and they kept replying to me that they were there to solve technical issues, not students questions. So yea, that was really fucking bad. Luckly I already was into htb so what I have done is I left the official lab and kept studying through htb or sites like that (much much much much better). Now I read that Offensive Security bought VulnHub, I guess they figured out they were providing such rotten lab service.

<h2># FIRST ATTEMPT</h2>

The exam is a 24h long challenge in which the student is spawned into a local network made out of 5 hackable machines: two worth 25pt, two 20pt and one 10pt. Usually, one of the 25pt is a Buffer Overflow. Each machine has a user flag and a root flag to retreive.

So once ready I shot my shot and YEA i failed it. It was early/mid July, the exam started at 10 a.m. and basically finished at 9 p.m. with me figuring out my failure. I had 35 points and you need 70.

Ok, yea sad, but you know, at least now I knew how the exam really was. So focused on next attempt, I kept studying.

<h2># SECOND ATTEMPT</h2>

Early October, I started at 8 a.m. this time with the willing of not throwing away the chance.
I got the Buffer Overflow in almost 20 mins - nice, 25 points.
Then nothing. Man I was lost on the other 25pt machine for so long. So I choosed to leave it and I went on the next ones.
At 4:00 p.m. I got a 20pt, 45pt total, quite good for a mid-afternoon.
At 8:00 p.m. I got the other 20pt, for a total of 65pt. I needed 5 more to pass.

At that point everything is psychological. You need to work on your mind, keeping it awake and aware, 24hrs non-stop are a fucking lot.
I took a nap from 12 p.m. setting the alarm at 3, but of course I did not sleep, too many thoughts.
At 1 a.m. I woke up and kept working.
<br>
<img src="../../../img/IMG_20200920_045700.jpg" width=30% height=auto alt="FLAGS_OSCP">
<br>
I was up to stay awake the whole night to find the last vulnerability. And I got it. At 3:50.
At that point, reached 75pt I was quite sure to have a possibility.

Once you took every single screenshot and copied the needed code and exploits, the remaining stuff is easy. Also the next day, the report is a pain in the ass but it's quite easy, so CARE YOUUR PSYCHOLOGYCAL STATE, that's the key.
<br>
<img src="../../../img/202010161356301000_COVERED.jpg" width="30%" height=auto alt="OSCP_CERTIFICATE">

</body>
