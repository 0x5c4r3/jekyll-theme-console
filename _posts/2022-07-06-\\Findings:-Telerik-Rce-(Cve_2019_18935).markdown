---
layout:     post
author:     0x5c4r3
image: /img/Car_Hacking_Part_1/twitter_banner.png
---
# <span style="color:red;font-size:17px;"><ins><b>\\\findings: Telerik RCE (CVE-2019-18935)</b></ins></span>

&nbsp;

<ins style="color:red;">Enumeration & Detection</ins>

&nbsp;

I was recently working on a pentest for a really big company, huge scope, quite a lot of different IPs and hosts from all over the world. Focusing on one IP, I was checking the various endpoints of its web servers and while scanning and enumerating the website to have a general map of the structure, I was checking the source code of a page and I noticed some references to Telerik, with an html comment that might have been the version implemented:

&nbsp;

<img src="/img/Telerik_RCE/detection_telerik.png" style="width:80%;height:80%;display:block;margin-left:auto;margin-right:auto;" alt="Burp_Detection">

&nbsp;

The pic clearly showed that _default.aspx_ had something to deal with Telerik, so I checked the HTTP History and I found the actual endopoint:

&nbsp;

<img src="/img/Telerik_RCE/detection2.png" style="width:60%;height:60%;display:block;margin-left:auto;margin-right:auto;" alt="Burp_Detection">

&nbsp;

Ok, at this point I was sure Telerik was actually implemented, but I was not that sure about the version - I could't only rely on an html comment - so I researched online and I found out that you can figure out the version implemented running the following very simple bash script against different endpoints: 

&nbsp;

{% highlight shell lineos %}
curl -skL <HOST> | grep -oE '20[0-9]{2}(\.[0-9]*)+'
{% endhighlight %}

&nbsp;

I ended up running it against 3 different endpoints related to Telerik that reported the same version: v2017.1.228.45.

&nbsp;

<ins style="color:red;">Exploitation</ins>

&nbsp;
  
I was already aware about <a href="https://nvd.nist.gov/vuln/detail/CVE-2019-18935" style="color:red;">CVE-2019-18935</a>, but I have never had the possibility to dig in details and actually use the exploit. 
