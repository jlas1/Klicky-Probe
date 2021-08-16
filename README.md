# Klicky-Probe
Microswitch probe with magnetic attachment, primarily aimed at CoreXY 3d printers with a focus on the Voron printers, should work on other printers with the variable mount.

The objectives for this project are:
- drop in replacement for Omron TL-Q5MC2 or PL-08N2 (you don't need to replace the toolhead)
- easier and faster to build than similiar probe types
  - does not require soldering
  - fixed probe dock mount (for the printers that are supported), less variables to adjust
- be able to detect all the print surfaces
- be as close to the hotend tip as possible
- high repetitive and accurate probes
- less temperature variations
- no melting of its parts
- cheap to built

Updated instructions provided by StefanRaatz (robbstech V2.663#9945 on Voron Discord)

It can also be used with the new [automatic Z calibration](https://github.com/protoloft/klipper_z_calibration) Klipper plugin to effectively calculate the Z offset from the probe and from the Z-Endstop.

The inspiration for the Klicky-Probe comes from the [Annex magprobe, now renamed to Quickdraw](https://github.com/Annex-Engineering/Quickdraw_Probe) and the [Euclid probe](https://github.com/nionio6915/Euclid_Probe), it uses some concepts from each of the projects.

![Klicky Probe image](Photos/Klicky_Probe.png)





# Probe Accuracy

The probe accuracy output is something like this:
probe accuracy results: maximum 6.430000, minimum 6.426250, range 0.003750, average 6.428750, median 6.428750, standard deviation 0.000791



# Print Settings

There are no need for supports, recommended settings are 4 perimeters/top/bottom, 13% infill.

![](./Photos/Klicky_Probe_recommended_printing_orientation.jpg)

# Mounting Options
The probe dock is mounted on the gantry, allowing it to be use as a Z-Endstop if desired (I use it that way).

There are three gantry extrusion mounts possible:
- one fixed to be used on the Voron V2.4 or V1.8 AB with MGN12 or MGN9
<img src="Photos/Fixed_mount_complete.jpg" width="100">
- one that has some variance for other toolheads
<img src="Photos/Variable_mount_complete.jpg" width="100">
- one fixed sidemount dock to allow a purge/scrub bucket on the left side of the bed
<img src="Photos/Fixed_sidemount_complete.jpg" width="100">

The fixed gantry extrusion mounts have been confirmed to work on the Voron V2.4 and V1.8

# Bill of Materials (BOM)

Tools:

- 1.5mm Drill 
- Multimeter to check for Continuity 
- Super Glue
- Soldering Iron for the heat inserts

Probe BOM:

- 1x microswitch (the omron D2F-5 or D2F-5L (removing the lever) is recommended)
- 2x M2x10 mm self tapping
- 4x 6 mm x 3 mm magnets

AB mount BOM:

- 3x 6 mm x 3 mm magnets
- 2x M3x8 mm SHC Screws
- 2 x 10cm 20AWG cable to connect the Klicky-Probe to the Mircofit Terminal

Probe Dock:

- 1x 6 mm x 3 mm magnets
- 2x M3x20 mm

Fixed Dock mount:

- 2x M3 threaded insert M3x5x4
- 2x M5x10 mm
- 2x M5 t-nut or equivalent

or 

variable Dock mount:

- 10x M3 threaded insert M3x5x4
- 8x M3x8 mm
- 2x M5x10 mm
- 2x M5 t-nut or equivalent



<img src="./Photos/All_Klicky_probe_components.jpg" width="600" />



I will add more detail to this repository as we go along.



# Assembly

## Step 1 - Dock mount and Probe Dock assembly (fixed Dock mount)

- [ ] 2x M3 threaded insert M3x5x4
- [ ] 2x M5x10 mm
- [ ] 2x M5 t-nut or equivalent

Install your heat set threaded inserts like you did within your Voron build. 

<img src=".\Photos\DockMount.jpg" style="zoom: 15%;" />



Install the magnet in the Probe dock and screw it onto the Dock mount with the two M3x20mm SHC screws.

Secure the magnet with a dab of super glue.

<img src=".\Photos\DockMountandProbeMount.jpg" alt="20210802_122818" style="zoom:15%;" />

Mount the Probe Dock to the back rail of your gantry with the two M5x10 and the two roll in nuts.

## Step 2: Probe Assembly

For the probe assembly you need the following parts:

- [ ] 1x microswitch (the omron D2F-5 or D2F-5L (removing the lever) is recommended)
- [ ] 2x M2x10 mm self tapping
- [ ] 4x 6 mm x 3 mm magnets
- [ ] 1.5mm Drill 
- [ ] Multimeter to check for Continuity 
- [ ] Super Glue

<img src="./Photos/probe_components.jpg" width="600" />

Maybe you need to clear the holes for the microswitch, a 1.5mm drill bit should work fine.

Install the microswitch so that the arrow on the probe body is pointing to the little switch.

<img src=".\Photos\Probe_MStoArrow_alignment.jpg" width="600px;" />



<img src="./Photos/probe_install.jpg" width="600" />

Then take your self tapping screws and screw the microswitch in place.

<img src="./Photos/Probe_topside.jpg" width="600" />

You want to install the magnets in the way that the two, which are connected to the microswitch, have the same polarity  The 3rd magnet should have the inverse polarity.

However there is the possibility that the magnets will demagnetize over time due to the alternating magnetic fields thay may result in a slow but sure demagnetization of the magnets, the magnets are so strong that may take a long time to show the effects of demagnetization YMMV.

There is no need for soldering, the probe microswitch connectors are press-fit on the magnets.

<img src="./Photos/probe_v1_underside.jpg" width="600" />

Don't forget to install the magnet which holds the probe to the probe dock.

Secure the magnets with some super glue.

As the last step of the probe assembly check if you have continuity between these two magnets

<img src="./Photos/probe_v1_underside_marked_magnets.jpg" width="600" />

If you have a normally open switch, then no current should flow, so no continuity. When you press the switch you should have continuity. When you have a normally closed switch then the behavior is the other way around.



## Step 3: AB Mount Assembly

For the AB Mount assembly you need the following parts

- [ ] 3x 6 mm x 3 mm magnets
- [ ] 2 x 10cm 20AWG cable to connect the Klicky-Probe to the Mircofit Terminal
- [ ] Multimeter to check for Continuity 
- [ ] Super Glue


The AB mount wires are also connected with pressure from the magnets, you can use the probe magnets as a template to insert the AB mount magnets, it is easier that way to don't insert the magnets the wrong way.
<p float="left">
  <img src="./Photos/AB_Mount_wiring_1.jpg" width="150" />
  <img src="./Photos/AB_Mount_wiring_2.jpg" width="150" />
  <img src="./Photos/AB_Mount_wiring_3.jpg" width="150" />
  <img src="./Photos/AB_Mount_wiring_4.jpg" width="150" />
  <img src="./Photos/AB_Mount_wiring_complete.jpg" width="150" /> 
</p>


You will not lose Y travel on any configuration in the tests that were done.

It is also recommended to glue the magnets in place, superglue is good.

After everything is assembled let's check again for continuity.

<img src="./Photos/ABMountCheckforContiuity.jpg" width="600px;" />

## Step 4: AB Mount installation and wiring

For the installation you need the following parts:

- [ ] 2x M3x8 mm SHC Screws



<img src="./Photos/ABMountInstalled.jpg" width="600px;" />

Connect the two wires from the Klicky-Probe to the GND and Signal of the Y-Endstop.

Then plug the probe into the Y-Endstop Port in your Z-MCU (should be z:1.28)

![SKR pinout](./Photos/SKR-V1.4-pinout.jpg)



## Assembled Klicky Probe

![Assembled Klicky Probe](./Photos/Voron_V2.4_300mm_back.jpg)



## Step 5: Klipper configuration Dock/Undock Macro
You will need to add macros to klipper to be able to dock and undock the probe as necessary to do the Endstop (if necessary) and Quad Gantry Level, it is in the Klipper Macro directory.

The macro is based on a version provided by the user garrettwp on Discord, many thanks to him.
I have tweaked it a lot.
It is also originally  based on the great Annex magnet dockable probe macros "#Originally developed by Mental, modified for better use on K-series printers by RyanG and Trails" and can be found [here](https://github.com/Annex-Engineering/Annex-Engineering_Other_Printer_Mods/blob/master/All_Printers/Microswitch_Probe/Klipper_Macros/dockable_probe_macros.cfg)

Would also like to thank the Voron discord community and VoronDesign for all the work that was and still is being made to maintain the Voron ecosystem.



### Klipper Configuration and Probe offset

Download the appropriate klicky-probe.cfg and upload it to your Klipper Config folder.

Then open your printer.cfg file and add the following line before the "Macros" Section.

`[include klicky-probe.cfg]`

Within your printer.cfg file search for the `[probe]` section and change the pin assignment to the new one `z:P1.28` or the ID where you connected your Klicky-Probe to. Depending on your switch you may need to add a `!` to invert that pin (normally open vs. normally closed).

Within the `[probe]` section also adjust your probe offset to the following values.

You need to set the probe offset within your `printer.cfg`  

There is now a arrow on the probe telling you where should the switch pole be to have the correct offset.
The probe offsets are:

`z_offset = 6.42`

`x_offset: 0 `

`y_offset: 19.75`

### Z-Endstop and Probe configuration

If you want to use the Klicky-Probe as your Z-Endstop, you need to change the `endstop_pin:` under the `[stepper_z]` section to `probe:z_virtual_endstop` . Just comment out the old one and add a new line `endstop_pin: probe:z_virtual_endstop`. 

You don't need to change anything else leave it as it is, so you can easily revert back to the original setup.



### Adjust Probe Pickup Position

One of the last things we need to do is to adjust the probe pickup position.

For this we need to home the x and y axis of our printer then attach manually the probe to the AB-Mount.

Now juggl the probe to the probe dock and move it so far to the back that the probe docks, note done the X- and Y-Positions.

Open you `klicky-probe.cfg` and find the `#dock location` section and edit the following two line

`variable_docklocation_x:`

`variable_docklocation_y:`

If you have your Dock mounted to the bed then you need to adjust the `variable_docklocation_z:`, too.

### Use Klicky-Probe with/without Z-Endstop switch (Voron)

If you want to use the Z-Endstop switch of the Voron to calculate the Z-Offset we the new [automatic Z calibration](https://github.com/protoloft/klipper_z_calibration) you also need to set the following, two lines, this is the Z-Endstop Location from your `printer.cfg`.

`variable_z_endstop_x:`     

`variable_z_endstop_y:`

If you want to use your Klicky-Probe as a Z-Endstop, then you need to set the two lines to, `0`.

`variable_z_endstop_x:     0`

`variable_z_endstop_y:     0`

### Calibrate Nozzle offset (pending a permanent solution)

There is a know bug within the macro which won't let you save the offset after the probe is undocked.

[Probe_Calibrate Error · Issue #8 · jlas1/Klicky-Probe (github.com)](https://github.com/jlas1/Klicky-Probe/issues/8)

Find the `PROBE_CALIBRATE` section in your `klicky-probe.cfg`and comment out the following two lines

`#Dock_Probe`

`#RESTORE_GCODE_STATE NAME=_original_nozzle_location MOVE=1 MOVE_SPEED={St}`

Then move your printhead to the middle of your build plate and run `PROBE_CALIBRATE`

After the script finished the probe accuracy test it will move the print head by the offset specified within the `printer.cfg`

Now you need to manually remove the Klicky-Probe from the printhead and proceed as normal.



Congratulations, your done :).

Enjoy your Klicky Probe!



# Dock and undock video

https://user-images.githubusercontent.com/16675722/122302371-eb9c4e00-cef9-11eb-91d3-3aded131bae0.mp4

It is working very well, if you decide to use it, give me feedback, either here, or on discord, my discord user is JosAr#0517.
This mod is also on [VoronUsers repository](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/JosAr/Klicky-Probe).

By standing on the shoulders of giants, lets see if we can see further.
