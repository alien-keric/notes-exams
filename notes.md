1. There is a machine running wamp server in the subnet. Provide the IP address of the server.(Find WampServer - inarun kwenye port 8080 - find ip [sikumbuki] utatoa kwenye nmap scan)

2.  Find the FQDN of the domain controller in the network. (nmap -sC -sV -vv 10.10.1.18 - [AdminTeam@.ECCCEH.com] )

3.  Identify the machine with smb enabled. Crack the smb credentials for the username given ("Apple123"). Access an encrypted file (sniff.txt) and decode the encrypted file to retrieve the flag. "hydra -l henry -P ~/Desktop/passwords.txt <IPINHERE> smb", "smbclient //<IPINHERE>/Users -U henry%Apple123 after here, cd Documents then kuna sniff.txt"

4.  There is an Android device in the subnet (nmap results look). Identify the device(adb connect 192.168.0.19:5555 then adb shell ). Get the files in scan folder(cd sdcard/Notification/Scan). Provide SHA384 hash with the largest of entropy (Answer linaanza na 7aea, hizo ni digit nne za mwisho, so utaangalia tu digits nne za mwisho, then inayofanan na hii, ndo jibu).

5.  Perform the vulnerability scan for the given IP address. What is the severe value of a vulnerability that indicates the end of life for a web development language platform?(10)

6.  Exploit a remote login application on a Linux target in the given subnet to access a sensitive file. Hapa utaangalia kwenye IP inayoanza na 192, then utaenda kwenye specific IP ambayo OS yake ni linux, kwenye hiyo specific IP utaangalia open ports ambazo unaweza kuziexploit so that to get root privileges, one among the port which is open is nfs, japo binafsi sijajua jinsi ya kuiexploit, i hope utaweza exploit.

7.  Analyze the image file to extract the hidden message. Password is given.( cd Documentsfile  called MyTrip.jpg, open with openstego then Extract then select Mytrip.jpg then chose folder to save output then enter password in which it was 'Imagination' provided from question). utapata bctextencoder then keep the whole massage to decrypt the message

8.  Exploit weak credentials of FTP. Obtain the hidden file. (password: Apple123; ftp ftp://sysadmin:Passwordfound@192.168.9.23
ls -la
get file.txt)

9.  Escalate privilege on a Linux machine. User-level credentials are given.( ssh running 192.168.0.0/24 then login in with username(smith) na password(L1nux123) provided then cat /imroot.txt : ssh smith@192.168.0.0/24)

10.  Find a file entry point. File is given(utapewa file la linux ila lipo kwenye windows, ww livute(smbclient //<IP>/Users -U 'Admin%Pa$w0rd') kutoka kwenye windows mpaka linux then open it with Cutter then look for entry0 - utaona address ya entry0), au unaweza kudownload cutter kwenye window ukafanyia hukohuko.

11.  From a pcap file, analyze a DDOS attack and provide the IP address that sent most packets.(open file then statistics - conversation - then IPV4 - then angalia bytes nyingi then take ip address = [172.20.0.21] 172 itakua pekeake)

12.  You are provided a username/password for a website. Use SQL Injection attack to extract the password of another user.(SQL injection kama moviescope.com kwenye lab (MSSQL Injection)
/ SQL injection on cybersecurity.cehort.com --> click kila sehemu on index page - tafuta id parameter then tumia sqlmap tool )

13.  Exploit a web application at www.xxxx.com and enter the flag value from given page.(Wordpress - www.cehort.com/?page_id=84 ndo kuna flag but lazima ulogin, so kubruteforce, wpscan --url http://wphost/ --passwords ~/Desktop/passwords.txt "(admin:Apple123)" but warning hii server ni nzito balaa). Kulingana na uzito wake sikufanikiwa, ilikuwa inaload mpk mwisho wa pepa

14.  Perform vulnerability research and exploit the target at given site.

15.  Perform SQL injection on a website and extract flag value.

16.  A file is available in a directory with DVWA. Access the file and enter the contents.( read hashes - login kwenye DVWA(admin:password) then login into DVWA change security from imposible to low then go to Command injection
                       Command za kutumia=>                '| dir <PATH ULIOYOPEWA>' then '| type <PATH ULIOYOPEWA>/Hash.txt then Crack online). Hii DVWA kaifungulie kwenye window machine.


17.  Analyze IoT traffic from a pcap file. Identify the packet with the publish message and enter the length.(Utapewa file then utaopen then utambiwa tafuta push message sasa ww utafilter 'mqtt' then utafuta push message na click any stream then angalia packet detail kutafuta message length - Ans[39])

18.  Crack the weak credentials of wifi from a pcap file. (aircrack-ng filename.cap -w ~/Desktop/passwords.txt  Answer [password1])

19.  A RAT server is installed on a server. Connect with it and access the file.(Hili lilikuwa linasema kuna remote machine ambayohuwezi kuifikia physically lkn kuna code file ambalo lipo kwenye hiyo machine, hiyo machine in window OS , lkn unachokijua ni kwamba hiyo machine ina RAT ambayo imekuwa installed for administration, so wanataka hilo code file hrf husubmit hiyo code, hiyo RAT nafikiria ni (Remote Administaration tools). 

20.  Decrypt the veracrypt volume.( Access file from windows ambayo ni hash(butterfly), wewe google then utaitumia kudecrypt volume ya Secret(C:\Secret) then kuna file lenye content ambayo ndo flag)

using site to google hash: (hashes.com
