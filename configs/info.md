# Klipper setup / config / tuning

# Config Files 
I'm still learning klipper so there maybe better ways to backup files.
This has that information with a combination of where to place them.

## Paths

These paths are using the Gemini board FW locations
* /home/fly/printer_data/config/
	* printer.cfg is the main one that references everything
	* boards/FLY_GEMINI_V3.cfg defines aliases for various pins so can have generic references in other config files
	* V0Display.cfg configures the USB display
	* fly_macros.cfg defines some gcode macros including the homing functions.
	* mainsail.cfg is a simlink to /home/fly/mainsail-config/client.cfg
	* fluidd.cfg is a simlink to /home/fly/fluidd-config/client.cfg

## Extras
* The LEDs:
	* klipper/klippy/extras/led_effect.py is a simlink to /home/fly/klipper-led_effect/src/led_effect.py

# Tuning Notes
## Do STEPPER_BUZZ for correct directions
* The STEPPER_BUZZ (and then homing down) was useful for me to confirm z-axis. I'd assumed printing location should be 120 but this really should be 0.0.
	* STEPPER_BUZZ https://docs.vorondesign.com/build/startup/#stepper-motor-check and matching video: https://www.youtube.com/watch?v=wXYruV6QdDQ$t=1700
* Z Calibration
	* Home - will go down to bottom (max) then move back up to 30 (soem distance from nozel).
	* From https://docs.vorondesign.com/build/startup/#z-endstop-location-v0 run Z_ENDSTOP_CALIBRATE to tune Z0 to nozzle and setup position_endstop.
		* Nozzle cold with paper; as thermal expansion is 100um ~ paper
		* Viedo of similar is at: https://www.youtube.com/watch?v=wXYruV6QdDQ&t=2110
* Bed Levelling:
	* After homing can run BED_SCREWS_ADJUST
		* Manual is at: https://docs.vorondesign.com/build/startup/#bed-leveling
		* Video is at: https://www.youtube.com/watch?v=wXYruV6QdDQ&t=2480
	* Redo z-calibration after levelling to ensure probe is correct

# Pluggins
## Neopixel LEDs - ie BED Logo
Installed from: https://docs.siboor.com/other-products/led-effect-notes/installing-led-effects-software

```
cd ~
git clone https://github.com/julianschill/klipper-led_effect.git
cd klipper-led_effect
./install-led_effect.sh
```

## Crowsnest for USB camera
* It seems crowsnest deprecated MJPEG-streamer. Repo is at:  https://github.com/mainsail-crew/crowsnest
	* These command were from: https://www.youtube.com/watch?v=7A4wIKLQQoM&ab_channel=PrintsLeo3D
		* My image already had a ~/crowsnest so I commented out the first few lines
		```
		# cd ~
		# git clone https://github.com/mainsail-crew/crowsnest.git
		cd ~/crowsnest
		sudo make install
		# This did some apt updates - I had to do Armbian fix below
		```
	* Looking at error log (/home/fly/printer_data/logs/crowsnest.log) allowed me to setup crowsnest.conf - was using incorrect device
	* Needed to restart crowsnest then klipper.
	* Note: Only gettig around 5fps

# Apt Fixes

## Armbian key issues

I had the following message during apt update:
```
sudo apt update
Get:1 https://github.armbian.com/configng stable InRelease [3,992 B]
Err:1 https://github.armbian.com/configng stable InRelease
  The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 93D6889F9F0E78D5
Hit:2 http://repo.jing.rocks/armbian-apt bullseye InRelease
Hit:3 https://mirrors.tuna.tsinghua.edu.cn/debian bullseye InRelease
Hit:4 https://mirrors.tuna.tsinghua.edu.cn/debian bullseye-updates InRelease
Hit:5 https://mirrors.tuna.tsinghua.edu.cn/debian bullseye-backports InRelease
Hit:6 https://mirrors.tuna.tsinghua.edu.cn/debian-security bullseye-security InRelease
Reading package lists... Done
W: GPG error: https://github.armbian.com/configng stable InRelease: The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 93D6889F9F0E78D5
E: The repository 'https://github.armbian.com/configng stable InRelease' is not signed.
N: Updating from such a repository can't be done securely, and is therefore disabled by default.
N: See apt-secure(8) manpage for repository creation and user configuration details.
```

This was resolved by adding a key (found these looking though foroms from above error)
```
sudo wget https://apt.armbian.com/armbian.key -O key
sudo gpg --dearmor < key | sudo tee /usr/share/keyrings/armbian.gpg > /dev/null
sudo chmod go+r /usr/share/keyrings/armbian.gpg
sudo echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/armbian.gpg] http://apt.armbian.com $(lsb_release -cs) main  $(lsb_release -cs)-utils  $(lsb_release -cs)-desktop" | sudo tee /etc/apt/sources.list.d/armbian.list
sudo apt update
```
