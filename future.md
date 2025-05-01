# Backlog of tasks

This is a backlog of tasks I'd like to improve.

# Current Status
## Blockers for printing
* Retune PID:
  ** Guide: https://docs.vorondesign.com/build/startup/#pid-tune-bed--hotend
  ** Hotend with stainless steel and fan now working
  ** Bed with all fans now working
* Above manual includes v0: BED_SCREWS_ADJUST - MAY help with bed levelling

* Re-level bed and setup z-home (z-offset) - with heated bed and hotend
  ** Check probing all points is 120; was 121 when cold.
  ** See if can adjust bed height to avoid initial 'hacks'
  ** https://docs.vorondesign.com/build/startup/#z-endstop-location-v0  Says do COLD with paper
* Check sensitivity for sensorless homing for x/y -> Less jerky finding end
  ** https://docs.vorondesign.com/tuning/sensorless.html

* Slicer integration; ideally over wifi
* Calibration Prints - ie cube


## Stretch
* Klipper LED as status - Something for finished, Printing and loading
* Camera - ideally mounted on top of z extruction. This may need mjpg-streamer + www-mjpgstreamer
* Look at accelerometer and input shaping.
* See if have included these - PDFs maybe in assembly
** Siboor mods to vanilla voron: https://docs.siboor.com/siboor-0.2-r1-aug/the-build/assembly-manual
** Wiring Summary and intiial setup: https://docs.siboor.com/siboor-0.2-r1-aug/the-build/initial-startup
** FW used
* Check if need to tune: Pressure Advance, Smooth Time

## Nice to improve
* Can extruder fan be controlled? Ideally off unless extruder > say 40deg. Allows machine to be quieter / always on.
** Any spare switch we can use to control?
* Ensure chamber fan does get triggered
* What is the MCU LED - has the Kirigami LED replaced this?
* Nevermore chamber filter - to help with ABS fumes as know will be in confined space
* Z-Stop - ideally Nozel probe
** I don't like z stop at bottom - at least how I'm doing z homing it is a pain.
** Currently finds switch but then goes fixed amount up as home. This isn't really viable with z-offset and bed levelling.
** Maybe combine with new toolhead for better solution.
** There are now lots of new options; Klacky, integrated into hotend, cartographer probing
* Look at Filament path through rear-right foot. May need pnumatic couplers rather than attempt to feed PTFE tube
* Ensure idler cam locks work well with printer hat
* Check toolhead is ok with PLA, may need better cooling.
** Can explore other options including CAM controlled for more flexible cambling
** Consider adding LED lights; I decided to NOT use in original mini StealthBurner build
** Consider a filament cutter to allow AMS system such as armoured turtle, 8 track or ERCF v2.
* LED Strips and possibly affects (if RGB)

# Print Fixes / Upgrades
  - AC input fix
  - Fix door handle
  - Carry Handles
  - Panel clips for quick removal
  - Rear right foot w filament inspection and/or better bowden tube access:
    - THINK: https://github.com/Lzhikai/SIBOOR-Voron-0.2/blob/main/supplementary/R0_Upgrade_R1-STL/Foot_Rear_Right_FRS_R0_x1.STL
      - MAYBE: https://github.com/VoronDesign/Voron-0/blob/Voron0.2r1/STLs/Skirts/Foot_Rear_Right_FRS_x1.STL
    - Possibly just didn't do pseumatic install??
  - Alternative filament path
  - Camera mount

## Future Mods:
  - Hat access filament > short path
    - Filament run-out senseor
  - Fan for fumes and bed heting.
  - Privacy for rear of chamber
  - Protector behind screen?
  - LED strips
  - Magentic side mounts?
  - Shorter HAT to fit in cube
  - Unsure: Filament runout sensor
  - Cam Locks > Larger hex wrench??. Maybe better options
  - I MAY have an expander; if so look at installing (possibly need for LEDs):
    - https://github.com/Lzhikai/SIBOOR-Voron-0.2/blob/main/expander/README.md




# Consider Buying
  - Alternative beds; ensure have something for each type; PLA, ABS, PETG
      - Glass (Tile?)
      - M8? PCB Stuff
  - CAN bus upgrade - for flexibility up top
  - FLY- GEMINI-V3 replacement + RPI.


# See if need somewhere else

* Notes:
  - Alignment tools ~ 19min of https://www.youtube.com/watch?v=zX7Bgzhw0OM&list=WL&index=6&ab_channel=KanduWorkshop
  - Motor B/X is top left  when viewed from the front
  - Motor A/Y is top right when viewed from the front

* Possible Future:
  - Sand axel so gears more fee, then reset gear (~p160). Add shims too!
  - Descibed in (4) p9.
    I didn't do this, at least not initially. It also required splicing both in parallel



=====