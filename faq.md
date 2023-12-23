<p align="center"><img src="about.png" alt="About Commander 16" /></p>

## What is the Commander X16?

Welcome! 

The Commander X16 is The 8-Bit Guy’s dream computer, designed to evoke the same fondness and nostalgia many of us had for 8-Bit computers, while retaining closeness to the hardware from a programming perspective, unlike the Raspberry Pi and others. But more than that, it is intended not only as an educational tool but to solve some of the issues of finding an 8-Bit system to tinker with today; namely ever-increasing costs, auction site price gouging/sniping, lack of replacement parts, and unreliability of 30-year old hardware.

The X16 will be made entirely with parts that are still readily available today, ensuring perpetual availability without reliability issues, but in keeping with David's vision, it will house a real CPU rather than using emulation or an FPGA recreation of a processor. Running Commodore BASIC V2 (with some additions), the X16 will be inexpensive enough to allow a critical mass of users to create an expansive software ecosystem, but simple enough that a single person can understand all of the chips and components that allow that software to run.

Three models, or "Generations" of the computer are planned under the "Commander X16" brand umbrella. All of the models will run the same software and will feature full support for keyboard, mouse, and game controllers. 

* **Gen-1**: This is the Developer Edition, with 4 expansion slots, giving you flexibility for hardware and software development. (A network card will be available to match the networking capabilities of G2 and G3 systems.)
* **Gen-2**: The Console Edition: Is it a computer or a game console? Yes. G2 will be smaller and less expensive, but it is still a complete Commander X16. 
* **Gen-3**: The "Elite" model will be similar in size to a Rasbperry Pi SBC. This will be inexpensive enough to be sold to schools and colleges for STEM programs.

As the G2 and G3 systems become available for sale, you will be able to buy all three systems.

