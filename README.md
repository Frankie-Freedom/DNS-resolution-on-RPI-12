# DNS-resolution-on-RPI-12
DNS resolution on RPI 12 with Network Manager
There was an error when trying to resolve with sites like github after a fresh install and enabling VNC I believe. 
There was a file in the /etc/nsswitch.conf that had a line that needed to be changed

hosts:          files mdns4_minimal [NOTFOUND=return] resolve [!UNAVAIL=return] dns

to 

hosts:          files dns mdns4_minimal [NOTFOUND=return] resolve [!UNAVAIL=return]

it is a small subtle change, but it was what fixed my issue of being able to git clone repos

original post 

https://forums.raspberrypi.com/viewtopic.php?t=278634
