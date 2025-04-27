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

# Main Components
* Kirigami Bed
* Phaetus Dragon HF Hotend
* Gemini v3 mainboard