Please watch [Commander X16 video playlist](https://www.youtube.com/playlist?list=PLfABUWdDse7bKGFshxR0itdHBhjUj86SX) for more details.

## Who is The 8-Bit Guy

David Murray, AKA "The 8-Bit Guy" runs a successful YouTube channel centered on vintage computing. He also dabbles in music, electric car culture, off-grid energy production, computer refurbishment and resale. 

His web site is [https://www.the8bitguy.com/](https://www.the8bitguy.com/)

## Specifications

Commander X16P Features & Specifications (subject to change)

* CPU
  * WDC 65C02S @ 8 MHz
  * 40-pin DIP package
  * Protoype board currently running stable at 8 MHz
* RAM
  * 40K of "Low RAM":
    * As 39.75K + 256 bytes of IO space
    * 8 IO spaces of 32 bytes each; one for the VERA, one for the VIAs, one for the audio
  * 512K of "High RAM" standard:
    * As 64 banks of 8K
  * Expandable to 1 MB, 1.5 MB, or 2 MB by adding additional RAM chips to 3 empty sockets
    * Up to 256 banks of 8K
  * ROM
    * 512K of Flash ROM
      * As 32 banks of 16K
      * Expandable to 4MB of ROM or RAM with expansion cards. 
  * Standard Commodore Kernal
  * CMDR-BASIC
    * Microsoft BASIC 2.0 (Complete, identical to Commodore 64 and VIC-20)
    * Commander X16 extentions
  * Machine Language Monitor (Supermon and CODEX)
  * ROM can be flashed in place. 
* Expansion
  * Four expansion slots with access to CPU databus
  * Each slot can select from one or more of 5 addressable 32 bytes of IO space
  * User Port (Extra lines from the single VIA)
* Input Devices
  * PS/2 Keyboard
  * PS/2 Mouse
  * Two SNES style game ports (two more as pin headers)
* Storage
  * IEC compatible (Commodore) disk drive port
  * Internal SD card slot on VERA
* Audio
  * Yamaha YM2151 sound chip
  * PCM audio on VERA
  * PSG waveform generator on VERA (simple waveforms and frequency. No envelopes or effects.)
* "VERA" module specifications
  * Video generator featuring:
    * Multiple output formats (VGA, NTSC Composite, NTSC S-Video, RGB video) at a fixed resolution of 640x480@60Hz
    * Support for 2 layers, both supporting:
    * 1/2/4/8 bpp tile and bitmap modes
    * Support for up to 128 sprites (with inter-sprite collision detection).
  * Embedded video RAM of 128 KB.
  * Palette with 256 colors selected from a total range of 4096 colors.
  * 16-channel stereo Programmable Sound Generator with multiple waveforms (Pulse, Sawtooth, Triangle, Noise)
  * High quality PCM audio playback from an 4 KB FIFO buffer featuring up to 48kHz 16-bit stereo sound.
  * SecureDigital storage.
* Board power consumption: ~15W
* PSU: TBC

## When will the X16 be released?

The first batch of dev boards have been received by David. The team is currently hand soldering development boards, and they are working on a solder dip station for rapid assembly. The first 100 boards should be delivered this year, with additional sales to follow. 

Update: they are working out the kinks in the assembly process, and expect to start selling boards "soon". This spring or summer is likely.

There will _not_ be a pre-order process. The 80-some boards that are part of the first batch will be first come, first served. An announcement will be made to the community when the board is available. 

## How much will it cost?

The price for the next production run will be $350 for a baseline board with 512K of RAM and a single VIA. Extra memory and a second VIA for the User port will be optional and can be added at the time of purchase. 

## Where can I get it? 

The Commander X16 can be pre-ordered from [Texelec](https://texelec.com/product/cx16-preorder/) and is due to be released February 29, 2024. Watch our social media channels on Facebook and Discord for more information.

## Why Commodore BASIC?

This entire computer is meant to be a close relative of the Commodore systems. While technically Commodore BASIC is actually Microsoft BASIC, David wants it to be as similar as possible to programming on a VIC-20, C64, or Plus/4. It will run BASIC v2 with some additions. We have reached agreement with the rights holder to license it for this purpose.

## What about other languages?

Compilers are available for several programming languages: at least two different C compilers support the X16 as a compiler target, with appropriate runtimes. We also have a FORTH compiler in progress, plus a new programming language named Prog8. You can also use a dialect of BASIC called XC=BASIC. Of course, 65C02 assembly language is also an option, and all of the popular 6502 assemblers can output object code that works on the X16. 

## Will it be compatible with Commodore 64 software?

No, this is not an emulation of any prior computer. The X16 is a unique product with its own memory layout and devices. It can run simple BASIC programs written for BASIC 2, and it can even run machine language programs that strictly use KERNAL calls for input and output. It will not, however, run Commodore games without re-writing the graphics, keyboard, joystick, and storage routines for this platform. 

## Can this emulate <some other computer>?

No. The 6502 does not have the necessary hardware for realtime emulation of other system architectures. Attempting to emulate any other computer in real time is going to be virtually impossible. Again, some things can be simulated at a superficial level, but full emulation that can run arbitrary machine code from another platform is unlikely.

## Why the name "X16"?

Commodore already has a "C16" computer: the Commodore 16. Obviously, we don't want people confusing "C16" and "C16". So the "X" was added to differentiate our computer. Perifractic proposed the always cool "X" be added to make "X16", and this got the team's vote. 

The "16" part comes from the intention to use a 65C816 processor. While that plan was scrapped, due to the need for additional hardware to demux the address and data lines, the name has not changed. 

## Why VGA instead of Composite or HDMI?

Licensing. While it's fairly simple to implement an HDMI device, we would have to pay license fees to build an actual HDMI output. Also, VGA is fairly easy to implement, and VGA to HDMI converters are fairly inexpensive. We will have specific models of tested and supported converters in the future. 
 
A digital video board may be made available in the future. Stay tuned for more information. 

## What sort of expansions would be possible?

There will be up to 4 expansion slots, and some of the unused VIA pins may be available on the rear panel. Expansion slots will have the full address and data bus, plus up to 5 shared CS lines. Using a jumper or DIP switch on the expansion card, a user should be able to map an expansion card to any of the 5 address ranges available for I/O. Cards can also access the address range used by the ROM and RAM banks, allowing for additional memory expansion, game cartridges, or high speed storage interfaces. 

## What sort of joysticks will you use and why?

SNES style game controllers. The SNES interface uses fewer wires and allows for more buttons on each pad. Also, joysticks have sort of fallen out of favor and people prefer gamepad controllers. 

## Will a floppy or CD-ROM drive be included?

The system will store data on SDHC or SDXC memory cards. (The older SD cards with less than 2GB may not be supported.) 

In addition, the Gen-1 system will include a Commodore compatible IEC port, to allow reading from a user-supplied Commodore 1541, 1571, or 1581 diskette drive. Floppy drives are no longer being manufactured, so there are no plans to include a floppy diskette or optical disk drive. 

## Will it support cassette drives?

Official cassette drive support is not planned, and the KERNAL ROM does not support reading from or writing to tape.

If you want to run a Commodore BASIC program you have saved on tape, you can use a Commodore computer to copy the program to diskette, or you can convert the cassette to TAP format on a PC, using various conversion tools (we can help you on the forums.)

## What do you need help with the most?

At the moment we need software development. The emulator is now available and people can start writing their own code. You can upload your creations to the software library at this website.

## Will it be available as a kit/pre-assembled/motherboard only?

We haven't decided for certain. The problem with selling it as a kit is that the design team will not have time for being end-user tech support. So, while the kit may end up being cheaper, it will also be sold without official technical support - although this website has been set up so people can still obtain support from the community and/or developers. If people assemble it and it doesn’t work, they can ask for support there. We will update the FAQ once a decision has been reached about whether to provide a kit option. As for a motherboard only option, our focus now is on releasing the computer. Once the project is launched and established, we will revisit these kind of options.

## Will a keyboard be included?

Yes. A custom Perixx keyboard has been designed by Perifractic. Based on the [PERIBOARD-409](https://perixx.com/products/periboard-409-u-w-wired-mini-keyboard-75-quiet-keys-in-white). The keyboard will resemble the late model Commodore 64C keyboard, WITH PETSCII glyphs, and a white case. You can also order a [custom WASD keyboard](https://www.wasdkeyboards.com/commander16-by-the-8-bit-guy.html) with compatible PS/2 firmware and PETSCII keycaps. [PETSCII Keycaps](https://www.wasdkeyboards.com/commander16-by-the-8-bit-guy-87-key-custom-cherry-mx-keycap-set.html) are also available separately.

## Why PS/2 Keyboard and not USB?

USB is tremendously more difficult to implement than PS/2. A good analogy is like the difference between implementing RS-232 or Ethernet. PS/2 keyboards (and mice) are still manufactured, easy to find, and inexpensive. And, since the kernel is going to handle keyboard input, there’s no reason we can’t upgrade to USB later when we have the resources for that - and it shouldn’t break compatibility.

## Will a case be included?

A case design is in progess. At this point, we believe the case will be an optional feature. 

## Why not a wedge case?

The case resembles a slim line, ATX PC case. It does not include a built-in keyboard for cost reasons.

Not all retro comptuers used wedge cases. Consider the Amiga 1000, A2000, A2500, A3000, A4000, Apple Macintosh, Apple III, Apple IIGS, Commodore 128D, Amstrad PCW, Amstrad PC1512, Amstrad PC1640, Acorn Archimedes, Sony MSX, Atari Mega ST, Atari TT030, Coleco Adam, Kaypro series, and many more beautiful retro machines with separate keyboards.

## What about expansion cards for each generation? 

* Gen 1: 4 expansion card slots. One slot will have the ROM bank lines and be "BONK" (RAM in ROM Bank) compatible. 
* Gen 2: Cartridge slot and all other external ports. The cartridge slot should be identical to slot 1 in the Gen-1 board. 
* Gen 3: TBD, but "probably not."

## Why isn't a monitor included?

Cost. If you don't have a spare monitor, you can pick one up for less money than it would cost for us to acquire and ship to you. Also, most enthusiasts already have a compatible monitor that can handle VGA graphics. 

## How about a mouse?

A PS/2 mouse is expected to be included. 

## Will it be available in the USA, Europe, & beyond?

We hope to offer international shipping from the USA. Note that the official keyboard will use the US ANSI layout, but it will be compatible with several languages and layouts. 

## Will user guides be included?

Perifractic designed a nostalgic traditional spiral bound Getting Started guide with an awesome (top secret) cover co-created by him and Trevor Storey. The manual includes a BASIC programming guide. The rest of the team are currently finishing up the finer details of the manual. Further docs are already available in the Downloads section of this website. The working title for the spiral bound guide is “Just the BASICs: Getting started with the Commander X16”. There will also be “Assembling Assembly” and a programmer’s reference guide. PDFs will likely be an option.

## Why not use the Parallax Propeller chip, FPGA, Arduino, Teensy, Pi Pico, etc?

We will not be using the Propeller for these reasons:
Most of its capabilities are on par with or inferior to our custom FPGA.
There are issues when putting it on the system bus related to CPU read attempt speed call and answer
The Propeller costs the same as if not more than the faster FPGA

## Will there be a GUI?

There is no official GUI planned. Support routines for GEOS are present in ROM, but at this point, no one has a working GEOS desktop or application suite. 

## Is there an emulator?

Yes, you can download it from via the [Official Software](https://cx16forum.com/forum/viewforum.php?f=30) section of this site or try the [web-based emulator](https://www.cx16forum.com/webemu/x16emu.html) from the home page!

## Is there a software library webpage?

Yes, just click [here](https://cx16forum.com/forum/viewforum.php?f=29) to get started! 

## What is the correct short-name for the Commander X16?

X16 or CX16 are both accepted. "CX16" is short for "Commander X16", in the same way C64 is short for "Commodore 64." But just like people said, "I have a 64", you can say "I have an X16," and we'll know what you mean.

## Will the X16 become open source?

There are no immediate plans to open source the computer. 

The KERNAL code is not available as open source, nor will it be, due to licensing issues. Commodore's KERNAL is owned by Cloanto corp, and this is not likely to change. So *you may not use the Commander X16 ROM without purchasing a Commander X16 Microcomputer.*

There are discussions of creating a fully open-source KERNAL for the Gen-2 gaming system. This discussion is ongoing, and we will update this FAQ if this changes. 

## Will there be a beta program? 

As of February 2023, The first 100 developer systems (aka Gen-1) are being assembled. These users will be the core beta test group. 

## Is this a commercial or not-for-profit venture?

The Commander X16 has been developed by a team of enthusiasts who shared David's vision to create a reliable, low cost, modern retro computer for the benefit of the retro community. The team is committed to launching the Commander X16 at the lowest price possible while still ensuring that the team will be reimbursed for out of pocket expenses incurred during the 2+ year development process (such as parts, prototypes, shipping, web hosting, etc.) David and the team are not looking to profit from the project and instead seek to strike a balance between continuing to produce the Commander X16 at an affordable price while also meeting the ongoing costs associated with continued development, manufacture, and infrastructure (e.g., website hosting, legal assistance, prototyping, deposits on parts, and so on).

## Who's been bringing the project to life?

The team has included at various points:
* David Murray aka The 8-Bit Guy - Ringleader and software development
* Kevin Williams aka TexElec - Board design/Prototyping/Manufacturing
* Christian Simpson aka Perifractic - Visual design, Branding, Website creation
* Michael Steil - ROM (KERNAL, BASIC) and Emulator
* Frank van den Hoef - VERA Video chip design
* Michael Allison - Assembler environment

Credit must also be given to our excellent Discord and forum community, who have been testing, developing, and sharing software for the X16. Without their contributions, the computer would never have made it to production.
