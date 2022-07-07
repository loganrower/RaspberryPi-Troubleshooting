# Enabling Ethernet on Pi's

## Buster OS installation 4/2022
(LAST CHECKED 7/6/2022)
If it is a fresh buster installation all that is needed is the following

Go to:
* sudo nano /etc/network/interfaces

In the interfaces file you will need to write the following line at the bottom 
* auto eth0

This will enable the eth0. However, it will be the same address so you will need to reset laptop such that it will be able to accept the device...

## Buster OS installation 4/2022 w/ Pi Wifi Access Point Functionality
