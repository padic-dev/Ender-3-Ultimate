# BLTouch Install Guide

This guide will walk you through the steps of installing the BLTouch auto bed leveling sensor on a Creality Ender-3 3D Printer.

> Note: This guide was created using an Ender-3 Pro, so although the steps will be similar for a regular Ender-3, the location of the mainboard and screws may be different.

Using the BLTouch on an Ender-3 requires the repurposing of the buzzer data lines for BLTouch control, so you will loose beeps when clicking on items in the menus. There is no practical functionality lost, but if tiny beeps are important to you, don't follow this guide. 



##### Materials

* Ender-3 or Ender-3 Pro (Obviously)
* Hex Wrenches (Included with Ender-3)
* [Official Creality BLTouch Kit](https://www.amazon.com/gp/product/B07SCLF42D)
* [Spiral Cut Cable Wrap (Optional)](https://www.mmnewman.com/products/heli-tube-spiral-wrap-abrasion-protector/heli-tube-spiral-cable-wrap-and-abrasion-protector/polyethylene-heli-tube-spiral-cable-wrap-and-abrasion-protector/black-polyethylene-spiral-wrap-3-8-od-on-a-25ft-spool/)
* Small Knife (Olfa/X-Acto/Etc.)
  * I use and highly suggest [this Olfa Knife](https://olfa.com/professional/product/stainless-steel-precision-knife-svr-2/)
* [Mini USB Cable (NOT Micro USB)](https://www.monoprice.com/product?p_id=3896)



##### Operating System Requirements

Although most steps in this guide that involve a computer can be done using macOS, Windows, or Linux, unfortunately the software for the ISP programmer that comes with the BLTouch kit is windows only. As such, a Windows computer or a Mac running bootcamp will be necessary to flash the bootloader unless an alternate method is used. 



### A. Install BLTouch On Print Head

1. Open the BLTouch Kit and check that you have all the parts listed in the Packing List section of the BLTouch Guidebook.
2. Power off and unplug the printer.
3. Using a Hex Wrench, remove the two screws that connect the fan shroud to the print head. Be careful not to stress the fan wires once the fan shroud is disconnected. ![Fan shroud screws](/Images/Photos/IMG_20200130_101251.jpg)
4. Attach the [metal bracket](https://github.com/Jonathan-F-Bell/Ender-3-Ultimate/blob/master/Images/Photos/IMG_20200130_101431.jpg?raw=true) in front of the fan shroud using the included [M3\*8 screws](https://github.com/Jonathan-F-Bell/Ender-3-Ultimate/blob/master/Images/Photos/IMG_20200130_101353.jpg?raw=true). ![Installed Bracked](/Images/Photos/IMG_20200130_101602.jpg)
5. Connect the [white connector](https://github.com/Jonathan-F-Bell/Ender-3-Ultimate/blob/master/Images/Photos/IMG_20200130_101745.jpg?raw=true) of the included cable to the back of the BLTouch. Ensure that the colors of the wires, when looking at the plug of the BLTouch, are in the following order: Blue, Red, Yellow, Black, White (See Image). We have had kits ship with these wires inserted into the connector in the wrong order, which can cause major issues. ![BLTouch with connector](/Images/Photos/IMG_20200130_102249.jpg)
6. Attach the BLTouch to the bracket using the included [M3\*6 screws](https://github.com/Jonathan-F-Bell/Ender-3-Ultimate/blob/master/Images/Photos/IMG_20200130_102310.jpg?raw=true). Note that the screws should be inserted from the bottom up, as the threads are in the bracket, not the BLTouch. ![Mounted BLTouch](/Images/Photos/IMG_20200130_102622.jpg)
7. Use the [spiral cut cable wrap](https://github.com/Jonathan-F-Bell/Ender-3-Ultimate/blob/master/Images/Photos/IMG_20200130_102933.jpg?raw=true) to run the BLTouch cable along the Bowden tube to the extruder, then along side the motor wires down to the main control board on the front left of the printer. If you don't wish to use or purchase spiral cut cable wrap, you can alternatively cut the zip ties, feed the BLTouch cable through the preexisting sleeve, and reattach new zip ties. ![Managed cables, front](/Images/Photos/IMG_20200130_104217.jpg)![Managed cables, back](/Images/Photos/IMG_20200130_104156.jpg)

### B. Wire the BLTouch to the Main Control Board

1.  Flip the printer on its side, with the display side down.
2. Remove the 4 screws that hold the mainboard cover in place. There are 3 on the bottom and 1 on the top, as pictured below. **Important**: [1 of the 4 screws is longer](https://github.com/Jonathan-F-Bell/Ender-3-Ultimate/blob/master/Images/Photos/IMG_20200130_104651.jpg?raw=true). This screw goes in the [back middle screw hole on the bottom](https://github.com/Jonathan-F-Bell/Ender-3-Ultimate/blob/master/Images/Photos/IMG_20200130_104634.jpg?raw=true) when reassembling the printer. ![Bottom screws](/Images/Photos/IMG_20200130_104343.jpg) ![Top screw](/Images/Photos/IMG_20200130_104405.jpg)
3. I find it easiest to flash the bootloader at this step, since the breakout board for the BLTouch gets in the way of the pins. If you wish to flash the bootloader now, follow [this guide](/Guides/Bootloader-Flash-Guide.md) and then return to the next step of the current guide.
4. Using your cutting tool of choice, cut the hot glue that holds the display cable connector and the z-axis switch connector (3rd from the right on the bottom) in place and disconnect the two connectors. ![Disconnected connectors](/Images/Photos/IMG_20200130_105952.jpg)
5. Loosen the screws on the [z-axis switch](https://github.com/Jonathan-F-Bell/Ender-3-Ultimate/blob/master/Images/Photos/IMG_20200130_110003.jpg?raw=true) and remove it from the printer. You may need to push slightly on the top cover of the mainboard to extract the z-axis cable. ![Removed z-axis switch](/Images/Photos/IMG_20200130_110100.jpg)
6. Attach the [connector with black and white wires](https://github.com/Jonathan-F-Bell/Ender-3-Ultimate/blob/master/Images/Photos/IMG_20200130_110328.jpg?raw=true) from the BLTouch cable to the z-stop connector on the mainboard we just removed the z-axis switch from. ![Connected z-stop connector](/Images/Photos/IMG_20200130_110347.jpg)
7. Attach the connector with red, blue, and yellow wires to the [BLTouch/Display breakout board](https://github.com/Jonathan-F-Bell/Ender-3-Ultimate/blob/master/Images/Photos/IMG_20200130_110404.jpg?raw=true), with the yellow wire lining up with the "sig" label on the board. *Note:* Officially, the sig/ground/vcc pins on the breakout board are meant to be bent to a 90 degree angle away from the board. This isn't strictly necessary, but can help solve any clearance issues between the BLTouch connector, display cable, and mainboard cover. ![Connected to breakout board](/Images/Photos/IMG_20200130_110428.jpg)
8. Connect the display cable to the BLTouch/Display breakout board. ![Connected display cable](/Images/Photos/IMG_20200130_110513.jpg)
9. Connect the BLTouch/Display breakout board to the display connector on the mainboard. **Important:** The connector on the breakout board is not as wide as the connector it goes into, so it is possible to misalign the pins and still have the connectors attach. Double check that all pins are aligned and connected together correctly. ![Connected breakout board](/Images/Photos/IMG_20200130_110530.jpg)
10. If you haven't already, flash the bootloader using [this guide](/Guides/Bootloader-Flash-Guide.md). We will be closing up the case soon, and the case needs to be open to flash the bootloader.
11. At this point, I recommend installing the firmware using [this guide](/Guides/Firmware-Flash-Guide.md). Flashing the firmware can be done with the case closed (as long as the bootloader has been flashed first), however it is good to check that everything is working before closing the bottom case. At the very least, [plug in a USB cable](https://github.com/Jonathan-F-Bell/Ender-3-Ultimate/blob/master/Images/Photos/IMG_20200130_110715.jpg?raw=true) to ensure that the [BLTouch](https://github.com/Jonathan-F-Bell/Ender-3-Ultimate/blob/master/Images/Photos/IMG_20200130_110729.jpg?raw=true) and [display](https://github.com/Jonathan-F-Bell/Ender-3-Ultimate/blob/master/Images/Photos/IMG_20200130_110723.jpg?raw=true) both light up. *Note:* The printer will not function until the firmware is updated, as the stock firmware expects a z-axis switch rather than a BLTouch.
12.  Tuck the excess BLTouch cable into the empty space at the back of the case and reattach the bottom cover. *Reminder:* There are 2 short screws that go on the bottom front of the case, 1 short screw that goes on the top of the case, and 1 long screw that goes in the back middle of the bottom of the case. ![BLTouch Cable](/Images/Photos/IMG_20200130_110919.jpg)
13. Set the printer upright.
14. If you haven't already, flash the firmware using [this guide](/Guides/Firmware-Flash-Guide.md).
15. Hardware and software installation is now complete! Before the BLTouch will function correctly, it must be configured. Follow [this guide](/Guides/BLTouch-Config-Guide.md) to configure your BLTouch.

