# Klipper Macros for Voron Trident/V2/V0
WORK IN PROGRESS

These are my macros for my Voron V0.1 and Trident, but should work on any enclosed 3d printer like the Voron V2.4.
Functions:
* I don't have to change anything, the same macro works on both printers. 
* Filament can be changed on a cold printer, no need to preheat the nozzle.
* Klicky probe does not do unnecessary docking/undocking during start of print. 
* At the beginning of the print the printer waits until the chamber is hot and measures it with a hotend thermistor, no extra thermistor needed.
* I have a table translating the filament name to the desired chamber temperature before printing starts, so even slicers like PrusaSlicer, Cura, BambuStudio that don't allow you to set the chamber temperature can still comfortably print ABS without the user having to wait for the printer to preheat.
* print_start can recognize most of the default variable names found in the default printer profiles in various Slicers, you lose the chamber preheating but it's a bit more foolproof.
* At the end of a print, the printer waits for the bed to cool before it finishes printing. If you use Mobileraker and https://github.com/Clon1998/mobileraker_companion , your phone only gets notifications when it makes sense to go to the printer to take the print off.

## Start G-code:
### For Ultimaker Cura:
```
print_start BED={material_bed_temperature} HOTEND={material_print_temperature} FILAMENT={material_type}
```

### For PrusaSlicer:
```
M190 S0
M109 S0
print_start EXTRUDER=[first_layer_temperature[initial_tool]] BED=[first_layer_bed_temperature] FILAMENT={filament_type[0]}
```

### For SuperSlicer:
```
M190 S0
M109 S0
print_start EXTRUDER=[first_layer_temperature] BED=[first_layer_bed_temperature] CHAMBER=[chamber_temperature]
```
### For BambuStudio:
```
M190 S0
M104 S0
print_start EXTRUDER=[nozzle_temperature_initial_layer] BED=[bed_temperature_initial_layer_single] FILAMENT={filament_type[0]} 
```
### For BambuStudio-SoftFever:
```
M190 S0
M104 S0
print_start EXTRUDER=[nozzle_temperature_initial_layer] BED=[bed_temperature_initial_layer_single] CHAMBER=[chamber_temperature] 
```


## End G-code:
```
print_end 
```
