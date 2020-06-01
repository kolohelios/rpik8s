# rpik8s
Raspberry Pi K8s stuff


## Stuff:

- Raspbian Lite (32bit image) on Samsung 32 GB EVO Plus micro SD card
- 4 Raspberry Pi 4B, 4 GB of RAM, CanaKit USB C power adapters, 1 ft. gigabit Ethernet cables, and a four pi stackable case
- Linksys 8-port gigabit switch

## Initialization

For each pi, create an empty file in /boot on the micro SD called ssh (with no extension); this will allow you to connect to the pis remotely

In your router settings, add DHCP reservations for each pi. You'll need the MAC address. I used 192.168.1.10x (101, 102, 103, and 104) and the hostnames `rpik8sm`, `rpik8s1`, `rpik8s2`, and `rpik8s3`. It's your world; call them whatever you want to.

Once they are booted up, ssh in and run `sudo raspi-config`; set the hostnames accordingly, and choose to reboot once the change is made. This will save you some trouble when wondering which pi you're ssh'd into.

May as well update them; run `sudo apt-get update && sudo apt-get upgrade --yes` for each.

Follow ths guide to install `k3s`: https://opensource.com/article/20/3/kubernetes-raspberry-pi-k3s
