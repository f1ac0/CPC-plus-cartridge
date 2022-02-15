# CPC-plus-cartridge
In this repository you will find different PCB designs and code to make a CPC-plus cartridge. The ACID chip is implemented inside a XC9536XL CPLD using the equations published by octoate : https://www.octoate.de/articles/acid-verilog-code/

Facts about this project :
- The ZIF version has a ZIF socket for DIP32 ROM SST39SF040 or W29C040, and is longer than standard cartridges
- the PLCC version can be used with PLCC SST39SF040 ROMs and its size is more standard
- They both have jumpers to select 128k, 256k or 512K cartridge ROM banks

# Disclaimer
This is a hobbyist project, it comes with no warranty and no support. Also remember that the Amstrad machines are about 30 years old and may fail because of such hardware expansions.

I publish my work under the CC-BY-NC-SA license.

If you find it useful and want to reward me : I am always looking for Amiga/Amstrad CPC hardware to repair and hack, please contact me.

# BOM
- 1x XC9536XL CPLD
- 1x DIP32/PLCC32 ROM SST39SF040 or W29C040 and appropriate socket
- 1x 3.3v LDO, either SPX3819M5-L-3-3 or XC6206P332MR
- 2x 1uF (or more) 0805 capacitors
- 4x 100nF 0805 capacitors

# Making it
Check for shorts at least between 5V, 3.3V, and GND traces before applying power !

The programming port does not need to be soldered since it needs to be programmed just once : you can just hold it in place during the few seconds required for programming.

CPLD code is generated and built into xsvf using Xilinx ISE 14.7 IDE then iMPACT. "Macrocell power setting" can be "Low" an "Slew rate" to "Slow".

There are several methods to program the XC9536XL. I personally use xsvfduino : https://github.com/wschutzer/xsvfduino

Check the alignment between the cartridge pads and connector pads inside the CPC when installing it for the first time.

# Using it
- Burn the ROM images and install the ROM. Do not burn .cpr files directly, they need to be first converted using for example "CPRTools".
- Choose the ROM to use and its size using the jumpers :
  - 512k = both jumpers vertical
  - 256k = "256" jumper vertical and "512" to select 0 or 1
  - 128k = both jumpers to select 0 or 1
- Enjoy
