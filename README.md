# voron0
This tracks my Voron 0 build originally from a Siboor 0.2 r1 kit

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

## Electrical
My extruder fan was not originally working. This was tracked to a polarity issue into the fan cable. These cannot be swapped.


# TODO
Extract all paths I have floating around:
* PDFs for building
* FW used

# Main Components
* Kirigami Bed
* Dragon HF Hotend
* Gemini v3 mainboard - this has a RPI cl

# Current Status
## Blockers for printing
* Extruder is currently slipping, disassemble and check path.
* Retude PID for hotend, now has fan.
* Re-level bed and setup z-home
* Do initial print calibration

## Nice to improve
* Don't like z stop at bottom - pain for homing. Maybe combine with new toolhead for better solution.
** There are now lots of new options; Klacky, integrated into hotend etc
* Look at Filament path through rear-right foot. May need pnumatic couplers rather than attempt to feed PTFE tube
* Ensure idler cam locks work well with printer hat
* Checkk toolhead is ok with PLA, may need better cooling. Can explore other options including CAM controlled for more flexible cambling
* Look at accelerometer and input shaping.
* Klipper LED as status - may need to setup Klipper-LED effects
* Camera - ideally mounted on top of z extruction. This may need mjpg-streamer + www-mjpgstreamer