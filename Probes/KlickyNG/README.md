# Klicky Probe NG (Next Generation) (or No Glue :-) )
Microswitch probe with magnetic attachment, primarily aimed at CoreXY 3d printers, with enclosed magnets, don't fall, don't need to be glued.

This version has been used on tens (hundreds ?) of machines, so it can be considered functional and safe.
For new setups and due to it's easier assembly i would recommend the KlickyNG over Klicky regular for new builds.

The objectives for this project are:
- drop in replacement for Omron TL-Q5MC2 or PL-08N2 (you don't need to replace the toolhead), replacement of BLtouch probes
- no soldering required
- minimal adjustments required
- be able to detect all the print surfaces
- be as close to the hotend tip as possible
- highly repeatable and accurate probes
- less temperature variations
- no melting of its parts
- reuse spare parts if possible
- no need to use hard to source parts
- no need to glue the magnets

For now this document will only deal with KlickyNG-specific wiring; for all the rest of the configuration, please follow the [main guide](https://github.com/jlas1/Klicky-Probe).

The inspiration for the Klicky Probe comes from the [Quickdraw](https://github.com/Annex-Engineering/Quickdraw_Probe) and the [Euclid probe](https://github.com/nionio6915/Euclid_Probe), it uses some concepts from each of the projects, but with this version, it expands on the concept, as the method that it uses was developed independently. 

Please check the main Klicky repository for all the people that helped this project, for NG, would like to thank (in no specific order) Dustinspeed, Drachenkatze, clee, maz and whoppingpochard.

If you want to donate something regarding this project, use this [link](https://paypal.me/Josar154) or [__Buy me some ABS!__](https://www.buymeacoffee.com/JosAr), thanks

Without further delay, here is the new version with enclosed magnets:
<img src="Photos/overview.jpg" alt="Klicky Probe image" height="350" />

The eyebrows are clee+whoppingpochard's design.

# KlickyNG support

For now, only printers compatible with Voron StealthBurner/AfterBurner are compatible, as the NG mount has changed significantly and needs to be ported to the other mounts.

- [The CAD with all the files](../../CAD)
- [STL Files](./STL)

The arms are compatible with both Klicky and KlickyNG.

There is also [an exploded view](https://youtu.be/mlyU2tHjebo).

## Print Settings

There is no need for supports; recommended settings are 4 perimeters/top/bottom, at least 23% infill. The STL's are already oriented for you, so you only need to send them to the slicer.

![](./Photos/print_orientation.jpG)

## Required parts

|                                                              |                                                              |
| :----------------------------------------------------------: | ------------------------------------------------------------ |
| <img src="./Photos/NG_Probe_Dock.JPG" alt="NG_Probe_Dock" width="200" /><img src="./Photos/NG_2mm_extender.JPG" alt="NG_2mm_extender" width="200"  /> | If you want to reuse your old Klicky dock, it needs to use this setup for the back magnet. It will also be necessary to print the 2mm NG extender, as the dock needs to be 2mm longer. |
| <img src="./Photos/NG_Probe_insert.JPG" alt="NG_Probe_insert" width="200"  /> | Probe Insert, required to hold the switch and the two magnets that make the electrical connection, two versions; one for around 2.75mm (instead of 3mm) height, and one for actual 3mm-height magnets |
| <img src="./Photos/NG_Probe_body.JPG" alt="NG_Probe_body" width="200"  /> | Probe body, required to prevent the two front magnets from escaping the probe, holds the third magnet to help attach the probe to the mount and the back magnet to secure it to the dock. |
| <img src="./Photos/NG_back_mount.JPG" alt="NG_back_mount" width="200"  /> | Mount back, mounts to the AB/SB, holds the third magnet and the wire connections |
| <img src="./Photos/NG_front_mount_3mm.JPG" alt="NG_front_mount_3mm" width="200"  /><img src="./Photos/NG_front_mount.JPG" alt="NG_front_mount" width="200"  /> | Mount front, two versions; one for around 2.75mm (instead of 3mm) height, and one for actual 3mm-height magnets |

## Optional parts

|                                                              |                                                              |
| :----------------------------------------------------------: | ------------------------------------------------------------ |
| <img src="./Photos/probe_helpers.jpg" alt="NG_Probe_Dock" width="300" /> | To help with magnet installation (they can be very powerful and interact with each other before final assembly), you can use these parts, they require 3 more magnets (can be reused). |

# Bill of Materials (BOM)

- 1x microswitch (the Omron D2F-5, or D2F-5L with the lever removed, are recommended, but similar-sized microswitches like D2F-1 and KW10 will also work)
- 30cm of wire, AWG22 or similar
- 5 M2x10mm self-tapping screws
- 8x 6mm diameter x 3mm height magnets (add 3 more if you want to do the magnet helpers)
- 2x M3x18mm/M3x20mm screws

# Build Process

First, assemble the required materials.

<img src="./Photos/material.jpg" alt="material" height="400"  />

## Probe assembly

- Put one magnet on the back groove of KlickyNG_Probe_body, and add another to the matching hole on the KlickyNG_cap_magnet helper.
  <img src="./Photos/step1.jpg" alt="step1" height="300" /> <img src="./Photos/step2.jpg" alt="step2" height="300">
  
- Next, insert two magnets on the front sockets KlickyNG_Probe_body Body. These magnets should have the inverted polarity of the back magnet. After inserting each one, make sure to add the corresponding magnet to the magnet helper, it will help keep the magnets in place during assembly.
  <img src="./Photos/step3.jpg" alt="step3" height="300" />

- Now, place the insert on the body (select either the regular insert or the 3mm one), aligning the magnets and making sure that the front magnets do not move out of place, attach the switch (note the arrow pointing to the switch pin) secure with the M2x10 screws.
  <img src="./Photos/step4.jpg" alt="step4" height="300" /> <img src="./Photos/step5.jpg" alt="step5" height="300" />
  
  
  
- (left to right) insert a magnet on the dock, via the back hole. Then place a magnet on the front of the dock and insert it on the back pocket of the probe, taking care to follow the same magnetic orientation, finally make sure the probe docks properly.
  
  <img src="./Photos/step6.jpg" alt="step6" height="300"/> <img src="./Photos/step7.jpg" alt="step7" height="300"/> <img src="./Photos/step8.jpg" alt="step8" height="300"/>

## AB/SB mount assembly

- Cut the 30cm of wire in half to create two 15cm lengths of wire. Remove 7-8mm of insulation, and rotate the core to prevent loose wires.
  <img src="./Photos/20220510_235357.jpg" alt="20220510_235357" height="400" />
- Insert the wire on the holes on the back mount
  <img src="./Photos/20220510_235456.jpg" alt="20220510_235456" height="400" />
- Rotate the wires around the other end to prevent them from escaping when the mount is being assembled
  <img src="./Photos/20220510_235612.jpg" alt="20220510_235612" height="400" />
- Put two magnets on top on the probe front magnets
  <img src="./Photos/20220510_235643.jpg" alt="20220510_235643" height="400" />
- Insert the correct front mount on the magnets so that they remain attracted to the probe.
  <img src="./Photos/20220510_235658.jpg" alt="20220510_235658" height="400" />
- with the magnets and front secure, joint the mount front and back with an m2 screw
  <img src="./Photos/20220510_235814.jpg" alt="20220510_235814" height="400" />
- Now, complete with the remaining two m2 screws that will keep the front level
  <img src="./Photos/20220510_235911.jpg" alt="20220510_235911" height="400" />
- Attach another magnet on the 3rd probe magnet
  <img src="./Photos/20220510_235937.jpg" alt="20220510_235937" height="400" />
- Respecting its polarity, put it into the mount back magnet socket
  <img src="./Photos/20220510_235952.jpg" alt="20220510_235952" height="400" />
- The mount is now assembled!
  | <img src="./Photos/20220511_000033.jpg" alt="20220511_000033" width="200" /> | <img src="./Photos/20220511_000042.jpg" alt="20220511_000042" width="200" /> |
  | ------------------------------------------------------------ | ------------------------------------------------------------ |

## Check Your Work

Before anything, make sure the magnet orientations are correct. Go
through the assembly instructions again to ensure correct orientation.
Below are a bunch of checks assuming correct magnet orientation.

- Ensure that the AB/SB mount wires and the magnets are making contact

  <img src="./Photos/check_your_work1.jpg" alt="Probe Magnets and Wire Making Contact" height="400" />

- If you have a multimeter handy, use it to check for continuity. Touch
  the bare wire on the top of the mount with one probe and the magnet
  on the opposing side with the other probe and check for continuity.

  <img src="./Photos/check_your_work2.jpg" alt="Mount Continuity Check using Multimeter" height="400" />

- Ensure that the probe magnets and the microswitch leads are touching

  <img src="./Photos/check_your_work3.jpg" alt="Probe and switch Making Contact" height="400" />

- Once again, if you have a multimeter handy, check for continuity by
  touching the two magnets with your multimeter probes.

  <img src="./Photos/check_your_work4.jpg" alt="Probe magnets and switch continuity check" height="400" />

- When you are first installing the AB/SB mount, don't tightening the bolts
  down all the way. Make sure the mount can still move since we need to adjust how far the mount sits above the probe/dock.

  <img src="./Photos/check_your_work5.jpg" alt="Loose AB mount bolts to allow for height adjustments" height="400" />

- Move the toolhead by hand to allow for the mount to sit right above
  the probe. There should be a hairs worth of gap between the mount and
  the probe. Once the correct height has been established, lock in the
  position by tightening down the bolts.

  <img src="./Photos/check_your_work6.jpg" alt="Loose AB mount bolts to allow for height adjustments" height="400" />

- You should now be able to move the toolhead back by hand and ensure
  that the probe attaches correctly.

  <img src="./Photos/check_your_work7.jpg" alt="Probe attaching to mount properly" height="400" />

## Final thoughts

For the installation, you should now replace the dock (or add the extender to your existing dock) and mount the probe mount to AB or SB and test it. You shouldn't need to change any configuration on your printer, if Klicky was already running without problems.

I have tested Aliexpress N35, N42 and N45 (graciously provided by Drachenkatze) with over 2000 attach/probe/dock without a single probe or dock operation failure.

Please test and report, but remember, it's still under development.

It is working very well for me. If you decide to use it, please send me feedback, either here, or on Voron discord. My discord username is `@JosAr#0517`.

By standing on the shoulders of giants, let's see if we can see further.
