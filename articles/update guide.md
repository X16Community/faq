# Commander X16 Update Guide

> [!WARNING]
> This guide is **DEPRECATED**. Follow this guide instead: https://github.com/X16Community/x16-docs/blob/master/X16%20Reference%20-%20Appendix%20H%20-%20Onboard%20Upgrade%20Guide.md

> [!CAUTION]
> **DO NOT** update your SMC following this deprecated guide. This will **BRICK** your SMC! (Unless you have repaired your bootloader)

## Acquiring

Start by obtaining all the update materials. You will need the ROM image, the 
SMC firmware, the VERA bitstream.

* Emulator (optional): [Emulator Releases](https://github.com/X16Community/x16-emulator/releases/)
  * The emulator is not required in order to update your X16, but you'll want the
    latest emulator, anyway, since it has the same changes as the ROM, SMC, and VERA
    that are on the official hardware.
* ROM: [ROM Releases](https://github.com/X16Community/x16-rom/releases/)
  * Download `x16-rom-Rxx.zip`, where `xx` is the latest version number.
  * Extract rom.bin from the zip file.  Save it as `ROM.BIN` all CAPS.
* VERA: [VERA Releases](https://github.com/X16Community/vera-module/releases/)
  * Download `FLASHVERA.PRG` and `VERA_47.0.2.BIN`
* SMC: (see note below) https://github.com/X16Community/x16-smc/releases
  * Download `SMC-47.0.0.BIN`
* Updater: [V3 Release](https://github.com/FlightControl-User/x16-flash/releases/)
  * Download `CX16-UPDATE-R3.0.0.PRG`

The SMC update is optional. We recommend _not_ updating the SMC at this time, if
you are not having problems with your PS/2 keyboard or mouse. To skip the SMC
update, simply do not include `SMC.BIN` in the steps below. The update tool will
skip the SMC update if the file is not present.

> [!CAUTION]
> Update (2025-10-07): When this guide was written, there was an unresolved problem causing SMCs to be bricked during firmware update.
The reason for this is that machines in the range ~PR001 to ~PR900 was delivered with SMC 45.1.0 and a "bad" version of the bootloader.
If you have one such machine and attempt to update your SMC, you will **BRICK** it if you follow the instructions here.
You are STRONGLY advised to **NOT** update your SMC as instructed here because of this.
However, if you follow the instructions given in the updated guide (see the top of this document), it is possible to update SMC with a bad bootloader,
but, this requires **SHORTING** two points on the X16 mainboard to succeed.

We recommend applying the update to a spare [ATTINY Microcontroller](https://www.mouser.com/ProductDetail/Microchip-Technology/ATTINY861A-PU?qs=LHmEVA8xxfaSeKN6IG2jWA%3D%3D)
and swapping that out. We are working on a manual update process. In the meantime,
see [This Discord channel](https://discord.com/channels/547559626024157184/1224465757786865694)
for the information we have collected.

## Installing

1. Power off the X16.
2. Remove your SD card from the X16 and insert it in the SD card slot of a PC or
   Mac.
3. Create a new directory on your SD Card named UPDATE (all caps) and copy all
   of the files into that directory.
4. Rename the SMC file to `SMC.BIN` **(Warning: Highly discouraged to include this file!)**
5. Rename the VERA file to `VERA.BIN`
6. Rename the update program to `UPDATE.PRG`
7. Your UPDATE folder should have these files on it:
    ```
    ROM.BIN
    SMC.BIN (optional, highly discouraged!)
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
8. The next step will be to update the SMC.
   * 2025-10-07 Friendly reminder: Do **NOT** proceed unless you know what you are doing.
     * If there is the slightly risk that you have the bad bootloader (stock machines with PR001-PR900),
       do **NOT** proceed unless you have read the "update with bad bootloader" instructions.
	   If not, abort the update. Disconnect power if needed.
   * If you still want to start the SMC update **(discouraged!)**:
     * When the program asks, hold the power button down and tap the RESET button.
	   You must do so before the timer runs out. 
9. You will then see the same SMC update progress.
10. If the SMC was updated, the power button on the front panel won't actually
    turn off the computer, because the SMC runs on the +5V Standby rail.
	* 2025-10-07 Follow the "update with bad bootloader"-guide to see which pins to **SHORT** if the machine hangs.
	  **DO NOT** disconnect power if you have "bootloader v2", as this will **BRICK** the machine!

11. After restarting your X16, confirm the version of the ROM, VERA, and SMC
    firmware by typing `HELP` and pressing RETURN.
    * After the full R47 release, the version numbers will be:
    * COMMANDER X16 ROM RELEASE R47
    * VERA: V47.0.2
    * SMC: 47.0.0
12. At this point, if you have purchased a 65C816 processor, you can power the
    system down (unplug it) and install the new CPU.
