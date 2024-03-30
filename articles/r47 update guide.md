# R47 Update Guide

## Acquiring

Start by obtaining all the update materials. You will need the ROM image, the 
SMC firmware, the VERA bitstream.

* Emulator (optional): https://github.com/X16Community/x16-emulator/releases/tag/r47
  * The emulator is not required in order to update your X16, but you'll want the
    latest emulator, anyway, since it has the same changes as the ROM, SMC, and VERA
    that are on the official hardware.
* ROM: https://github.com/X16Community/x16-rom/releases/tag/r47
  * Download `x16-rom-R47.zip`
  * Extract rom.bin from the zip file.  Save it as `ROM.BIN` all CAPS.
* SMC: https://github.com/X16Community/x16-smc/releases
  * Download `SMC-47.0.0.BIN`
* VERA: https://github.com/X16Community/vera-module/releases/tag/v47.0.2
  * Download `FLASHVERA.PRG` and `VERA_47.0.2.BIN`
* Updater: https://github.com/FlightControl-User/x16-flash/releases/tag/r3.0.0
  * Download `CX16-UPDATE-R3.0.0.PRG`

The SMC update is optional. We recommend _not_ updating the SMC at this time, if
you are not having problems with your PS/2 keyboard or mouse. To skip the SMC
update, simply do not include `SMC.BIN` in the steps below. The update tool will
skip the SMC update if the file is not present.

## Installing

1. Power off the X16.
2. Remove your SD card from the X16 and insert it in the SD card slot of a PC or
   Mac.
3. Create a new directory on your SD Card named UPDATE (all caps) and copy all
   of the files into that directory.
4. Rename the SMC file to `SMC.BIN`
5. Rename the VERA file to `VERA.BIN`
6. Rename the update program to `UPDATE.PRG`
7. Your UPDATE folder should have these files on it:
    ```
    ROM.BIN
    SMC.BIN (optional)
    VERA.BIN
    UPDATE.PRG
    ```
8. Safely eject the card from your computer and re-install it in the X16.

## Updating

1. Look for the **J1** Write Protect jumper on your motherboard. The jumper cap
   must be _installed_ to enable writing to the system flash ROMs. 
   * This may be labeled "Remove J1 to write protect system ROM".
2. Start your X16 and type `DOS"CD:/UPDATE"` and press RETURN
3. type `LOAD UPDATE.PRG` and press RETURN
4. Type `RUN` and press RETURN
5. You'll get some warning screens about compatibility. These are normal.
    * You will need to press `SPACE` and `Y` quite a few times before you get to
      the point where flashing will begin.
    * The Updater application does provide quite detailed instructions.  Read
      everything carefully.
6. The ROM will update first. Once that's done, you'll be told to close the JP1
   pin on VERA. Don't actually close the pin until after the program has read 
   VERA.BIN (the bottom portion of the screen will be filled with dots) and the
   middle portion says `CLOSE the JP1 jumper header on the VERA board!`
7. Place the jumper cap on JP1 on the VERA board and press the SPACE bar. 
   * This disables the SD card, so you'll need to remove the cap once the
     VERA flash is complete.
8. The next step will be to update the SMC. When the program asks, hold the
   power button down and tap the RESET button. You must do so before the timer
   runs out. 
9. You will then see the same SMC update progress.
10. If the SMC was updated, the power button on the front panel won't actually
    turn off the computer, because the SMC runs on the +5V Standby rail. So you
    need to unplug your X16 from the wall to de-power the SMC, then plug it back
    in.
    * **DO NOT** unplug the 12V barrel connector to de-power the Pico PSU (if
      you are using one.) Unplug the 120/240V to 12V adapter from the wall,
      instead.
11. After restarting your X16, confirm the version of the ROM, VERA, and SMC
    firmware by typing `HELP` and pressing RETURN.
    * After the full R47 release, the version numbers will be:
    * COMMANDER X16 ROM RELEASE R47
    * VERA: V47.0.2
    * SMC: 47.0.0
12. At this point, if you have purchased a 65C816 processor, you can power the
    system down (unplug it) and install the new CPU.
