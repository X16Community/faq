<p align="center"><img src="about.png" alt="About Commander X16" /></p>

## What is the Commander X16?

Welcome! 

The Commander X16 is The 8-Bit Guy’s dream computer, designed to evoke the same fondness and nostalgia many of us had for 8-Bit computers, while retaining closeness to the hardware from a programming perspective (unlike the Raspberry Pi and others). More than that, it is intended not only as an educational tool but to solve some of the issues of finding an 8-Bit system to tinker with today: namely ever-increasing costs, auction site price gouging/sniping, lack of replacement parts, and unreliability of 30-year old hardware.

While many folks might have their own definition of their dream computer, this is David's.

The X16 is made entirely with parts that are readily available today, ensuring perpetual availability without reliability issues, but in keeping with David's vision, it will house a real CPU rather than using emulation or an FPGA recreation of a processor. Running Commodore BASIC V2 (with some additions), the X16 will be inexpensive enough to allow a critical mass of users to create an expansive software ecosystem, but simple enough that a single person can understand all of the chips and components that allow that software to run.

Three models, or "Generations" of the computer are planned under the "Commander X16" brand umbrella. All of the models will run the same software and will feature full support for keyboard, mouse, and game controllers. 

* **Gen-1**: This is the Developer Edition, with 4 expansion slots, giving you flexibility for hardware and software development.
* **Gen-2**: The Console Edition: Is it a computer or a game console? Yes. G2 will be smaller and less expensive, but it is still a complete Commander X16 albeit with more SMD parts and fewer expansion slots.
* **Gen-3**: The "Elite/Edu" model will be similar in size to a Rasbperry Pi SBC. This will be inexpensive enough to be sold to schools and colleges for STEM programs.

As the G2 and G3 systems become available for sale, you will be able to buy all three systems.

