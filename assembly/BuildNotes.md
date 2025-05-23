# Mechanical Assembly Build Notes
These are originally notes I took during building.
0 Keiths Notes.txt should be a consise delta to the readme and assembly PDF>

After this the ../future.md

# Overview

These are my assembly notes for: Voron 0.2 R1 (2023 June) by Siboor
  - This had SIBOOR upgrades not part of official Voron, so was called SUBOOR v0.2 R1 (Aug 2023)
  - The kit I had was:
    - Included printed ABS parts (main black, highlights red)
    - Included a Fly Gemini v3.0 mainboard
      - Includes RPI functionality on single board
    - Had the Kirigami bed
    - Upgraded to the Dragon HF Hotend (not TZ-v6-2.0 HoteEnd)
    - Silicon heater 75W (was 60W)
    - Mini Stealthburner with Hot end umbilical toolhead
    - High Temperature Resistant PC Panel
  - TBC RGB indicator

## Specs
- Built Weight: < 7kg
- External Dimensions: 240x240x380 (in mm) 
    - Note: This CANNOT fit in ikea cube even with top-hat removed. The hotend/tubes are too high.
- Printing Size: 120x120x120 (in mm)

## Purchase notes
- I bought from Aliexpress not siboor store (no reason, saw on Aliexpress).
  - I did consider CNC but kept with printed ABS incase wanted to mod later.
    - At time, think some ABS still had to be used ie 1 fut.
  - Went black and red (expect most common); didn't notice option for different extrusions at time of ordering.
    - Kit had note saying: Sunlu red + sublu black
- Was 857.29 plus P&H > 943.02 (at 23-Feb-2023)

## Build Time
- I wasn't rushing and took a while to find deltas from my kit to officail documentation
- Siboor store said 3 days; have seen 30hr estimate.
- I found about a week before powering on doing a few hours most nights and several on weekends.

## References
* [1] README with deltas to official: https://github.com/Lzhikai/SIBOOR-Voron-0.2/blob/main/supplementary/README.md
* [2] Official 0.2: https://github.com/VoronDesign/Voron-0/blob/Voron0.2/Manuals/VORON_V0.2_Assembly_Manual.pdf
* [3] Motors and Feet: https://github.com/Lzhikai/SIBOOR-Voron-0.2/blob/main/supplementary/SIBOOR%20V0.2%20Supplementary%20Manual.pdf
    * For CNC parts (I used ABS)
* [4] Wiring / Motors: https://github.com/Lzhikai/SIBOOR-Voron-0.2/blob/main/supplementary/SIBOOR0.2-supplementary.pdf
* [5] https://github.com/Lzhikai/SIBOOR-Voron-0.2/blob/main/supplementary/SIBOOR%200.2%20R0%20Upgrade%20R1%20Guide.pdf
* [6] Bom: https://github.com/Lzhikai/SIBOOR-Voron-0.2/blob/main/BOM.md
* Root Project from QR Code: https://github.com/Lzhikai/siboor-voron/tree/main/Voron-0.2
* [7] Sourcing guide including Lubricates https://vorondesign.com/sourcing_guide

* Videos:
  * [8] 0.2 Siboor kit build video: https://www.youtube.com/watch?v=zX7Bgzhw0OM&ab_channel=KanduWorkshop
  * [9] 0.2 build video series: https://www.youtube.com/watch?v=-NzwDm4eyQc&ab_channel=Greg%27sMakerCorner
  * [10] 0.2 build series: https://www.youtube.com/watch?v=lKliWNphWic&list=PLiiEyXLrqIBSOPptPnDcVc-NQQFDGW8lQ&index=7&ab_channel=ModBotArmy
  * [11] 0.1 Bed upgrade (webpage): https://3dpandme.com/2022/03/12/funssor-kirigami-bed-upgrade-for-the-voron-0-1/

# Extras I bought
* Isopropyl alchohol
* WD40 White Lithium Greece (spray can)
    * I used as lubricate for linear rails and screw
* Permatex White Lithium Grease - 80345 for bearings
    * For print head bearings
* Locktight Blue for grub screws
* Super glue for print head nut
    * I had 2 part 5min eproxy
* Cable cutter and stripper
* JST XH connector tool - at least for hotend to Umbiligal PCB
* Optional:
    * Cable management stickies


# Notes:
- Parts:
  - From (1):
    - Extrusion A=B (All tapped)
    - C=H
  - The Kirigami bed deprecates:
    - 100mm "F Extrusion" x2 (end M3)
    - 100mm "G Extrusion" x1 (27.5x2 same face)
    - ~ page 38 (note says to skip to page 43)
  - There are separate extrusions in the kit for the lid
- I think these were omitted below so including here to ensure captured
  - Alignment tools ~ 19min of https://www.youtube.com/watch?v=zX7Bgzhw0OM&list=WL&index=6&ab_channel=KanduWorkshop
  - Motor B/X is top left  when viewed from the front
  - Motor A/Y is top right when viewed from the front
  - I didn't sand axel so gears more free (~p160)
  - Something about [4] p9
    - I didn't do this, at least not initially. It also required splicing both in parallel
