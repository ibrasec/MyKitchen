To save nmap result to metasploite database simply do the command

```
msf> db_nmap -v -T4 -PA --version-all --osscan-guess -A -sS -p 1-65535 <target-addres>
```
then to retrieve these infomation from within metasploite use
```
msf> services
```
