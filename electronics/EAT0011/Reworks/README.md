### EAT0004 to EAT0011 rework instructions

These directions are for reworking a EAT0004 hot end module into a EAT0011. This path is NOT recommended as the new PCBs will be more reliable and fit better into the FPD. Mainly for bringup only. 

Refer to EAT0002_to_EAT0011_top_rework.png and EAT0002_to_EAT0011_bot_rework.png for all the following steps. 

1. Get a programed PIC16F1704 with the latest base firmware. Once there is a initial program load it can be updated via I2C. BUT blank parts cannot be programed over the I2C bus.  
1. Remove and discard U2 (24AA014 eeprom 6 pin SOT) 
1. On the top side cut the AIN trace where shown by the blue X near the IO connector. 
1. On the bottom side cut the DOUT trace where shown by the red X near the IO connector. 
1. On the top side connect pins 1, 2, 3, 8, 9, 11, 12, 13, and 14 of the PIC16F1704 to the pads marked by blue numbers. Fine telephone, ribbon cable, or wire wrap wire works best. 
1. On the bottom side connect pin 4 of the PIC16F1704 to the pad marked by the red 4. Note leave enough wire to wrap around the top edge of the card else it will get pinched in the card guides on the EMC0002. 
1. Optionally pin 7 can be connected to a 150 ohm resistor and LED. Tie the + side of the LED to the +5V rail (same pad as pin 1 of the PIC16F1704) 
1. Verify pins 5, 6, 10, and 7 (if not used for the LED) are not shorted or connected to anything else. 

At this point the reworks are finished and the module is ready for use. Recommend securing the PIC16F1704 to the top of the card just above the IO connector using hot glue. Also apply a light coat of hot glue to the pins and wires to insulate them. Make sure the PIC16F1704 and hot glue does not hang over into the rail zones on either edge of the card. 

TODO add picture of reworked card to package.  