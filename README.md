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

# smb,http,ssh cracking
```
hydra -L usernames.txt -P passwords.txt $ip smb -V -f
hydra -L ./webapp.txt -P ./webapp.txt $ip http-get /admin
hydra -v -V -u -L users.txt -P passwords.txt -t 1 -u $ip ssh
```

## Lab2 answers
```
# Task Summary

### 1. Crack NTLM Password Hashes for User James
- **Location**: Documents folder of the Parrot Security console machine
- **Question**: What is the password of user James?
- **Answer**: `qwerty` - (Correct Attempt)

### 2. Crack NTLM Password Hashes for User Jones
- **Location**: Documents folder of the Parrot Security console machine
- **Question**: What is the password of user Jones?
- **Answer**: `12345678` - (Correct Attempt)

### 3. Analyze Registry Snapshot for Driver Package Changes
- **Question**: Has the driver packages registry changed? (Yes/No)
- **Answer**: `Yes` - (Correct Attempt)

### 4. Identify Sniffing Protocol from Network Traffic
- **Location**: Documents folder on EH Workstation - 2 (Windows 11), file `sniffsession.pcap`
- **Question**: What protocol was used for sniffing on the network?
- **Answer**: `ARP` - (Correct Attempt)

### 5. Find ICMP Packet ID in Traffic Capture
- **Location**: Documents folder on EH Workstation - 2 (Windows 11), file `webtraffic.pcapng`
- **Question**: Find the packet ID that uses the ICMP protocol.
- **Answer**: `0xfc83` - (Correct Attempt)

### 6. Analyze Leaked Credentials in Web Application Traffic
- **Location**: Documents folder on EH Workstation - 2 (Windows 11), file `movies.pcapng`
- **Question**: What are the leaked credentials?
- **Answer**: `Jason/welcome` - (Correct Attempt)

### 7. Determine Data Size of Custom UDP Packet
- **Location**: Documents folder on EH Workstation - 2 (Windows 11), file `CustomUDP.pcapng`
- **Question**: What is the data size of the UDP packet (in bytes)?
- **Answer**: `600` - (Correct Attempt)

### 8. Find Attacker's IP in DoS Attack Traffic
- **Location**: Documents folder on EH Workstation - 2 (Windows 11), file `DoS.pcapng`
- **Question**: What is the IP address of the attacker's machine?
- **Answer**: `192.168.0.51` - (Correct Attempt)

### 9. Analyze Network Traffic Surge in CEHORG Datacenter
- **Task**: Study network traffic logs due to increased incoming traffic from multiple sources in CEHORG's datacenter.
answer: 3

## 13. The incident response team has intercepted an image file from a communication that is supposed to have just text. You are asked to investigate the file and check if it contains any hidden information. Find out the information hidden in the file. Note: The vacation.bmp file is located at C:\Users\Admin\Documents in EH Workstation – 2 machine. (Format: AAANNNNNNN)
answer: USD1234567

## 14. An employee in your organization is suspected of sending important information to an accomplice outside the organization. The incident response team has intercepted some files from the employee's system that they believe have hidden information. You are asked to investigate a file named Confidential.txt and extract hidden information. Find out the information hidden in the file. Note: The Confidential.txt file is located at C:\Users\Admin\Documents in EH Workstation – 2 machine. (Format: Aaaaa/AaaaaaaNNNNN)
answer:James/Hopkins13456

### 15. Use Yersinia on the “EH Workstation – 1” (Parrot Security) machine to perform the DHCP starvation attack. Analyze the network traffic generated during the attack and find the Transaction ID of the DHCP Discover packets. (Format: NaNNNaNNNN)
answer:

## 16. A denial-of-service attack has been launched on a target machine in the CEHORG network. A network session file "DoS.pcapng" has been captured and stored in the Documents folder of the EH Workstation - 2 machine. Find the IP address of the attacker's machine. (Format: NNN.NNN.N.NN)
answer: 192.168.0.51

## 17.CEHORG hosts a datacenter for its bussiness clients. While analyzing the network traffic it was observed that there was a huge surge of incoming traffic from multiple sources. You are given a task to analyze and study the DDoS.pcap file. The captured network session (DDoS.pcapng) is stored in the Documents folder of the EH Workstation -2 machine. Determine the number of machines that were used to initiate the attack. (Format: N)
Answer: 3



```

