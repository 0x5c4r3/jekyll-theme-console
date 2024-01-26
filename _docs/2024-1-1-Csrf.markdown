---
layout:     post
author:     0x5c4r3
type: docs
permalink: CSRF
---


<span style="font-size: 35px; color:red"><b>Cross-Site Request Forgery</b></span>

CSRF vulnerabilities may arise when applications rely solely on HTTP cookies to identify the user that has issued a particular request. Because browsers automatically add cookies to requests regardless of the request's origin, it may be possible for an attacker to create a malicious web site that forges a cross-domain request to the vulnerable application.

<span style="font-size: 25px; color:white"><b>Test CSRF with Burp</b></span>
- Right click on the POST request you want to double check > Generate CSRF PoC.
- Alter the input on the modified field and click Copy HTML.
- Open a text editor and paste the copied html. Save it and open it with the same browser.
- If the attack has been successful and the account information has been successfully changed.
