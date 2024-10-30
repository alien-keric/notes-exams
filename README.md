# cheat sheet and notes

## NMAP
```
nmap -sT 10.10.14.0/24 -T4 -vvv
nmap -sC -sV 10.10.14.123 -T4 -vvv -oN nmap.txt
```

## NFS (2049)
```
Default ports and output
2049/tcp open  nfs     2-3 (RPC #100003

## show all mounts
showmount -e $ip


## mount a NFS share
mount $ip:/vol/share /mnt/nfs

## use nfspy to mount share
- Will get around permission errors
					nfspysh -o server=$ip:/home/vulnix/


## nmap scan on rpcbind and NFS
nmap -sV -p 111 --script=rpcinfo 10.11.1.1-254
nmap -sV -p 111 --script=rpcinfo 10.11.1.1-254
nmap -v -p 111 10.11.1.1-254


## mount
kali@kali:~$ mkdir home
kali@kali:~$ sudo mount -o nolock 10.11.1.72:/home ~/home/
kali@kali:~$ cd home/ && ls
jenny joe45 john marcus ryuu



#Note
Take a look of suid if permission denied
Create new user and change the suid of user to the correct one

sudo sed -i -e 's/1001/1014/g' /etc/passwd
```

## SMB
```
smbclient -L 10.10.14.123

smbclient \\\\10.10.14.123\\users -U admin
```

## wordpress
```
nikto wordpress.com

wpscan --url wordpress --passwords /pass.txt
```

## wifi
```
aircrack-ng test.pcap -w wordlists.txt
```


## vera decrypt
```
Online:https://medium.com/@roshanmsk/decrypting-a-text-file-using-veracrypt-a3bf924638f2
```

## searching for geolcations
```
1. https://www.iplocation.net/ip-lookup
```


## enumeration with gpt
```
Perform a DNS enumeration on www.certifiedhacker.com and find out the name servers used by the domain. (Format: aaN.aaaaaaaa.aaa, aaN.aaaaaaaa.aaa)

Tools:
nslookup -type=ns certifiedhacker.com
dig ns certifiedhacker.com +short

Example of output:
ns1.certifiedhacker.com
ns2.certifiedhacker.com
```

