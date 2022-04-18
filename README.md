## RPi Kiosk

Kiosk system for the Raspberry Pi. Build and tested on Raspberry Pi 3 running RaspiOS BullsEye ([link](https://downloads.raspberrypi.org/raspios_full_armhf/images/raspios_full_armhf-2022-01-28/))

**Installation:**

    cd ~
    sudo apt-get -y install git
    git clone https://github.com/JCQ81/rpi-kiosk.git
    cd rpi-kiosk
    sudo chmod +x install
    sudo ./install

**Functionality:**
 - Screen types / media types / extentions:
	 - Images: .jpg / .png
	 - Videos: .mp4
	 - Websites: .html / .url (windows web link)
 - Media source options:
	 - USB stick (map on USB stick: /kiosk)
	 - HTTP provisioning
		 - Path from DHCP option 241 with name CPATH
		 - Configuration file 
		 	- Filename: [serialnumber].cfg (*cat /proc/cpuinfo | grep Serial*)
		 	- Content: (see example file)
		 		- Path to media package 
				- Delay between screens
		- Media package
			- Archive file (.tgz/.zip/.7z) containing media files
 - OS:
 	- Runs kiosk as a service, using a limited user without autologin
	- Set filesystem to ReadOnly for extending SD lifespan
 		- To make changes, disable ReadOnly (active until reboot): *kioskctl rw*
