# klipper_macros for Voron Trident/V2.4
These are my macros for my Voron Trident it has a Klicky probe, no Z-enstop, Dragon HF hotend and measures chamber temperature using the hotend thermistor as I don't have a chamber temperature sensor.

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
PRINT_START EXTRUDER=[nozzle_temperature_initial_layer] BED=[bed_temperature_initial_layer_single] FILAMENT={filament_type[0]} 
```
### For BambuStudio-SoftFever:
```
M190 S0
M104 S0
PRINT_START EXTRUDER=[nozzle_temperature_initial_layer] BED=[bed_temperature_initial_layer_single] CHAMBER=[chamber_temperature] 
```


## End G-code:
```
print_end 
```
