# Backlog of tasks

This is a backlog of tasks I'd like to improve. It was started after initial mechanical assembly.

# Current Status
## Blockers for printing

* Re-level bed and setup z-home (z-offset) - with heated bed and hotend
    * Initially look at: https://docs.siboor.com/siboor-0.2-r1-aug/the-build/initial-startup-checks#calibrate-the-z0-position
    * Then continue with anything else in Guide: https://docs.vorondesign.com/build/startup/#z-endstop-location-v0 mentions Z_ENDSTOP_CALIBRATE - think also wants cold with paper.
    * Check probing all points is 120; was 121 when cold.
    * See if can adjust bed height to avoid initial 'hacks'
    * How was the bottom endstop set? Add it if possible

* Look at running/fixing: v0: BED_SCREWS_ADJUST - MAY help with bed levelling
    * Initially look at: https://docs.siboor.com/siboor-0.2-r1-aug/the-build/initial-startup-checks#bed-screws-adjust
    * Then continue with anythign else in Guide: https://docs.vorondesign.com/build/startup/#bed-screws-v0
    * Hotend with stainless steel and fan now working
    * On printer think:
        * /home/fly//klipper/klippy/extras/bed_screws.py
      * Also have:
        * /home/fly//KlipperScreen/panels/bed_mesh.py
        * /home/fly//klipper/klippy/extras/bed_mesh.py

## Final setup before doing generic prints
* Calibration Prints
  * cube https://docs.siboor.com/siboor-0.2-r1-aug/the-build/slicer-setup#slice-the-3d-model
      * Check can wirelessly send to printer
  * Maybe more at: https://docs.siboor.com/siboor-0.2-r1-aug/tuning-guides (some of these are below in stretch)
  * Teching Tech or makers muse likely have others; retraction, overhangs etc
* Move printer to next to ender3
* Look at steps to apply for serial.


## Stretch
* Look at accelerometer and input shaping.
  * Resonances: https://docs.siboor.com/siboor-0.2-r1-aug/tuning-guides/measuring-resonances
* Check if need to tune: Pressure Advance, Smooth Time
  * Pressure Advance: https://docs.siboor.com/siboor-0.2-r1-aug/tuning-guides/pressure-advance
  * Random video: https://www.youtube.com/watch?v=LVp15eGXwm0

* Klipper LED as status - Something for finished, Printing and loading
* Camera - mount on top of z extruction.
    * I bought: https://www.amazon.com.au/dp/B09KHHN8B3
    * Have this working with crowsnest - think deprecates mjpg-streamer + www-mjpgstreamer

## Nice to improve
* Case clips for panel quick attach/detach
* Door handle fix - I'm ok to screw through front panel
* Can extruder fan be controlled? Think also called hotend fan.
    * Ideally off unless extruder > say 40deg. Allows machine to be quieter / always on.
    * According to: https://docs.siboor.com/siboor-0.2-r1-aug/the-build/initial-startup-checks the Hotend fan cannot be controlled.
    * Any spare switch we can use to control?
    * https://docs.vorondesign.com/build/startup/#pid-tune-bed--hotend says Parts cooling to 25% can be done with: M106 S64
    * Eg: SET_FAN_SPEED FAN=Nevermore SPEED=0.7
    * Fly_Gemini_v3 defines:
        * FAN0=PC6,
        * FAN1=PC7,
* Ensure chamber fan does get triggered
* What is the MCU LED - has the Kirigami LED replaced this?
* Nevermore chamber filter - to help with ABS fumes as know will be in confined space
* Z-Stop - ideally Nozel probe
    * I don't like z stop at bottom - at least how I'm doing z homing it is a pain.
    * Currently finds switch but then goes fixed amount up as home. This isn't really viable with z-offset and bed levelling.
    * Maybe combine with new toolhead for better solution.
    * There are now lots of new options; Klacky, integrated into hotend, cartographer probing
* Look at Filament path through rear-right foot. May need pnumatic couplers rather than attempt to feed PTFE tube
* Ensure idler cam locks work well with printer hat
* Check toolhead is ok with PLA, may need better cooling. Think Dragon Burner useful and helps with some other options (filament cutter, maybe probe)
    * Can explore other options including CAM controlled for more flexible cambling
    * Consider adding LED lights; I decided to NOT use in original mini StealthBurner build
    * Consider a filament cutter to allow AMS system such as armoured turtle, 8 track or ERCF v2.
* LED Strips and possibly affects (if RGB)

# Print Fixes / Upgrades
* AC input fix
* Fix door handle
* Carry Handles
* Panel clips for quick removal
* Rear right foot w filament inspection and/or better bowden tube access:
    * THINK: https://github.com/Lzhikai/SIBOOR-Voron-0.2/blob/main/supplementary/R0_Upgrade_R1-STL/Foot_Rear_Right_FRS_R0_x1.STL
        * MAYBE: https://github.com/VoronDesign/Voron-0/blob/Voron0.2r1/STLs/Skirts/Foot_Rear_Right_FRS_x1.STL
    * Possibly just didn't do pseumatic install??
* Alternative filament path
* Camera mount


# Future Mods:
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

# Consider Buying Addons
* Alternative beds; ensure have something for each type; PLA, ABS, PETG
  * Glass (Tile?)
  * G10/FR4 PCB material as Bed
* INDX looks interesting, expect to fit 4x toolchangers in V0. Can be shared with EnderNG etc. Think LATE 2025 but monitor as closer
  * Especially if can support/requires CAM or USB extension. Can start replacing other toolheads earlier.
* Do up V6 drop-in could be good for replacements (replaced by above) - mini steath burner then dragon burner.
* Box Turner AWS - allow filamenet swaps after filament cutter
  * May need filamenet run-out sensors etc
* Consider CAM or USB version to toolhead vs this V0 Umbilical solution - maybe add to ender NG too for more mainline support/shared data.
* Maybe replace Fly-Gemini-V3 to RPI4 and generic with CAM support. Allow mainline klipper??
