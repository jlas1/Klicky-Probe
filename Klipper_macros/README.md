# Klipper macros

These macros are  based on the great Annex magprobe dockable probe macros "#Originally developed by Mental, modified for better use on K-series printers by RyanG and Trails", kudos to them.
That macro as since evolved into a klipper plugin that currently is pending inclusion in klipper, more information [here](https://github.com/Annex-Engineering/Quickdraw_Probe/tree/main/Klipper_Macros)

Would alse like to thank the Voron discord community and VoronDesign for all the work, suggestions and support that they have given to improve on the macros.

## Updating from an earlier version

While you should read these instructions to the end, as the necessary helper functions are now split on different files and it's better explained below, as a current user of the klicky macros, it's easier to configure.

The first macro on the old klicky-probe.cfg contained all the necessary variables, you should the values you changed one by one to the new klicky-variables.cfg, the most important are these ones:

```python
# if you do not have any of these variables, read the explanation on klicky-variables.cfg and the setup of the macros on your respective printer, this is a quick start quide
variable_enable_z_hop           # set this to false for beds that fall significantly under gravity (almost to Z max)
variable_max_bed_y              # bed max y size
variable_max_bed_x              # bed max x size

variable_z_endstop_x            # copy this value over your old file
variable_z_endstop_y            # copy this value over your old file

variable_docklocation_[x,y,z]   # copy this value over your old file
Variable_dockmove_[x,y,z]       # use 40,0,0 it's the old default
Variable_attachmove_[x,y,z]     # use 0,30,0 it's the old default
```

Now if you use auto-z calibration, you also should copy z-calibration.cfg to klicky-z-calibration.cfg and remove the z-calibration.cfg include in printer.cfg.



## New installation

The macros are currently separated by function, there is klicky-probe.cfg that should include the remaining files, this both keeps klipper's printer.cfg cleaner and allow for backward compatibility.

The remaining files are the klicky-macros.cfg that stores all the general macros (like the dock and attach macros, this file is required on all the printers), the klicky-variables.cfg where it's necessary to configure the dock location and do other printer specific configurations and the klipper helper files for specific functions.

The helper files work by expanding the standard klipper function with a attach and dock command, so that you can use all the klipper commands without the need to manually attach and dock the printer.

Right now the macros are divided in multiple files, that way it is much easier to upgrade, configure and maintain

| File                             |        v2.4        |        v1.8        |       Legacy       |      Trident       |         v0         |       Tiny-M       |      V-core3       | MercuryOne         |
| -------------------------------- | :----------------: | :----------------: | :----------------: | :----------------: | :----------------: | :----------------: | :----------------: | ------------------ |
| klicky-probe.cfg                 | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| klick-variables.cfg              | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| klicky-bed-mesh-calibrate.cfg    | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| Klicky-quad-gantry-level.cfg     | :heavy_check_mark: |        :x:         |        :x:         |        :x:         |        :x:         |        :x:         |        :x:         | :x:                |
| Klicky-screws-tilt-calculate.cfg |        :x:         | :heavy_check_mark: | :heavy_check_mark: |        :x:         | :heavy_check_mark: | :heavy_check_mark: |        :x:         | :grey_question:    |
| klicky-z-tilt-adjust.cfg         |        :x:         | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |        :x:         |        :x:         | :heavy_check_mark: | :heavy_check_mark: |



* klicky-probe.cfg (includes all the necessary files in klipper)
* klick-variables.cfg, stores all the Klicky variables, printer specific, should not be necessary to update very often
* klicky-bed-mesh-calibrate.cfg, bed mesh helper scripts, assumes bed mesh is already configured, includes a commented example, further help on setup [here](https://www.klipper3d.org/Bed_Mesh.html#bed-mesh)
* Klicky-quad-gantry-level.cfg, Quad Gantry Level helper script, allows on machines with four Z independent motors to level the bed automatically, assumes QGL is already configured (it's used on a V2.4 to level the gantry relative to the bed), further help [here](https://www.klipper3d.org/Config_Reference.html?h=quad#quad_gantry_level)
* Klicky-screws-tilt-calculate.cfg, screws tilt adjust helper script, knowing where the bed screws are, it will assist in leveling the bed by calculating on the number of times each screw should be rotated, assumes that the configuration is already defined, further help on setup [here](https://www.klipper3d.org/Manual_Level.html#adjusting-bed-leveling-screws-using-the-bed-probe)
* klicky-z-tilt-adjust.cfg, Z tilt adjust helper script, allows on machines with two or three Z independent motors to level the bed automatically, assumes that the configuration is already defined, further help on setup [here](https://www.klipper3d.org/Config_Reference.html?h=z_tilt#z_tilt)
* klicky-specific.cfg, place to put other configurations specific to your printer, like probe or bed mesh klipper configuration

Some printers, like the Voron v0 or Tiny-M don't have the probe as a standard configuration, so in those printers documentation there are extra klipper configurations that you need to use in order to configure the actual probe.

## printer.cfg configuration 

Download the appropriate files (or the zip containing them all and delete the ones that are not relevant) and upload it to your klipper Config folder.

```
cd ~/klipper_config/
wget https://raw.githubusercontent.com/jlas1/Klicky-Probe/main/Klipper_macros/Klipper_macros.zip
unzip Klipper_macros.zip
```

Check the klicky-probe.cfg, remove or comment the macros that are not required for your printer or that you do not want to implement.
Edit klicky-variables.cfg (there are printers specific recommendations on the printer configuration page) for klicky to operate properly.

There are some configurations that need to be checked, otherwise your will run into **out of range** problems, that is by design.

Open your printer.cfg file, comment out *safe_z_home* or *homing_override*, if you have them (the macros will take care of homing) and add the following line before the "Macros" Section.

`[include klicky-probe.cfg]`

It should look like this:

```
#####################################################################
# 	Macros
#####################################################################
[include klicky-probe.cfg]
```

You now need to configure the probe pin, that is printer specific, and the details are on your printer configuration guide.

Regarding you print start and end macros, with the helper scripts implemented, they do not need to be changed.

If however you would like to reduce the times that the toolhead attaches and docks the probe, you can use Attach_Probe_Lock that prevents the probe to be docked after an operation that normally would dock the probe.

**BEWARE that the probe may hit the bed depending on what you are doing**.

When you don't need the probe attached anymore, run Dock_Probe_Unlock to dock and unlock the probe.

## Pre and Post macros for dock operations

If your setup requires a custom move, a macro to be called before attaching and docking, there are two macros **\_DeployDock** and **\_RetractDock** that are executed (if they are configured) when it's required for the dock to be ready for docking and attachment operations.

## XY Sensorless homing 

If you are using sensorless homing, and have your own X and/or Y homing macros, you can use override the klicky macros behavior with your very own _HOME_X and _HOME_Y macros.

If they exist on your klipper configuration, klicky macro will use them instead of the default G28 commands.

## Advanced users

**Beware going forward, you will leave the safety that the macros provide**

I recognize that some users are very technical and may want to write custom macros, so here are the only commands that you need to  attach and dock the probe, without any fail safes or checks.

### Probe attach commands

```python
# Probe entry location
G0 X{docklocation_x|int - attachmove_x|int - attachmove2_x|int} Y{docklocation_y|int - attachmove_y|int - attachmove2_y} F{travel_feedrate}
# Attach probe
G0 X{docklocation_x|int - attachmove2_x|int} Y{docklocation_y|int - attachmove2_y} F{travel_feedrate}
G0 X{docklocation_x} Y{docklocation_y} F{dock_feedrate}
# Probe exit location
G0 X{docklocation_x|int - attachmove_x|int} Y{docklocation_y|int - attachmove_y|int} F{release_feedrate}
```

### Probe dock commands

```python
# Probe entry location
G0 X{docklocation_x|int - attachmove_x|int} Y{docklocation_y|int - attachmove_y|int} F{travel_feedrate}
# Drop Probe to Probe location
G0 X{docklocation_x} Y{docklocation_y} F{dock_feedrate}
# Probe decoupling
G0 X{docklocation_x|int + dockmove_x|int} Y{docklocation_y|int + dockmove_y|int} F{release_feedrate}
G0 X{docklocation_x|int + dockmove_x|int - attachmove_x|int} Y{docklocation_y|int + dockmove_y|int - attachmove_y|int} F{release_feedrate}
```

The typical variables values are:

variable_travel_speed:          100    # how fast all other travel moves will be performed when running these macros
variable_dock_speed:             50    # how fast should the toolhead move when docking the probe for the final movement
variable_release_speed:         75    # how fast should the toolhead move to release the hold of the magnets after docking
variable_docklocation_x:                 # X Dock position
variable_docklocation_y:                 # Y Dock position
#Dock move (if the dock is mounted on the back extrusion, these values can be left untouched)
Variable_dockmove_x:              0    # Final toolhead movement to release
Variable_dockmove_y:            40    # the probe on the dock
Variable_dockmove_z:              0    # (can be negative)
#Attach move (if the dock is mounted on the back extrusion, these values can be left untouched)
Variable_attachmove_x:          30    # Final toolhead movement to Dock
Variable_attachmove_y:            0    # the probe on the dock
Variable_attachmove_z:            0    # (can be negative)

Variable_attachmove2_x:          0    # intermediate toolhead movement to attach
Variable_attachmove2_y:          0    # the probe on the dock (can be negative)
Variable_attachmove2_z:          0    # (to be used as a last move before attaching the probe, suitable for Euclid)

**Again, be advised that these will not raize the bed to avoid hitting it, won't check if the probe is docked or attached. USE EXTREME CAUTION**
