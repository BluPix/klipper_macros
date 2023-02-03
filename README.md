# klipper_macros fort Voron Trident/V2.4

## Start G-Code:
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
M109 S0 ; uncomment to remove set&wait temp gcode added automatically after this start gcode
print_start EXTRUDER=[first_layer_temperature] BED=[first_layer_bed_temperature] CHAMBER=[chamber_temperature]
```
