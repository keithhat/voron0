This is tracking my ideas for hotends.
There maybe other info at: https://3dprintersforants.com/


Rough plan is:
	- Have a Dragpn HF in Mini Stealth burner.
		- Want a second Hotend for abrasive materials - also handle blocks
		- MAY want additional parts to help with Dragon HF clogs - think had snapped filament cause this at start


Mini StealthBurner - Default Toolhead



Dragon Burner:
	- https://github.com/chirpy2605/voron/tree/main/V0/Dragon_Burner
		- v8 was defined for Voron 0.2
	- Bom (Extracted)
		- FANS:
			- Part Cooling: 2x 4010 24V blower fans
				- Recommended: https://www.aliexpress.com/item/32799324058.html 	AUD 5.05
			- Hotend Cooling: 1x 3010 24V
				- Recommended: https://www.aliexpress.com/item/1005002857100082.html AUD $ 8.78
		- LEDs:
			- 3x LEDs for lgoo and nozzle lights (optional)
				- Can be a mixture of NeoPixels and/or Sequins (nozzle??)
				- Support has been added for either standard Neopixels or Sequins for the nozzle LEDs, Neopixels, Sequins and RainbowBarf for the Logo LED.
				- Links I found:
					- https://www.aliexpress.com/item/1005007646205279.html AUD 1.59 (need to solder/crimp myself)
					- https://www.aliexpress.com/item/1005006046634379.htm AUD 10.59 looks socketed prepared for StealthBurner
		Dragon SF and HF
		Dragon + Volcano (Rapido HF mount)
		Dragonfly BMO
		Dragonfly BMS (7 fin)
		Revo Voron
		Rapido HF
		NF Crazy
		Creality Spider Pro
		Bambu Labs X1C
		TaiChi
		E3D V6 Groove Mount
		Red Lizard K1 Pro (Dragon mount)
		Red Lizard K1 UHF (Rapido HF mount)
		Dragon Ace HF (with spacer use the Rapido HF mount, without spacer use the Dragon Ace HF mount)
		Phaetus NeXt G HF (Dragon mount)
		Phaetus NeXt G UHF (Rapido HF mount)
	- Extruder:
		Extruder support:
		E3D Roto Vitamins (use the Sherpa Mini hotend mount)
		LGX Lite (use the Sherpa Mini hotend mount)
		Sherpa Mini
		Sherpa Micro
		Sailfin/Sharkfin
		Orbiter v1.5
		Orbiter v2
		Vz-HextrudORT (Uses the LGX Lite extruder mount and Sherpa Mini hotend mount)
		Double Folded Ascender
		RoundTrip (Gears from the LGX Lite, TBG Lite, Orbiter v1.5, Orbiter v2)
		Galileo v2 Standalone (G2SA) with specific mounts for Sherpa Mini and Orbiter v2 mount hole configurations
		Wristwatch BMG and G2 use the Orbiter v2 hotend mounts
		Papilio Lite (Paplite) extruder (use Sherpa Mini mount)
	- Probes:
		- SlideSwipe magnetic probe support: https://github.com/chestwood96/SlideSwipe - likley start with: https://github.com/chestwood96/SlideSwipe/blob/master/Alternative_Mounts/FrontCowlingMount/README.md
		- (Un)Klicky Probe support: https://github.com/jlas1/Klicky-Probe/tree/main/Printers/Voron/v0 (also read https://github.com/T4KUUY4/Voron-Stuff/tree/main/KlickyProbeZoffset)
			- https://github.com/jlas1/Klicky-Probe/tree/main/Printers/Voron/v0#integrated-cowling-v01
			- https://github.com/jlas1/Klicky-Probe/tree/main/Probes/KlickyNG
		- ZeroClick probe support: Inspired by Clikcy but for small printers: https://github.com/zruncho3d/ZeroClick
		- Think also Tap and Boop in mounts
	- Mounts:
		- Extruder and PCB Mounts: https://github.com/chirpy2605/voron/tree/main/general/PCB_Mounts
		- Alternative Mounts: Mounts are available
	- Extra:
		- ADXL345 front mount
		- Heatsink thermistor support on most hotend mounts
		- Neopixel support (nozzle and logo)
		- Adafruit Sequin support (nozzle and logo)
		- [Lab4450](Shop - RGB Neopixel Sequins for Voron Mini SB - Lab4450.com) Neopixel Sequin support (nozzle and logo)
			- https://lab4450.com/product/rgb-neopixel-sequins/ EU 2.00
			- https://github.com/julianschill/klipper-led_effect


Noet:
	- Avoid XoL

Want:
	- Dragon HF
	- V6 PZ
	- Orbiter v2.5++

Stetech:
	- Filament Cutter (for AMS)
	- Probe:
		- TAP: https://github.com/chirpy2605/voron/tree/main/general/Alternative_Voron_Mounts/Modified_Mounts/Tap
	- Vooron Revo (ideally with PZ)
		- MAYBE easier to clear clogs;
			- Possibly something else to heatup outside of printer


Future:
	-CAM Bus

