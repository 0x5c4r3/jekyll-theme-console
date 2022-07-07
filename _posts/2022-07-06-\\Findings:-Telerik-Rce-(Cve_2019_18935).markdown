---
layout:     post
author:     0x5c4r3
image: /img/Car_Hacking_Part_1/twitter_banner.png
---
# <span style="color:red;font-size:17px;"><ins><b>\\\findings: Telerik RCE (CVE-2019-18935)</b></ins></span>

&nbsp;

<ins style="color:red;">Enumeration & Detection</ins>

&nbsp;

I was recently working on a pentest for a really big company, huge scope, quite a lot of different IPs and hosts from all over the world. Focusing on one IP, I was checking the various endpoints of its web servers and while scanning and enumerating the website to have a general map of the structure, I was checking the source code of a page and I noticed some references to Telerik, a famous collection of UI tools for web applications. The webpage also contained an html comment that might have been the version implemented:

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

<ins style="color:red;">CVE-2019-18935 - Quick Theory</ins>

&nbsp;
  
I was already aware about <a href="https://nvd.nist.gov/vuln/detail/CVE-2019-18935" style="color:red;">CVE-2019-18935</a>, but I didn't have the possibility to dig in details.<br/>
The vulnerability is based on 2 parts: an Unrestricted File Upload and an Insecure Deserialization.

&nbsp;

  _RadAsyncUpload_, a file handler that allows asynchronous encrypted file uploads. Until v2017.2.621, the encryption mechanism implemented was not secure, allowing an attacker to use a hard-coded key to craft a file upload request to _/Telerik.Web.Ui.WebResource.axd?type=rau_ with a custom encrypted rauPostData POST parameter. Changing the _TempTargetFolder_, an attacker is able to save the uploaded file to any directory the web server has write acess to.
 
&nbsp;
  
 kug 
  
&nbsp;

<ins style="color:red;">Exploitation</ins>

&nbsp;
