# Backlog of tasks

This is a backlog of tasks I'd like to improve. It was started after initial mechanical assembly.

# Current Status

## Final setup before doing generic prints

* Calibration Prints
  * cube https://docs.siboor.com/siboor-0.2-r1-aug/the-build/slicer-setup#slice-the-3d-model
  * Initial observations:
      * See if can look at homing; seems to need to be homed to start print but then starts homing again...
        * MAYVE Don't need. Noticed first time but this was good for reprinting the same job
      * First layer indicated some issues with oozing; at leat the white filament. Moving from purge line; and first layer
        * Think this is mainly retraction; think a stringing test to help set
      * Klipper console log showed some details - unknown command:
        * Unknown Command:
        *   EXCLUDE_OBJECT_DEFINE - at start
        *   EXCLUDE_OBJECT_START - lots of pairs
        *   EXCLUDE_OBJECT_END 0 lost of pairs
        * Popup at end of Job: Move out of Range: 230 230 36 [7355.028]
      * Some lines shown; seem consistent (for same job); are around end of z etc so maybe not just fixed x cm issues.
  * Assume Will Need:
    * Temperature Tower
    * Retraction Distance - Is this related to oozing??
    * First Layer??
    * Max Dimensions; especially Z and no shifts
    * Anything to help tune acceleration?
  * Maybe more at: https://docs.siboor.com/siboor-0.2-r1-aug/tuning-guides (some of these are below in stretch)
  * Teching Tech or makers muse likely have others; retraction, overhangs etc
* Move printer to next to ender3


## Nice to Have
* Filament runout sensor - from foot
* Look at accelerometer and input shaping.
  * Resonances: https://docs.siboor.com/siboor-0.2-r1-aug/tuning-guides/measuring-resonances
* Check if need to tune: Pressure Advance, Smooth Time
  * Pressure Advance: https://docs.siboor.com/siboor-0.2-r1-aug/tuning-guides/pressure-advance
  * Sameple videos: https://www.youtube.com/watch?v=deqJTNmnVyc  https://www.youtube.com/watch?v=LVp15eGXwm0

## Assistance for maintenance
* Case clips for panel quick attach/detach.
  * Several potential options; check all for V0.2 rather than V2.4 etc
    * Snap Latch for 1515: https://www.printables.com/model/172427-voron-01-filament-latch-1515-extrusion
      * As have M3 nuts MAYBE look at these. Unsure if other remixes etc
    * [FT Panel Clips for Voron V0/V0.1/V0.2] (https://www.printables.com/model/933648-ft-panel-clips-for-voron-v0v01v02) Only negative is key isn't flush
      * Alternative with same idea; https://github.com/KayosMaker/1515PanelClips (based on Annex but no longer skeletonized)
    * Potentially best magnet idea: https://www.printables.com/model/435407-voron-magnetic-panel-clips/comments
      * Unsure if need something else for doors
    * Zero Panels: https://github.com/zruncho3d/ZeroPanels
      * v3 Has tape mainly to keep alignment; potentially would like a version 2 without?
      * Some remix: https://github.com/adooze/ZeroPanels_for_Stock_V0.2
    * Excessively Magnetic Panel Mod https://www.reddit.com/r/VORONDesign/comments/1ccbihw/the_excessively_magnetic_panel_mod_emp_is_now_in/ / 
      * Needs 236x 6x3mm Magents, 8x M3x8 screens, 69xNits and VHB tape
      * Similar (unsure what are best):
        * https://github.com/VoronDesign/VoronUsers/tree/main/printer_mods/bobbleheed/Magnetic_Panels / https://mods.vorondesign.com/details/xQAsIUzijkbXU2yXrRKdXg
* Door handle fix - I'm ok to screw through front panel
  * Randome link: https://mods.vorondesign.com/details/mbzWlsb9PXA54FhWXtRCQ
* Add panels for dust etc
* Belt Tesnsion checking
  * https://github.com/Diyshift/3D-Printer/tree/main/GT2%20Belt%20Tension%20Meter
    * Need Spring and Piano wiring for correction tension
    * Video of demo: https://www.youtube.com/watch?v=AmgCqy7FisE
    * Link has tension guidlines: 1.9 for Voron 0. When printhead centered (and motors active)

## MVP Completion
* Look at process to apply for serial.

## Stretch

* LED Strips and possibly affects (if RGB)
    * Wiring: https://docs.siboor.com/siboor-0.2-r1-aug/faq-oct-3 
    * https://docs.siboor.com/other-products/led-effect-notes
    * https://docs.siboor.com/other-products/rgb-pcb-light
    * Also some Daylight STLs to mount
* Klipper LED as status - Something for Printing (percentage); loading job? Pause
    * Really want:
      * toolhead neopixel; so can indicate temperate
      * Enclosure LEDs; help show status?
* Camera - mount on top of z extruction.
    * I bought: https://www.amazon.com.au/dp/B09KHHN8B3
      * Look at designing own back mount to replace clip; USB strain relieft MAY need looking at; don't want to resolder anything when swap
      * I broke the retraction (spring flew out).


## Nice to improve

* Can extruder fan be controlled? Think also called hotend fan. Mainly for me being in same room :)
    * Ideally off unless extruder > say 40deg. Allows machine to be quieter / always on.
    * According to: https://docs.siboor.com/siboor-0.2-r1-aug/the-build/initial-startup-checks the Hotend fan cannot be controlled.
    * Any spare switch we can use to control?
    * https://docs.vorondesign.com/build/startup/#pid-tune-bed--hotend says Parts cooling to 25% can be done with: M106 S64
    * Eg: SET_FAN_SPEED FAN=Nevermore SPEED=0.7
    * Fly_Gemini_v3 defines:
        * FAN0=PC6,
        * FAN1=PC7,
