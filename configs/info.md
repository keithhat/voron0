# Klipper config files

I'm still learning klipper so there maybe better ways to backup files.
This has that information with a combination of where to place them.

## Paths

These paths are using the Gemini board FW locations
* /home/fly/printer_data/config/
** printer.cfg is the main one that references everything
** boards/FLY_GEMINI_V3.cfg defines aliases for various pins so can have generic references in other config files
** V0Display.cfg configures the USB display
** fly_macros.cfg defines some gcode macros including the homing functions.
** mainsail.cfg is a simlink to /home/fly/mainsail-config/client.cfg
** fluidd.cfg is a simlink to /home/fly/fluidd-config/client.cfg


### Extras

* The LEDs:
** klipper/klippy/extras/led_effect.py is a simlink to /home/fly/klipper-led_effect/src/led_effect.py
