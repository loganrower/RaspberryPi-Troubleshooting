# Enabling Ethernet on Pi's

## Buster OS installation 4/2022 w/ Pi Wifi Access Point Functionality
(LAST CHECKED 7/7/2022)
If it is a fresh buster installation all that is needed is the following

Go to:
* sudo raspi-config

Enable ssh and vnc. Primarily just need ssh in order to allow 
the laptop to recieve the connection

In addition DO NOT make any changes to the dhcpcd.conf or the interfaces files. There are methods to make a static ip address for a pi using these methods, but this may result in conflicts with the DHCP server connection and disable the wirless interfaces.

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

This will work for all pis using the same ethernet cable and connecting to the same device so the IP address should not change.
