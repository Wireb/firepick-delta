### EAT0010 Bed heater with I2C A2D

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

Here is the tool slot # to I2C address table
|Tool slot #|EEPROM write|EEPROM read|A2D write|A2D read|
|-----------|------------|-----------|---------|--------|
|1|0xA2|0xA3|0xB2|0xB3|
|2|0xA4|0xA5|0xB4|0xB5|
|3|0xA0|0xA1|0xB0|0xB1|
|4|0xA6|0xA7|0xB6|0xB7|