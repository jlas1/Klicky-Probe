# KlickSwipe - A servo-powered retractable dock for Klicky Probe

![KlickSwipe](./images/KlickSwipe%20Render.png)

KlickSwipe is a alternative mount for the klicky probe derived from the [SlideSwipe](https://github.com/chestwood96/SlideSwipe/) probe, but modified specifically for Klicky.  
It mounts to 1515 extrusion and was designed for use in the V0, but may work in other small printers as well.  
KlickSwipe is particularly useful when your print head can't reach outside of the bed to attach the probe, as it moves the probe within reach only when necessary.




## Bill Of Materials

| Part                              | Qty         | Notes                                   |
| --------------------------------- | ----------- | --------------------------------------- |
| MG90s Servo                       | 1           | SG90 May also work                      |
| M2x8mm Self Tapping Screw         | 2           |                                         | 
| M3x8mm BHCS or SHCS               | 4           |                                         |
| Threaded Insert M3x5x4            | 4           | Standard Voron size                     |
| 4mm OD PTFE Tube                  | 49mm total  | 14mm x 3, 7mm x 1  cutting jig included |
| 6mm x 3mm round neodymium magnets | 1           | Standard Voron size                     |


## Assembly
![Assembly](./images/assembly.gif)

## Configuration

Configure klicky probe as per the usual process, but include the following macros in your config, *after* klicky-macros.cfg:


```
[gcode_macro _DeployDock] # Deploy Arm
gcode:
    SET_SERVO SERVO=KlickSwipe ANGLE=90
    G4 P500

[gcode_macro _RetractDock] # Retract Arm
gcode:
    SET_SERVO SERVO=KlickSwipe ANGLE=0
    SET_SERVO SERVO=KlickSwipe WIDTH=0
```

