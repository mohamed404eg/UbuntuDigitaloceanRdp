Commands: 
sudo apt update 
sudo apt install xubuntu-desktop 
sudo apt install xrdp 
sudo systemctl status xrdp 
sudo adduser xrdp ssl-cert 
sudo ufw allow 3389 
sudo ufw allow from 192.168.2.0/24 to any port 3389 (for specific IP address) 
sudo ufw reload 

To fix the common issue: 

Stop xrdp with sudo service xrdp stop 

Edit the xrdp start script: sudo nano /etc/xrdp/startwm.sh 

In this file, replace the lines 

test -x /etc/X11/Xsession && exec /etc/X11/Xsession 
exec /bin/sh /etc/X11/Xsession 
with startxfce4 

(You can comment out lines by adding # at the start)

 Restart xrdp with sudo service xrdp start 

Select Xrdp as the session, and log in.



https://www.youtube.com/watch?v=yDspwAm9_sY&t=2s

Ubuntu 20.04 (LTS) x64 is work good is test

