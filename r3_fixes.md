## R3

### Fixing DPAD size 

Fixed the position and markings of the D-PAD, including orientation holes (ERRATA#28).
Replaceed the two small thin black buttons with another pair of round pads, as described in the blog post (ERRATA#29).
Swaped the function of the existing pair of round pads and the two thin black buttons (ERRATA#30).

https://github.com/MEGA65/megaphone-pcb-2020/issues/20

### Replace VGA with HDMI-compatible interface #13

Useed the HDMI circuit design from the MEGA65 R3 PCB schematic to implement HDMI, freeing up a number of pins (ERRATA#4).
To verify that the necessary signal integrity is possible via the standard .1” IDC headers we created small main board for TE0725 that can hold PMOD boards. We have made changes to existing PMOD so we can use TMDS signals. After few unsucesfull atempts we managed to get HDMI working.
Main problem was that for some reason serialiser from Mega65 HDMI did not work. So we tryed with simple DVI sample from ULX3S, and that worked. 

Replaced VGA interface with HDMI interface based off the MEGA65 R3 PCB (ERRATA#4).

https://github.com/MEGA65/megaphone-pcb-2020/issues/13

### LCD

Removeed the currently routed 6-pin FLC connector for the touch panel, and the 6-pin FLC connector near the bottom of the PCB, but not the one nearest the bottom of the PCB, which is to be retained (ERRATA#5).
Removed the smaller of the two slot-holes in the PCB, and the two extra 6-pin FLC connectors to free up some PCB space (ERRATA#29). This will be somewhat offset by having to route the I2C lines further to get to the connector’s new position.
Moved the remaining 6-pin touch panel digitiser connector 2mm in the direction of the D-SUB9 joystick port (ERRATA#3).
Moved the 40-pin LCD panel connector 10mm further towards the top of the board (ERRATA#1).

https://github.com/MEGA65/megaphone-pcb-2020/issues/9

### Pin swapping

Swaped pins 1 and 3 of S7, so that the "on" position is "on under control of the power control circuit" and "off" is truly off (ERRATA#39).

https://github.com/MEGA65/megaphone-pcb-2020/issues/7

### Transmitters

For regulatory purposes, it is desirable for the main PCB to not be an “intentional transmitter”, that FCC/EC etc approvals are greatly simplified. 
Wifi, lora, BT moved from the board.
Moving the WiFi and BT modules from the main PCB to mezannines
Instead of having wifi and BT separated in R3 we can use ESP32 that offers both with one module.

### CM4

Use CM4, which uses mezannine connectors instead of SODIMM, and takes less space.
Route the parallel video (DPI) interface GPIOs to the main FPGA (requires doing #30 and #13 to free up enough pins on the main FPGA. There should be enough for at least 5 bits per RGB channel, plus HSYNC, VSYNC and DE).
Currently we only added CM4 connectors so we can check if everything will fit.

https://github.com/MEGA65/megaphone-pcb-2020/issues/31
https://github.com/MEGA65/megaphone-pcb-2020/issues/24
https://github.com/MEGA65/megaphone-pcb-2020/issues/2

### POT-X/Y and DSUB

POT-X/Y circuitry copyed from the MEGA65 R3 PCB (ERRATA#17)
Allowed the FIRE line of the joystick port to be controlled and read at high-speed, by using 2 FPGA pins: one to read the level-converted FIRE input, and the other to control a transistor that can be used to pull the 5V side of the FIRE pin to GND when activated. Retain the existing connection to the I2C IO expander (ERRATA#18).
Moveed the D-SUB9 connector to the approximate position of U24, so that it can fit in the main rectangular outline of the PCB (ERRATA#19).

https://github.com/MEGA65/megaphone-pcb-2020/issues/19

### PCB outline

PCB outline returned to the main rectangle, removing the extensions for the D-SUB connectors (ERRATA#20).

### LoRa

Replaceed the on-board LoRa radios with a single header connector that can be used to connect an arbitrary packet radio module (ERRATA#12). 
This connector is compatible with the RFD900 packet UHF radio.

https://github.com/MEGA65/megaphone-pcb-2020/issues/11
