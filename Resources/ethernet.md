# Enabling Ethernet on Pi's

## Buster OS installation 4/2022 w/ Pi Wifi Access Point Functionality
(LAST CHECKED 7/7/2022)
If it is a fresh buster installation all that is needed is the following

Go to:
* sudo raspi-config

Enable ssh and vnc. Primarily just need ssh in order to allow 
the laptop to recieve the connection

In addition DO NOT make any changes to the dhcpcd.conf or the interfaces files. There are methods to make a static ip address for a pi using these methods, but this may result in conflicts with the DHCP server connection and disable the wirless interfaces.

Then connect the pi to the laptop via ethernet cable

The eth0 IPv4 address will differ between each pi device and will not change if you switch the OS SD Card in the Pi. So you can either document the IP address of each pi, or instead of that utilize the following command in linux terminal on your laptop or local machine in order to find the raspberry pi IP address

* ping raspberrypi.local

The output of this ping will be the IP address that you will need to utilize in order to ssh into the Pi, but before that we need to do a couple more things to make things a bit easier...

By just enabling ssh on the pi then you can install the following on ubuntu:
* sudo apt-get install dnsmasq-base

Then run nm-connection-editor where you can see the new ethernet connection (labeled as Pi)
* nm-connection-editor

You can then ssh into the ip address for the pi which will remain consistently the same.
* ssh pi@[ip_Address]

However, it is important to note that if there as an error where it says "WARNING REMOTE HOST IDENTIFICATION HAS CHANGED". Then you should
make note of the line that there is an error in the known_hosts file, and open that file and delete that line.
* /home/[name]/.ssh/known_hosts

After that line has been deleted then you can proceed to run the ssh command in order to connect to the pi from the linux machine
* ssh pi@[ip_Address]
