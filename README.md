# voron0
This tracks my Voron 0 build.
This was originally a Siboor 0.2 r1 kit (Aug2023) with ABS printed parts. I bought of AliExpress from official Siboor retailer.
Having time again I'd see price bying from siboor directly to choose different colours.

# Main Info
* http://192.168.7.60/#/ (Ethernet)
	* WiFi 2.4GHz: http://192.168.7.61/#/
* Login:
	* username: fly
	* default password: mellow

# Notes
* Do NOT do full apt upgrade on console.
	* I initially broke my Siboor image doing this, I did force some which may have been kernal.
	* I got everything back using Gemini images and some sample Siboor files.
	* Updating through the mainsail interface was ok, including plugins. Some had path clashes that were easily resolved.
* The polarity of at least the extruder fan is important.
* My extruder was skipping when initially tuning, ended up being some broken filament in heatbreak. Disassembled and used a tool to help extract

# Build Info
## Mechanical Assembly
* The mechanical build largely went well following the PDF manuals.
	* As this was a 0.2r1 kit some mod 'patches' were not fully covered.
* The ADX345 accelerometer mounting was eventually found at end of "assembly/4 SIBOOR0.2-supplementary.pdf".
	* I had previouslly used longer bolts and attempt to mount to front of toolhead.
* I think there are other notes somewhere
	* Alignment tools ~ 19min of https://www.youtube.com/watch?v=zX7Bgzhw0OM&list=WL&index=6&ab_channel=KanduWorkshop
	* Motor B/X is top left  when viewed from the front
	* Motor A/Y is top right when viewed from the front
	* I didn't sand axel so gears more free (~p160)
	* Something about [4] p9
		* I didn't do this, at least not initially. It also required splicing both in parallel


## Electrical
My extruder fan was not originally working. This was tracked to a polarity issue into the fan cable. These cannot be swapped.

## FW
(!)Do not do arbitrary system udpates for gemini board. Updating through mainsail interface was ok though.
Flashing fimware main indicate success and failure; this was found to be ok but confirmed through dfinding id


# Current Main Components
* Kirigami Bed
	* Has 8 RGB LED neopixel in logo
* Phaetus Dragon HF Hotend
* Gemini v3 mainboard
* V0 Umbilical
	* This is fairly stiff; a CAM bus or USB equivalent think would be useful in future

# Guides - Assembly, FW and Tuning
* Siboor v0.2 r1 Aug: https://docs.siboor.com/siboor-0.2-r1-aug
	* Initial Startup and Wiring: https://docs.siboor.com/siboor-0.2-r1-aug/the-build/initial-startup
	* Mods to vanilla: https://docs.siboor.com/siboor-0.2-r1-aug/the-build/assembly-manual
* Gemini v3:
	* Image: https://mellow.klipper.cn/en/docs/ResDownload/system-img/fly-Gemini/?persistLocale=true
	* General: https://mellow-3d.github.io/fly-gemini_v3_general.html
	* Fan: https://mellow.klipper.cn/en/docs/ProductDoc/MainBoard/fly-gemini/fly-gemini-v3/fan/
* Voron: https://docs.vorondesign.com/build/software/

## Tuning and Initial Setup
This explicitly calls out some sections
* Moving, homing, estep, PID: https://docs.vorondesign.com/build/startup/
* Sensorless Homing: https://docs.vorondesign.com/tuning/sensorless.html
* Klipper Common Errors: https://docs.vorondesign.com/community/troubleshooting/eddie/klipper_common_errors.html

## Sample Configus
* Siboor Voron 0.2 Aug: https://github.com/Lzhikai/SIBOOR-Voron-0.2-AUG/blob/main/printer.cfg

## Neopixel LED effects
* https://github.com/julianschill/klipper-led_effect
* https://docs.siboor.com/other-products/led-effect-notes/configuring-the-effects
* https://docs.siboor.com/other-products/led-effect-notes/advanced-effect-layer-blending

### Various Sample Effects
* https://gist.github.com/bistory/08e279ebda4d5cd2521dfe1add09dab4
* https://pastebin.com/GBzkNXcq
* https://pastebin.com/pv8M4huD
* https://github.com/julianschill/klipper-led_effect/blob/master/examples/Voron_Stealthburner/stealthburner_led_effects_3_leds.cfg

## Unsure if used:
* https://www.klipper3d.org/Config_Reference.html


# Additional Tools:
The Dragon HF seemed to be missing some additional tools in full kit; ended up getting the following to help
I bought following:
* Open Ended Mini Spanners: https://www.amazon.com.au/dp/B0DBY93B7Q 			AUD 14.98 	Set (4mm, 4.5, 5, 5.5, 6, 7, 8, 9, 10, 11)
    * These worked for removing nozzel from Dragon HF, but was relatively thick for disassembly heatbreak from heat-block.
