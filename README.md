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
Cheatsheet: https://pentestlab.blog/2012/12/24/sql-injection-authentication-bypass-cheat-sheet/

### Nmap
Scan for vulnerabilities: nmap -Pn --script vuln 10.x.x.x

### RSA
https://github.com/ius/rsatool<br />
https://github.com/Ganapati/RsaCtfTool

### SSH
https://medium.com/bugbountywriteup/cracking-ssh-private-key-passphrase-459ba17e8d5d


### HASH
Identify hashes: https://hashes.com/en/tools/hash_identifier<br />
Tool to identify hashes: https://gitlab.com/kalilinux/packages/hash-identifier/-/tree/kali/master <br />
- *wget https://gitlab.com/kalilinux/packages/hash-identifier/-/raw/kali/master/hash-id.py*<br /> 
- *python3 hash-id.py*

### Active Directory
PowerView-3.0 tips and tricks https://gist.github.com/HarmJ0y/184f9822b195c52dd50c379ed3117993

### Ghostcat
https://github.com/00theway/Ghostcat-CNVD-2020-10487

### Steganogrphy
https://pequalsnp-team.github.io/cheatsheet/steganography-101 <br />
https://github.com/DominicBreuker/stego-toolkit