* Modest Mesh; maybe several options eg: https://www.printables.com/model/407822-voron-v0-modesty-mesh
* Carry Handle

* What is the MCU LED - has the Kirigami LED replaced this?
* Nevermore chamber filter - to help with ABS fumes as know will be in confined space
* Z-Stop - ideally Nozel probe
    * Prefer probe bed accuratly than assume offset - potentially max height issues though. Good to understand why v0.2 moved to bottom?
    * This looks simple/cheap - doesn't allow for different beds though: https://github.com/Polar-Ted/STL-Files/tree/main/V0.1_Its_Not_a_Sexbolt_switch
        * Video is at: https://www.youtube.com/watch?v=bdxmqTDDsMM
    * Expect some options especially if change to DragonBurner - this would allow for differnt beds too.
    * There are now lots of new options possibly for bed leveling/mesh:
      * Beacon/Cartographer (original)
      * Eddy
      * Tap -> Moves entire toolhead so less rigid; BUT has both bed and nozzle.
      * Klacky? - look at
        - Unsure of nap that nozzle pushed on button next to bed. If this then one it picks up probe temporarily
      * BLTough ? unsure if still useful

* Ensure idler cam locks work well with printer hat
* Check toolhead is ok with PLA, may need better cooling. Think Dragon Burner useful and helps with some other options (filament cutter, maybe probe)
    * Can explore other options including CAM controlled for more flexible cambling
    * Consider adding LED lights; I decided to NOT use in original mini StealthBurner build
    * Consider a filament cutter to allow AMS system such as armoured turtle, 8 track or ERCF v2.
    * Additional filament sensors (blocked?)


# Maintenance
* Belt Tension:: https://www.youtube.com/watch?v=AmgCqy7FisE

# Print Fixes / Upgrades
* AC input fix
* Fix door handle
* Carry Handles
* Panel clips for quick removal
    * Zero Panels; have v3 that has tape PLUS foam. Will click onto frame so tape doesn't need to be too strong.
        * Worth looking for earlier versions which think skip tape; maybe slide on corerns
* Alternative filament path
* Camera mount


# Future Mods:
- Hat access filament > short path
    - Filament run-out senseor
- Fan for fumes and bed heting.
- Privacy for rear of chamber
- Protector behind screen?
- Magentic side mounts?
- Shorter HAT to fit in cube
- Unsure: Filament runout sensor
- Cam Locks > Larger hex wrench??. Maybe better options
- I MAY have an expander; if so look at installing (possibly need for LEDs):
    - https://github.com/Lzhikai/SIBOOR-Voron-0.2/blob/main/expander/README.md

# Useful Ideas for storing tools:
* Container hold set of smaller wrench; ideally rotatable like one of the screwdrivers I have.
  * MAYBE want a flat cotiner; tbc
* Something to store the hex driver sets I have
* Something to hold collection of alan keys; sort between printers.
* Something to hold collection of flat cheapper spanners; sort between printers

# Consider Buying Addons
* Alternative beds; ensure have something for each type; PLA, ABS, PETG
  * Glass (Tile?)
  * G10/FR4 PCB material as Bed
* INDX looks interesting, expect to fit 4x toolchangers in V0. Can be shared with EnderNG etc. Think LATE 2025 but monitor as closer
  * Especially if can support/requires CAM or USB extension. Can start replacing other toolheads earlier.
* Do up V6 drop-in could be good for replacements (replaced by above) - mini steath burner then dragon burner.
  * Didn't notice a V6 in https://github.com/Lzhikai/SIBOOR-Voron-0.2/tree/main/STL/Toolheads%EF%BC%88%E5%B7%A5%E5%85%B7%E5%A4%B4%EF%BC%89/Hotend_Mounts
* Box Turner AWS - allow filamenet swaps after filament cutter
  * May need filamenet run-out sensors etc
* Consider CAM or USB version to toolhead vs this V0 Umbilical solution - maybe add to ender NG too for more mainline support/shared data.
* Maybe replace Fly-Gemini-V3 to RPI4 and generic with CAM support. Allow mainline klipper??

* Randome Modded V0.2 for ideas:
  * https://forum.vorondesign.com/threads/my-voron-0-2.1587/
