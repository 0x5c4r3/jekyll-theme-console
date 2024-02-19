---
layout:     post
author:     0x5c4r3
type: docs
permalink: ADSearch
---

<span style="font-size: 35px; color:red"><b>ADSearch</b></span>
AD Enumeration with custom Lightweight Directory Access Protocol (LDAP) searches.

i.e. From CobaltStrike, search for all objects whose category is "user":
```powershell
execute-assembly C:\Tools\ADSearch\ADSearch\bin\Release\ADSearch.exe --search "objectCategory=user"
```
