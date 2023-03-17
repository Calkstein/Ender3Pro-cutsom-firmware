# custom firmware for Ender3Pro with 25 Kalibrationpoints
## flash my prebuild firmware (not recommened because the `NOZZLE_TO_PROBE_OFFSET` is not correct)
- delete all oldfiles from the mircoSD-card and upload the `Ender3Pro.bin`
- insert the mircoSD-card and wait 20 seconds.
- finished
## create your custom firmeware
- download https://github.com/MarlinFirmware/Marlin.git
- optinoal download https://github.com/MarlinFirmware/Configurations/ if you dont have a `Ender3Pro`
- copy the 4 `*.h` files into the `MARLIN-BUGFIX-2.1.X/Marlin/src` folder

### i have edited the following lines
#### Configuration.h
- Comment #define SHOW_CUSTOM_BOOTSCREEN (86)
- Uncomment #define PIDTEMPBED (743)
- Add #define HAS_PIN_27_BOARD (1399)
- Change values from { 0, 0, 0 } to your distance values. For me it was #define NOZZLE_TO_PROBE_OFFSET { -45, -6, -3.1 } (1555)
- Uncomment #define AUTO_BED_LEVELING_BILINEAR (1945)
- Change value from 3 to 5 -> GRID_MAX_POINTS_X 5 (2031)
- Uncomment LCD_BED_LEVELING (2095)
- Uncomment #define Z_SAFE_HOMING (2168)
- Comment #define SDSUPPORT (2538)
- Uncomment #define SLIM_LCD_MENUS (2554)
- Comment #define SPEAKER (2627)
#### Configuration_adv.h
- Uncomment and change value from 500 to 200 -> #define BLTOUCH_DELAY 200 (918)
- Change value from 1 to 10 -> #define BABYSTEP_MULTIPLICATOR_Z 10 (2092)
- Change value from 1 to 10 -> #define BABYSTEP_MULTIPLICATOR_XY 10 (2093)
- Comment #define ARC_SUPPORT (2311)

as `STM32F103RC_creality` builden

## Cura
- open "Settings/Printer/Manage Printers..."
- choose your printer and open "Maschine Settings"
- copy paste `cura_config.txt` in "Start G-code"
- close and finished

you must reslice all your files if you reprint something old

## addons
[camera holder](https://www.thingiverse.com/thing:5211461)

[dual drawer](https://www.thingiverse.com/thing:3416444)

[Extruder Knob](https://www.thingiverse.com/thing:3176144)

[filament guide](https://www.thingiverse.com/thing:4045196)

## Quellen
https://danieldoesmanythings.com/357/configuring-marlin-2-0-for-an-ender-3-pro-and-bltouch/

https://reprap.org/forum/read.php?415,880766
