## RPi Kiosk

Kiosk system for the Raspberry Pi. Build and tested on Raspberry Pi 3 running RaspiOS BullsEye ([link](https://downloads.raspberrypi.org/raspios_full_armhf/images/raspios_full_armhf-2022-01-28/))

**Installation:**

    cd ~
    mkdir kiosk-setup
    cd kiosk-setup
    git clone https://github.com/JCQ81/rpi-kiosk.git
    sudo chmod +x install
    sudo ./install

**Functionality:**
 - Screen types / media types / extentions:
	 - Images: .jpg / .png
	 - Videos: .mp4
	 - Websites: .html / .url (windows web link)
 - Media sources:
	 - USB stick (path: /kiosk)
	 - HTTP provisioning
		 - Path from DHCP option 241 with name CPATH
		 - Configuration file 
		 	- Filename: [serialnumber].cfg (*cat /proc/cpuinfo | grep Serial*)
		 	- Content: (see example file)
		 		- Path to media package 
				- Delay between screens