Please watch [Commander X16 video playlist](https://www.youtube.com/playlist?list=PLfABUWdDse7bKGFshxR0itdHBhjUj86SX) for more details.

## Who is The 8-Bit Guy

David Murray, AKA "The 8-Bit Guy" runs a successful YouTube channel centered on vintage computing. He also dabbles in music, electric car culture, off-grid energy production, computer refurbishment, and resale. 

His web site is [https://www.the8bitguy.com/](https://www.the8bitguy.com/)

## Specifications

Commander X16P Features & Specifications (subject to change)

* CPU
  * WDC 65C02S @ 8 MHz
  * 40-pin DIP package
  
* RAM
  * 40K of "Low RAM":
    * As 39.75K + 256 bytes of IO space
    * 8 IO spaces of 32 bytes each; one for the VERA, one for the VIAs, one for the audio
  * 512K of "High RAM" standard:
    * As 64 banks of 8K
    * Expandable to 1 MB, 1.5 MB, or 2 MB by adding additional RAM chips to 3 empty sockets for up to 
    256 banks of 8k High RAM
  * ROM
    * 512K of Flash ROM
      * As 32 banks of 16K
      * Expandable to 4MB of ROM or RAM via a cartridge or expansion card. 
  * Standard Commodore Kernal
  * CMDR-BASIC
    * Microsoft BASIC 2.0 (Complete, identical to Commodore 64 and VIC-20)
    * Commander X16 extentions
  * Machine Language Monitor (Supermon and CODEX)
  * ROM can be flashed in place. 
* Expansion
  * Four expansion slots with access to CPU databus (X16 Developer Edition)
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
  * Yamaha YM2151 sound chip (8 channels of 4-Op FM)
  * PCM audio on VERA (Up to 48kHz, 16-bit stereo)
  * PSG of 16 channels with 4 selectable waveforms
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
* RTC: Microchip MCP7940N
* Board power consumption: ~15W
* PSU: TBC

## When will the X16 be released?

After a run of pre-release boards, along with an initial limited official run, the X16 Developer Edition is 
now readily available on texelec.com for $349.99! It is expected it will be continually available though 
be aware it may take some time for your X16 to be assembled and delivered to you based on the production
schedule.

## How much does it cost?

The Developer Edition is currently $349.99 US with 512k of RAM and a single VIA. Extra memory and a second VIA 
for the User port is optional and can be added at the time of purchase. 

## Where can I get it? 

The Commander X16 can be pre-ordered from [Texelec](https://texelec.com/product-category/commander-x16/).

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

## Why VGA instead of HDMI?

Licensing, simplicity, and the ability to run both LCD and CRTs on the X16.
A future VERA with a built-in HDMI-like output may be available in the future.

## Will it hook to my CRT TV, like a Commodore 64 or ZX Spectrum?

In addition to VGA, the computer has composite, and S-Video outputs. So
you can connect to just about any NTSC compatible display. However, you'll
want to restrict yourself to the 40-column text modes, as the 80-column modes
are not readable in composite color.

## What sort of expansions would be possible?

There are 4 expansion slots on the Developer Edition and some of the unused VIA pins are
available on pin headers. Expansion slots have the full address and data
bus, plus up to 5 shared IO Select lines.

Expansion cards can hold ROM, RAM, sound, video, and communications interfaces.
Some planned devices include cartridge games, a MIDI/serial interface card, a
network interface card, and memory expansion cards with 3.5MB of additional RAM.

## What sort of joysticks will you use and why?

SNES style game controllers. The SNES interface uses fewer wires and allows for
more buttons on each pad. 

## Will a floppy or CD-ROM drive be included?

The system will store data on SDHC or SDXC memory cards. Older SD cards with 
less than 2GB may not be supported.

In addition, Developer Edition system will include a Commodore compatible
IEC port, to allow reading from a user-supplied Commodore 1541, 1571, or 1581
diskette drive.

## Will it support cassette drives?

No. There are no plans to support a cassette drive, although it's possible that
someone may decide to build a cassette interface on an expansion card or as an
attachment for the User port.

## What do you need help with the most?

Write software for the system. The more software we have available, the more
people will want to use the computer.

Expansion and interface devices are also highly requested: network interface,
MIDI interface, and RS-232 interfaces are at the top of the list.

## Will it be available as a kit/pre-assembled/motherboard only?

It is unlikely, at this point. If you want a kit system, you will want to join
Discord and talk to some of our community designers who are building their own
versions, including kits with all the needed parts included. 

## Will a keyboard be included?

Yes. A custom Perixx keyboard has been designed by Perifractic, based on the
[PERIBOARD-409](https://perixx.com/products/periboard-409-u-w-wired-mini-keyboard-75-quiet-keys-in-white).
The keyboard will resemble the late model Commodore 64C keyboard, with PETSCII
glyphs and a white case.

## Why PS/2 Keyboard and not USB?

USB is much more complicated to implement, and it's just not a good fit for an
8-bit system. Future systems might include a simple USB host driver, but they
will only work with basic keyboard devices that do not have internal hubs,
RGB lighting, and so on.

## Will a case be included?

The official case is made by [Lazer 3D](https://lazer3d.com/x16-p/). The design
is still under revision and will be modified for the second run of developer
boards, with a cartridge port on the case's right side.

As the Developer Edition is mATX, most mATX cases should work. There are also
community members working on their own cases, some of which may be available
from them directly or available under a free license (e.g. Creative Commons)
for folks that have the means can make their own.

## Why not a wedge case?

Cost and configurability. Anyone is free to design and manufacture a compatible keyboard case,
however.

## What about expansion cards for each generation? 

* Gen 1 "Developer": 3 expansion card slots and one right angled cartridge slot
* Gen 2 "Console": One expansion/cartridge slot.
* Gen 3 "Elite": TBD

Note: all 3 systems are planned to be produced concurrently. Gen 2 and 3
will not _replace_ Gen 1. Instead, Gen 1 ("Dev") is expected to be used for game
development, testing, and power users. Gen 2 ("Console") will be the primary consumer edition for
home users. Gen 3 ("Elite/Edu") system is intended to be cost-reduced, with the minimum
number of parts, primarily meant to be used as a companion device for teaching
6502 machine language and retro games development.

## How about a mouse?

A PS/2 mouse is included, or you can use any compatible PS/2 mouse.

## Will it be available in the USA, Europe, & beyond?

We hope to offer international shipping from the USA. Note that the official
keyboard will use the US ANSI layout, but the computer is be compatible with
several layouts.

## Will user guides be included?

Perifractic designed a nostalgic traditional spiral bound Getting Started guide with an awesome (top secret) cover co-created by him and Trevor Storey. The manual includes a BASIC programming guide. The rest of the team are currently finishing up the finer details of the manual. Further docs are already available in the Downloads section of this website. The working title for the spiral bound guide is “Just the BASICs: Getting started with the Commander X16”. There will also be “Assembling Assembly” and a programmer’s reference guide. PDFs will likely be an option.

## Why not use the Parallax Propeller chip, FPGA, Arduino, Teensy, Pi Pico, etc?

We will not be using the Propeller for these reasons:
Most of its capabilities are on par with or inferior to our custom FPGA.
There are issues when putting it on the system bus related to CPU read attempt speed call and answer
The Propeller costs the same as if not more than the faster FPGA

<!-- tomxp411: I like the thought, but it doesn't feel right in a FAQ.

## Seriously, if the X16 doesn't have X, I don't want it.

At this stage the design has been ratified with hardware in people's hands and
changes to the base hardware are very unlikely.

Engineering is ultimately an exercise in compromise. To meet the goals of the
project at a cost target, not everything and the kitchen sink could be included.
Likewise, the X16 represents a stable platform with which to write amazing
software. If it had too many features (like a bunch of FPGA accelerators) it
would be harder to use and compatibility, testability, etc. would have been more
difficult.

Building a community around the X16 is just important as the hardware and given
the educational goals of the X16, this meant the base system is static and
simple.

That said, one of the benefits of the X16 is that it does have a fully capable
expansion bus available for folks to augment and extend it in many ways. This
allows for a lot of possibilities! Even CPU accelerator cards are possible!

If the X16 isn't your cup of tea, that's totally ok! There are plenty of retro
options, both new and old, available and we hope you find one that suits you!

--> 

## Will there be a GUI?

No. The main interface is good old BASIC, with some text based utilities
accessible through BASIC commands or the main menu. (Which you can get to
with the MENU command in BASIC.)

## Is there an emulator?

Yes, you can download it from via the [Official Software](https://cx16forum.com/forum/viewforum.php?f=30) section of this site or try the [web-based emulator](https://www.cx16forum.com/webemu/x16emu.html) from the home page!

## Is there a software library webpage?

Yes, just click [here](https://cx16forum.com/forum/viewforum.php?f=29) to get started! 

## What is the correct short-name for the Commander X16?

X16 or CX16 are both accepted. "CX16" is short for "Commander X16", in the same way C64 is short for "Commodore 64." But just like people said, "I have a 64", you can say "I have an X16," and we'll know what you mean.

## Will the X16 become open source?

There are no immediate plans to open source the computer. 

The KERNAL code is not available as open source, nor will it be, due to
licensing issues. Commodore's KERNAL is owned by Cloanto corp, and this is not
likely to change. So *you may not use the Commander X16 ROM without purchasing a
Commander X16 Microcomputer.*

There are discussions of creating a fully open-source KERNAL for the Gen-2
gaming system. This discussion is ongoing, and we will update this FAQ if this
changes. 

## Is this a commercial or not-for-profit venture?

The Commander X16 has been developed by a team of enthusiasts who shared David's
vision to create a reliable, low cost, modern retro computer for the benefit of
the retro community. The team is committed to launching the Commander X16 at the
lowest price possible while still ensuring that the team will be reimbursed for
out of pocket expenses incurred during the 2+ year development process (such as
parts, prototypes, shipping, web hosting, etc.) David and the team are not
looking to profit from the project and instead seek to strike a balance between
continuing to produce the Commander X16 at an affordable price while also
meeting the ongoing costs associated with continued development, manufacture,
and infrastructure (e.g., website hosting, legal assistance, prototyping,
deposits on parts, and so on).

## Who's been bringing the project to life?

The core team has included at various points:

* David Murray aka The 8-Bit Guy - Ringleader and software development
* Kevin Williams aka TexElec - Board design/Prototyping/Manufacturing
* Christian Simpson aka Perifractic - Visual design, Branding, Website creation
* Michael Steil - ROM (KERNAL, BASIC) and Emulator
* Frank van den Hoef - VERA Video chip design
* Michael Allison - Assembler environment

Credit must also be given to our excellent Discord and forum community, who have been testing, developing, and sharing software for the X16. Without their contributions, the computer would never have made it to production.