- Clarification
  - p21 
    - These were leavered arms in first tray
  - p36 'Frame - Component Prep' this is all bed tray
    - MOD: Have Kirigami which mentions skip (on p38) but is here
      - These two parts are part of metal tray for Kirigami.
      - A Kirigami v0 install video is at: https://www.youtube.com/watch?v=eOnNvhircn8&ab_channel=MapleLeafMakers
        - I have v0.2 which has some mods coming up:
      - The part on p36 is deprecated:
        - It WAS 'VORON v0.0_v0.1_legacy_chain_mount.stl
'https://github.com/christophmuellerorg/voron_0_kirigami_bed/blob/master/STL/VORON%20v0.0_v0.1_legacy_chain_mount.stl with install guidance on at 7:27
        - I had BLACK 'Voron_0.2_stealth_chain_mount.stl'  https://github.com/christophmuellerorg/voron_0_kirigami_bed
        - This is installed like: https://github.com/christophmuellerorg/voron_0_kirigami_bed/blob/master/Images/stealth_beta.png
        - NB: My dragchain ends were same, the v0.1 mentions one goes BOTH ways and use that on tray
      - There is another BLACK part which is shown in red with a Z on https://github.com/christophmuellerorg/voron_0_kirigami_bed/blob/master/Images/stealth_beta.png
        - This needed 1x M3 heat insert and 4x M3x6 BHCS
      - Keep the lead screw with anti-back lash mount attached until mouting z-axis motor.
          - The part shown in RED with the Z was BLACK in my kit
          - Mount with the horizontal part at top (I originally did bottom and notied at p92 - leasily swapped)
        - Electronics used 3x6
      - Returns to manual after attached p47 (covered by https://github.com/christophmuellerorg/voron_0_kirigami_bed/blob/master/Images/stealth_beta.png)

  - p49-51; have an update to z endmount stops in 0.2 R1 upgrade
      - this is shown in (5) as z endstop mount; the red one with frowny eye-brows
      - uses 2x M2x10 self tapping from switch outside. Red switch on RHS from front
      - then tried M3x8 BHCS into frame
    - https://www.youtube.com/watch?v=zX7Bgzhw0OM&list=WL&index=4&ab_channel=KanduWorkshop @3:37 shows a red part;

  - p53; I added extra 2 nuts to allow for 5VPSU mounting in fuure if required (kit has all in 1 board)

  - p70; shims M3x6x0.5
    Spacer is red ~10mm

  - 81 used lock-tight on grub screws

  - 92 for Kirigami skip this; will mount with lead screws from motor to tray in p104
    - From TODO the mount should be attached to tray as in https://github.com/christophmuellerorg/voron_0_kirigami_bed/blob/master/Images/stl_mounting.png 
    - Kept the lead screw attachment connected to the lead screw but if unattached wait until p104 (as will lubricate)
      - This is consistent with:
        - 0.1 tray upgrade: https://3dpandme.com/2022/03/12/funssor-kirigami-bed-upgrade-for-the-voron-0-1/
        - https://www.youtube.com/watch?v=zX7Bgzhw0OM&list=WL&index=4&ab_channel=KanduWorkshop at 4:21

  - p73 + p79; don't over tighten these bolds into the motor at this stage
    - The belt tensioner will shift them later (p135).

  - p95 NB 4xM3 nuts on back right virtical, confirm at p97
  - p105 for Kirigami bed, this also needed screw nut attached to bed
    - For threaded rod lubrication I used white lithium greace, same as linear rails (WD40)
       - If need to reattach have tallest part facing up:
            - See https://www.youtube.com/shorts/Y4ScC2dLlLY (linked from manual p92)
      - To attach screw nut to Kirigami bed I used M3x12 (to match p92)

  - p113 suggest not tightening nuts to attach linear rail so it is centerd (p118)

  - p121; I added another 3 nuts to each side to mount carry handles as a future mode
    - eg: https://www.printables.com/model/550363-voron-02-carrying-handles/files
    - I probably would have preferred it on lower handle but thought about it too late.

  - p129; the kit allowed 102x3 lengths so I cut 3 to same length to have a spare.
      - I fed each part through the x-carriage slot temporarily to 'zipper' together to check teath same
      - Potentially off-by-one but will tune to 110Hz to ensure ok (p135)

  - p130
    - My belt tensions didn't move, which traced to shims bining into ABS when attached motors in on p73 + p79
      - Luckily I had some larger M3 washers that fit in the slot without being bound so could be attached.
    - Have suggestion to temporarily mount x-carriage to linear rail with M2x6 (p134) while threading belt
      - See https://www.youtube.com/watch?v=_PidL01HJL8

  - p131 count teath is useful but will be trimming belts flush later (p136) to allow toolhead to be attached

  - p134; I droped the thread lock into a hole and pushed with end of pliers (filament was too thick), ensure wipe off before attaching ABS x-carriage.

  - p135 I used 'pano tuner'; hard to set exact; got 123 with logic will quickly loosen.

  - p145 I WANTED to use the left over silcon spaces I had rather than yellow spings
    - However extended beyond printer and front over heat pad so would need to cut down to fit. Potential in future but for now keep yellow spings
    - The M3x40 screws are very long but confirmed do not hit when bed is at the bottom

  - p146; will wire kirigami bed header later. For now tuck out of the way under the heater pad

  - p147 for Kirigami v2 bed dragchain was already assembed so can skip

  - p151 can skip the 'standoff' heatset inserts. There is an aluminium replacement part now
    - This is installed at p180 (on bsvk of screws holding extruder motor)

  - p153 didn't notce a built in support

  - p154 bottom bearing may have already mounted, possibly friction fit.
    - I could remove by placing in p155 part, or some needle nose pliers.
    - The design should allow these to be easily align for gear to vertically align with gear gripping the filament.
      - Mine was originally too tight (could fit with force), even with some sanding.
        - Further sanding was required to assist in self aligning.
        - The other gear and grub thread needs to go past this later (p158)
        - Add axel into drill to help sanding maybe 10sec using 80 grit paper I had.
          - eg 58:24 https://www.youtube.com/watch?v=3Z6UbegCPGA&list=PLiiEyXLrqIBSOPptPnDcVc-NQQFDGW8lQ
          - cleaned after with some isopropyl alchol
    - Not no 3d printed space but was already correct length
      - Apparently if too long can mount and bind later in usage.

  - p155 I used 2part eproxy resin (5min) to glue nut; then held down with temp screw
    - avoid thread locker as can sometimes impact ABS

  - p157 I tried but stopped, in hindsight it would have worked:
    - Added 1-2xM3 shims to Hinge Pin to assist it but need to ensure hight doesn't impact clearance during p160
    - These were spare from washers added to tensioning arm previously

  - p158 if the gear had trouble fitting onto shaft further sand.
    - Ideally bearings allow axel to freely move up and down, and gear can move within cutout section.
    - I did NOT lock tight this grub screw as only loosly fitted atm. It is in the flat section of shaft

  - p160 I found best to add shims to top and bottom to keep axel spaced, then when gear added can remove. The gear and filament is what self senters.

  - p165 had 2 sets of fans; blower fans both 3010 24V 0.1A
    - blower fans as those without exposed fan
    - they needed a plastic clip removed, but note array first (I transfered with silver marker)
      - See 6:30 of https://www.youtube.com/watch?v=zX7Bgzhw0OM&list=WL&index=4&ab_channel=KanduWorkshop at 4:21
    - Add the hotend fan (p166) - used shorter cable DC24V 0.1A BEFORE right fan (viewed from rear) routing through same channel

  - p169 I removed the tension knob from 162 to get better access but can be worked around
    - This is needed in next step anyway

  - p174 I had a phaetus dragon which mounted with M3x8  SHCS
    - I used some blue capricorn tubing for PTFE (is lower diameter) mainly for looks.
    - There is the jig on p176, I found ~20mm to be the final and was easily to trim a slight excees

  - p177 I gound backet writing had to be to BACK (motor side)
    - The hootend tapered side is to back, and has more poking out at back.
      - See 7:32 of https://www.youtube.com/watch?v=zX7Bgzhw0OM&list=WL&index=4&ab_channel=KanduWorkshop
    - NOT discussed; hotend cartrige and thermister. as at 8:08front fan. Added these before mouting.

  - p180 looks different, more like a man with several cutouts; bottom half same
    - Used all M3x8 (no M3x6); also attached umbilical PCB
    - Added zip ties to arms and routed similar to p182


  - p185
    - See (4) to mount standoffs for mobo before inserting panel.
      - Think (4) panel is upside down to (1)
      - p186 swapped insert so heatsinks on top right
        - Followed 9:50 of https://www.youtube.com/watch?v=zX7Bgzhw0OM&list=WL&index=5&ab_channel=KanduWorkshop
          - I had a long fan cable so no issues of what is mentioned.
    - Notes:
      - Mobo does cover some mounting screws, so removed to swap
      - Remove film before inserting panels
      - 2x Extra screws per panell cannot be accessed so were unnecessary
        - two on side away from ethernet can be added to plastic
    - > Skip to 191

  - p192; added M3x6 screws as well as tape

  - p193 this part needs the 4x heatsets shown on p187

  - p200 > [4] p4-7
    - I wired up Kirigami bed
      - Cable management I added a heatset and M3x12 to attach
    - No light to front of bed yet
      - Believe on wiring diagram but wait until later. Unsure of dragchain spaec too
    - > Returns 205


  - p218 + 219 > Replaced with umbilical PCB and red cable pass through bracket

  - Notes on case parts - have a tab goes along top/bottom to align parts