* Hex Wrench for Dragon HF heat-block (1.27mm):
	* https://www.ebay.com.au/itm/196192220714 AUD 24.88 for Set (0.9, 1.27, 1.3, 1.5, 2.0)
	* https://www.ebay.com.au/itm/134291755243 AUD 3.10 single 1.27mm
* Hex multi-tool to help with Hotend: https://www.amazon.com.au/dp/B0DSBQDLFP 	AUD 11.89 	Spanner: (6, 7, 8, 10,20), Hex Tool: (M2.5, M2, M3, M4), Copper Wire Brush
	* Got to help have a thinner spanner for Dragon HF disassembly - unblocked before needing to disassemble.
* Filament unblock tool (when nozel removed): https://www.aliexpress.com/item/1005002948629438.html 	AUD 2.95
	* I made a seperate heatbreak and heat block that could be connected to umbilical and moved from printer to help unblock.
		* Heater Block: https://www.aliexpress.com/item/1005005038625574.html 	AU 8.99 	Up to 500deg. Missing silicon sock, I got the wrong one.
* Nozzle Needless:
	* https://www.aliexpress.com/item/1005004227280655.html AUD 4.09 	(0.2 and 0.5)
* Anti-Static Tweezer set: https://www.aliexpress.com/item/1005007425589207.html 	AU 4.59


# Additional Parts
## General
These can be ued with several of below
* I bought several stainless steel nozels for different sizes and abrasive materials.:
	* https://www.aliexpress.com/item/1005001620042630.html 	AUD 4.14  	I got pairs on: (0.2, 0.4, 0.6)
* Drive Gear with Hardended Steel gears - have NOT yet used this for gears (arrived after re-assembling mini Stealthburner)
	* https://www.aliexpress.com/item/1005007929025658.html 	AU 7.39 	Intended as spare 50T gear and abrasiev filamenets.

## Parts for Dragon HF Hotend abrasive/replacement
These are not yet used, arrived too late. 
TODO: Need silicon cover. This is WRONG for Phaetus Dragon HF: https://www.aliexpress.com/item/1005005886011113.html 	AU 5.79
TODO: Need cool zone? Possibly something that can be shared with EnderNG
* I made a hotend that could be used to unblock hotend or nozels (think 3rd party Dragon HF):
	* 50W 24V thermistor / heaterset: https://www.aliexpress.com/item/32967546419.html 	AU 5.39
	* HF Heatbrewak: https://www.aliexpress.com/item/1005006869637598.html 	AU 23.79

## Replacement Hotend
A cheaper hotend for abrasive seems useful. Also allows using if Dragon blocked.
TODO: Confirm can use above stainless stell nozzels
TODO: Make up as drop-in for Dragon HF; mini stealthburner, then Dragon Burner
* I later bought a TZ-V6 2.0 Hotend - 35mm3/s
	* 60W V6: https://www.aliexpress.com/item/1005006417172044.html 	AU35.19. TBC if ok for abrasive.
		* Nozzle: SKD11, hardness: HRC60 - TBC if takes above V6 stainless stell (this looked smaller.)

## Dragon Burner
The Dragon Burner seems to be better reviewed, especially for PLA. Also would like a filament cutter (for box turtle) and nozzle probe for correct z-offset.
Home is: * Dragon Burner v8 Home: https://github.com/chirpy2605/voron/blob/main/V0/Dragon_Burner/README.md

### Bought Parts
* 1x 3010 24V 			https://www.aliexpress.com/item/1005002857100082.html 	AU 13.89 x1
* 2x 4010 Blower 24V 	https://www.aliexpress.com/item/32799324058.html 		AU 9.49 x2
* Orbiter v2.5 Extruder: https://www.aliexpress.com/item/1005007653572332.html 	AU 79.18
* Logo NeoPixel: https://www.aliexpress.com/item/1005006046634379.html 	AU 11.79 	(looks to have sockers already) + 2 LEDs
	* NeoPixel DIY: https://www.aliexpress.com/item/1005007646205279.htm 	AU 6.09 	<- Unsure if would be better than above. Got both to check.
* RGA Sequins: https://www.aliexpress.com/item/1005006023213341.html 	AU 5.62 (4 LEDs)
	* Neopixel Alternative: https://www.aliexpress.com/item/1005006220336798.htm 	AU 5.79 	<- I got both, thought this was neopixel above normal RGB


# Future Thoughts
* Look at case quick assembly and door handles
* Look at chamber filter - maybe something to vent if ABS stinks
* INDX looks interesting, expect to fit 4x toolchangers in V0. Can be shared with EnderNG etc
* Do up V6 drop-in could be good for replacements (replaced by above) - mini steath burner then dragon burner.
* Dragon Burner - gets good reviews. Allows for AMS and potentially probing.
* Box Turner AWS - allow filamenet swaps after filament cutter
	* May need filamenet run-out sensors etc
* If INDX can support CAM bus good to update all system for better strain relief.
* Maybe replace Fly-Gemini-V3 to RPI4 and generic with CAM support. Allow mainline klipper??