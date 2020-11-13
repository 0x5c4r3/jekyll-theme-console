---
title: /
layout: default
permalink: /
---
<br>
<div style="color:#e78d32;"> # Hi_I_Am_Scarecrow </div>
<body onload="typeWriter();">
<script>
var i = 0;
var txt = 'Yeah so, long story short, I was bored of playing games and hacking casual machines, so I came out with this idea: why not wasting time and money on creating a format to share cyber security knowledge and create a web of interested hackers - I know that you are script kiddies, don't lie to me - to share knowledge with?
Since I just finished my University carreer and I think I GOT SKILLZ, my main goal's to create a different type of content, not the usual Teacher-Students approach, but a way of "learning togheter", aka I keep doing stuff and you babies keep discovering new things along with me. I'm still working on the idea, I know, there's plenty of work to do but HEY, COVID19 had locked us home again so..';
var speed = 80;

function typeWriter() {
  if (i < txt.length) {
    document.getElementById("demo").innerHTML += txt.charAt(i);
    i++;
    setTimeout(typeWriter, speed);
  }
}
</script>
</body>
