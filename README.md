# keepnote-rip
Keepnote is no more maintain on kali. Being used to keepnote, I tried to find a way to continue to use it as before on my fully upgraded kali. In this repo, I will explain how to do that.

A +1 star if the below helps you guys.


# Step 1 : Install docker
apt-get install docker.io

# Step 2: Run docker
docker build -t th3xace/keepnote

docker run -it --name keepnote1 th3xace/keepnote

docker run -d -v /mnt:/mnt -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=unix$DISPLAY --name keepnote1 th3xace/keepnote

Note: the directory mnt is mapped on the host, so you can transfert files or watever from docker to host and host to docker. You can also map a usb device if you want to save the notes on a USB device. 

# Step 3 : Create a script with below content.

#!/bin/bash

service docker start

xhost +

docker start keepnote1

or run manually by running each command, one by one.

# Step 4 : Run the script through .bashrc 
put the below entry in the .bashrc
alias kp='bash /root/.scripts/keepnote.sh'

# Step 5 : Refresh .bashrc 
source /root/.bashrc

# Step 6 : run keepnote
run kp in terminal.

# The docker containes the following apps to be used via keepnote:
 + Firefox:  A browser to view notes in a web browser
 + Okular: Text Editor (view PDF)
 + Nautilus: File Explorer
 
 It is normally already configured in the keepnote (Edit > Preferences > Helper Applications)
 
 Enjoy! Keepnote on the new KALI.
 
 
