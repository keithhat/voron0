# voron0
This tracks my Voron 0 build.
This was originally a Siboor 0.2 r1 kit (think Aug2023) with ABS printed parts. I bought of AliExpress from official Siboor retailer.
Having time again I'd see price bying from siboor directly to choose different colours.

# Main Info
* http://192.168.7.60/#/
* username: fly
* default password: mellow

# Notes
* Do NOT do full apt upgrade on console.
** I seemed to break my Siboor image; eventually got everything back using the Gemini images.
* The polarity of at least the extruder fan is important.

# Build Info
## Mechanical
The mechanical build largely went well following the PDF manuals.
As this was a 0.2r1 kit some mod 'patches' were not fully covered. I made some notes in.

The ADX345 accelerometer mounting was eventually found at end of <TODO>.
I had previouslly used longer bolts and attempt to mount to front of toolhead.

## Nozels
I needed to buy a 7mm wrench to help change nozels

## Electrical
My extruder fan was not originally working. This was tracked to a polarity issue into the fan cable. These cannot be swapped.

## FW
(!)Do not do arbitrary system udpates for gemini board. Updating through mainsail interface was ok though.
Flashing fimware main indicate success and failure; this was found to be ok but confirmed through dfinding id



# TODO
1. Cleanup all files I have in other window; adding notes etc to git.
2. Find links to all documents I have and add here
3. Store all documents and FW I have; maybe another repo?
4. Look at all linked webpages I have to store here.

* PDFs for building
** Siboor mods to vanilla voron:
*** https://docs.siboor.com/siboor-0.2-r1-aug/the-build/assembly-manual
* Wiring Summar and intiial setup: https://docs.siboor.com/siboor-0.2-r1-aug/the-build/initial-startup
* FW used

# Main Components
* Kirigami Bed
* Phaetus Dragon HF Hotend
* Gemini v3 mainboard

# Current Status
## Blockers for printing
* Extruder calibration / esteps
* Retude PID for hotend, now has fan.
* Bed Screws Adjust macro working - to help with bed levelling
* Re-level bed and setup z-home
* Slicer integration; ideally over wifi
* Do initial print calibration
* Confirm emergency stop on display works


## Nice to improve
* Can extruder fan be controlled? Ideally off unless extruder > say 40deg. Allows machine to be quieter / always on.
* Ensure chamber fan does get triggered
* What is the MCU LED - has the Kirigami LED replaced this?
** Does the LED on the screen have a name?
* Nevermore camber filter - to help with ABS fumes as know will be in confined space
* I don't like z stop at bottom - at least how I'm doing z homing it is a pain.
** Currently finds switch but then goes fixed amount up as home. This isn't really viable with z-offset and bed levelling.
** Maybe combine with new toolhead for better solution.
** There are now lots of new options; Klacky, integrated into hotend, cartographer probing
* Look at Filament path through rear-right foot. May need pnumatic couplers rather than attempt to feed PTFE tube
* Ensure idler cam locks work well with printer hat
* Checkk toolhead is ok with PLA, may need better cooling.
** Can explore other options including CAM controlled for more flexible cambling
** Consider adding LED lights; I decided to NOT use in original mini StealthBurner build
** Consider a filament cutter to allow AMS system such as armoured turtle, 8 track or ERCF v2.
* Look at accelerometer and input shaping.
* Klipper LED as status - may need to setup Klipper-LED effects
* Camera - ideally mounted on top of z extruction. This may need mjpg-streamer + www-mjpgstreamer



# LED Installations
https://docs.siboor.com/other-products/led-effect-notes/installing-led-effects-software

cd ~
git clone https://github.com/julianschill/klipper-led_effect.git
cd klipper-led_effect
./install-led_effect.sh