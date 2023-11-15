# Double-Wide SYZYGY Breakout Flash with Level Shifters
SYZYGY 56 pin Breakout Board with level shifters for any voltage flash chip. I wanted a way to experiment with flash without having to spin a new board for each footprint or solder yet another BGA or TSOP. Flash programmers with ZIF adapters seemed like the best choice and SYZYGY would make it compatible with a wide range of FPGA boards. This is the biggest and baddest version of the other SYZYGY flash breakout boards and requires the smart VIO in the SYZYGY DNA to be set to your flash logic level. It requires two adjacent standard ports which can only be found on a handful of FPGA dev boards such as the [Opal Kelly XEM8320](https://opalkelly.com/products/xem8320/).

# Building Firmware
A prebuilt firmware has been provided in the 'firmware' directory. If you want to customize the SMART VIO then modify 'szg-flash-std.json' with the custom power values and use the official [SYZYGY tools](https://github.com/SYZYGYfpga/syzygy-tools/) repo to build the firmware. 
python ..\..\syzygy-tools\dna-tools\syzygy-tools.py -d ..\szg-dna\SZG-FLASH\szg-flash-std.json -f ..\..\syzygy-tools\pod-fw\avr-dna-fw-main.hex

# Fabrication
I use JLCPCB and OSH Park. I used the DRC rules for OSH Park so the board doesn't have any special fabrication requirements. Just pick your favorite PCB shop and color.

# FPGA Development
The board has silkscreen pin designators for the Opal Kelly XEM8320. Theoretically you can use this board with any FPGA dev board that has a double-wide SYZYGY connector then you could use the respective controller for your flash device OR find someway to expose it to AXI and PS to use it with flashrom. As I figure out specific tools that work well then I'll update this README with tutorials.

# BOM
You can find datasheets for each component in the datasheets directory. All of the components can be bought from Mouser or Digikey. 
* Epson SG5032VAN
* Texas Instrument TLV1117LV
* Aries 48-6554-11
* KF2510 8-pin Vertical Connector

# Future Work
This board is still under active development. As I find/create IP and software that works with this board then I'll update this README with tutorials on how to use them. Feel free to create a GitHub issue detailing your own success story or use case.

