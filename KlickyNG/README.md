# Klicky Probe NG (Next Generation)
Microswitch probe with magnetic attachment, primarily aimed at CoreXY 3d printers, with enclosed magnets, don't fall, don't need to be glued.

This version is still a **BETA** version, so please use with care.
Its parent version, and still the recommended one is [Klicky](https://github.com/jlas1/Klicky-Probe).

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

Please check the main Klicky repository for all the people that helped this project, for NG, would like to thank (in no specific order) Dustinspeed, Drachenkatze, clee, top_gun_de and whoppingpochard.

If you want to donate something regarding this project, use this [link](https://paypal.me/Josar154) or [__Buy me some ABS!__](https://www.buymeacoffee.com/JosAr), thanks

Without further delay, here is the new version with enclosed magnets:
![Klicky Probe image](Photos/overview.jpg)

The eyebrows are clee+whoppingpochard's design.

# KlickyNG support

For now, only printers compatible with Voron StealthBurner/AfterBurner are compatible, as the NG mount has changed significantly.

- [The CAD with all the files](./CAD)
- [Common KlickyNG STLs](./STL)

You can also [view an exploded view](https://youtu.be/mlyU2tHjebo).

## Print Settings

There is no need for supports; recommended settings are 4 perimeters/top/bottom, at least 23% infill. The STL's are already oriented for you, so you only need to send them to the slicer.

![](./Photos/print_orientation.jpg)

## Required parts

| <img src="./Photos/NG_Probe_Dock.JPG" alt="NG_Probe_Dock" style="zoom:5%;" /><img src="./Photos/NG_2mm_extender.JPG" alt="NG_2mm_extender" style="zoom: 5%;" /> | If you want to reuse your old Klicky dock, it needs to use this setup for the back magnet. It will also be necessary to print the 2mm NG extender, as the dock needs to be 2mm longer. |
| :----------------------------------------------------------: | ------------------------------------------------------------ |
| <img src="./Photos/NG_Probe_insert.JPG" alt="NG_Probe_insert" style="zoom:5%;" /> | Probe Insert, required to hold the switch and the two magnets that make the electrical connection |
| <img src="./Photos/NG_Probe_body.JPG" alt="NG_Probe_body" style="zoom:5%;" /> | Probe body, required to prevent the two front magnets from escaping the probe, holds the third magnet to help attach the probe to the mount and the back magnet to secure it to the dock |
| <img src="./Photos/NG_back_mount.JPG" alt="NG_back_mount" style="zoom:5%;" /> | Mount back, mounts to the AB/SB, holds the third magnet and the wire connections |
| <img src="./Photos/NG_front_mount_3mm.JPG" alt="NG_front_mount_3mm" style="zoom:5%;" /><img src="./Photos/NG_front_mount.JPG" alt="NG_front_mount" style="zoom:5%;" /> | Mount front, 2 versions; one for arround 2.75mm (instead of 3mm) height, and one for actual 3mm-height magnets |

# Bill of Materials (BOM)

- 1x microswitch (the Omron D2F-5, or D2F-5L with the lever removed, are recommended, but similar-sized microswitches like D2F-1 and KW10 will also work)
- 30cm of wire, AWG22 or similar
- 5 M2x10mm self-tapping screws
- 8x 6mm diameter x 3mm height magnets
- 2x M3x18mm/M3x20mm screws

# Build Process

First, assemble the required materials.

<img src="./Photos/20220510_234804.jpg" alt="material" style="zoom:50%;" />

## Probe assembly

- Put two magnets on the KlickyNGProbe_v3 Insert, and make sure they have the same polarity.
  <img src="./Photos/20220510_234928.jpg" alt="20220510_234928" style="zoom:50%;" />
- Next, insert another magnet on the back groove of the KlickyNGProbe_v3 Body. In this image, all 3 magnets should have the same polarity on top, so that when they are assembled, the back magnet will repulse the two front magnets.
  <img src="./Photos/20220510_235026.jpg" alt="20220510_235026" style="zoom:50%;" />
- Now, place the insert on the body, aligning the magnets and making sure that the front magnets do not move out of place.
  <img src="./Photos/20220510_235051.jpg" alt="20220510_235051" style="zoom:50%;" />
- Insert the microswitch in its place (pictured here a KW10)
  <img src="./Photos/20220510_235119.jpg" alt="20220510_235119" style="zoom:50%;" />
- Secure the microswitch with the two M2x10 screws to secure the switch, and also pull the two parts of the probe body together.
  <img src="./Photos/20220510_235228.jpg" alt="20220510_235228" style="zoom:50%;" />
- Insert the back magnet, and the probe is complete!
  | <img src="./Photos/20220510_235234.jpg" alt="20220510_235234" style="zoom:50%;" /> | <img src="./Photos/20220510_235241.jpg" alt="20220510_235241" style="zoom:50%;" /> |
  | ------------------------------------------------------------ | ------------------------------------------------------------ |

## AB/SB mount assembly

- Cut the 30cm of wire in half to create two 15cm lengths of wire. Remove 7-8mm of insulation, and rotate the core to prevent loose wires.
  <img src="./Photos/20220510_235357.jpg" alt="20220510_235357" style="zoom:50%;" />
- Insert the wire on the holes on the back mount
  <img src="./Photos/20220510_235456.jpg" alt="20220510_235456" style="zoom:50%;" />
- Rotate the wires arround the other end to prevent them from escaping when the mount is being assembled
  <img src="./Photos/20220510_235612.jpg" alt="20220510_235612" style="zoom:50%;" />
- Put two magnets on top on the probe front magnets
  <img src="./Photos/20220510_235643.jpg" alt="20220510_235643" style="zoom:50%;" />
- Insert the correct front mount on the magnets so that they remain attracted to the probe.
  <img src="./Photos/20220510_235658.jpg" alt="20220510_235658" style="zoom:50%;" />
- with the magnets and front secure, joint the mount front and back with an m2 screw
  <img src="./Photos/20220510_235814.jpg" alt="20220510_235814" style="zoom:50%;" />
- Now, complete with the remaining two m2 screws that will keep the front level
  <img src="./Photos/20220510_235911.jpg" alt="20220510_235911" style="zoom:50%;" />
- Attach another magnet on the 3rd probe magnet
  <img src="./Photos/20220510_235937.jpg" alt="20220510_235937" style="zoom:50%;" />
- Respecting its polarity, put it into the mount back socket
  <img src="./Photos/20220510_235952.jpg" alt="20220510_235952" style="zoom:50%;" />
- The mount is now assembled!
  | <img src="./Photos/20220511_000033.jpg" alt="20220511_000033" style="zoom:50%;" /> | <img src="./Photos/20220511_000042.jpg" alt="20220511_000042" style="zoom:50%;" /> |
  | ------------------------------------------------------------ | ------------------------------------------------------------ |

## Final thoughts

For the installation, you should now replace the dock (or add the extender to your existing dock) and mount the probe mount to AB or SB and test it. You shouldn't need to change any configuration on your printer, if Klicky was already running without problems.

I have tested Aliexpress N35, N42 and N45 (graciously provided by Drachenkatze) with over 2000 attach/probe/dock without a single probe or dock operation failure.

Please test and report, but remember, **this is a BETA! It may twist your extrusions, or ruin your print surface. Use with care.**

There will also be soon a [Unklicky](https://github.com/majarspeed/Unklicky) for KlickyNG, stay tuned.

It is working very well for me. If you decide to use it, please send me feedback, either here, or on Voron discord. My discord username is `@JosAr#0517`.

By standing on the shoulders of giants, let's see if we can see further.
