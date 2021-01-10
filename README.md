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
sudo add-apt-repository ppa:gnome-terminator<br />
sudo apt-get update<br />
sudo apt-get install terminator<br />
