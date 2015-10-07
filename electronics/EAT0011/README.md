### EAT0011 hot end heater / stepper control with I2C A2D

This design is to work around the issues with multiple 5V references and electrical noise causing weird temperature readings. 

Also fixed in this design is the location of the FET heatsink. Module will now be usable in all slots vs just #1 and #3. 

Current firmware address map can be found here:
https://docs.google.com/spreadsheets/d/1kPm5gxKLETWQP0ESqcd6hGNN2_4XGnE_AItsoCVzvwQ/edit?usp=sharing


High level function overview:

1. I2C A2D 10 bit converter for thermistor input.
1. I2C EEPROM storage (256 bytes)
1. Fet Gate buffer (prevents Fet from going into linear mode due to bad input voltage level)
1. Heater status led. 


The firmware is also set up to allow updating via I2C and the hardware can support self contained PID operation with updated firmware. 