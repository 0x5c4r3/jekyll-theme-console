---
layout:     post
author:     0x5c4r3
type: docs
permalink: Windows_Privesc
---


<span style="font-size: 35px; color:red"><b>Windows Privilege Escalation</b></span>
&nbsp;
<span style="font-size: 25px; color:white"><b>Windows Services</b></span>
Enumerate services:
```shell
sc query
```
OR
```powershell
Get-Service | fl
```
<span style="font-size: 25px; color:red">Unquoted Service Paths</b></span>
execute-assembly C:\Tools\SharpUp\SharpUp\bin\Release\SharpUp.exe audit UnquotedServicePath

List services and their paths (looking for <span style="color: red">Unquoted Service Paths</span>:
```shell
wmic service get name, pathname
```
i.e. For an unquoted service path like C:\Program Files\Vulnerable Services\Service.exe, the OS will look for:
- C:\Program.exe
- C:\Program Files\Vulnerable.exe
- C:\Program Files\Vulnerable Services\Service.exe
&nbsp;
Check permissions on Folders and Files:
```powershell
Get-Acl -Path "C:\Program Files\Vulnerable Services" | fl
```
and check for <span style="color: red">BUILTIN\Users Allow  CreateFiles</span>.
