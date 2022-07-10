Voron 2.4/Trident Direct Mount MGN12 X Carriage with support for CW2
This is a modified MGN12 X carriage for the Voron 2.4/Trident which directly interfaces with the Klicky. This is based on Arkeet's MGN12 carriage and BlueDrogonX's.

The primary benefits of this approach are more rigid mounting of probe and reduced offset from the nozzle. Hotend airflow may also be improved as the rear of the carriage is now open.

This mod does not work with the standard fixed dock mounts as the location of the probe is changed in relation to the hotend. I have included new fixed mount to account for this.
you will need the fix mounted dock from https://github.com/kyledavis417/Klicky-Probe/tree/main/Printers/Voron/v1.8_v2.4_Legacy_Trident/Usermods/bluedragonx

Installation
You will need to print each of the following:

v2.4_x_carriage_frame_mgn12_left_CW2.stl
v2.4_x_carriage_frame_mgn12_right_endstop_CW2.stl
And one of the two dock mounts depending on where you wish the dock to live:

v2.4_x_carriage_dock_mount_fixed.stl
v2.4_x_carriage_dock_side_mount_fixed.stl

Bolt together the two halfs of the carriage as normal. Follow the instructions for the regular Klippy AB mount to install the magnets and wiring.

Setup
This mod changes the standard Klicky probe offset so you will need to adjust your settings to account for this.

The only value you should need to adjust is the y_offset for the probe. The new value is 17.5mm.

Both dock mounts are 4mm shorter in the Z direction. The fixed dock mount is also 2mm longer in the Y direction.
