# DRAGON 32 RECREATION Rev 3 #

![Dragon 32 revision 3 render](Dragon32plus.png)

This project started as a recreation of the SA2120 CPU Mainboard
for the 1982 Dragon Data **Dragon 32**

Everything (excluding modifications) is taken from the SA2120
schematics. Where this version changes is that the options to
use banks of 16K DRAM is gone, you must use 64K DRAMs, with it
goes all the extra circuitry for configuring the memory for
different types of chip.

The ROM is now a single 27C256 eprom with an option to switch
between two images using JP6 or to allow the rom to be
automatically selected from the PIA.

A second ROM selection jumper is available at JP3 to be used
when a 27C512 is fitted. This swaps the value to A15 between
high and low. When a 27C256 is fitted this must be set low.

Hidden on the back of the board is a solder pad jumper (JP7) that
also needs setting to handle a 27C256 or 27C512. Bridging pad
1 sets pin 22 of the rom to ground, using pad 3 sets the
pin to use the ROM select signal shared with pin 20. When a
27C512 is fitted this must be set to pad 1.

The video circuits have been isolated from the rest of the
board to improve output quality.

A second (internal) cartridge port has been added, by way of
a 2x20 header, along with an additional +5V/Gnd pickup point
for further internal expansion.

An optional 256K banking solution is incorporated using the
design for Stewart Orchard's upgrade board and GAL design.
<https://gitlab.com/sorchard001/dragon-256k-banker-board>

## Progress ##

In the current state (3.0) none of the board is tested. This
is purely experimental although the schematics have been
tested with the previous rev 2 board and are largely unchanged.

## Modifications ##

### Joysticks ###

The two joystick ports provide a second fire button capability
wired to consecutive keyboard rows, as per the Tandy CoCo.
Unless a two button joystick is used this make no difference to
the operation of the computer. It also requires the use of 6-pin
DIN sockets, these are pin compatible with the 5-pin originals
so a regular single button joystick can still be used.

The two extra buttons can also be disabled by omitting L3 and L4.

### Parallel Port ###

A jumper (JP2) has been introduced to bypass the logic inverter
on the STROBE line. When bypassed the parallel port should
operate as a communication port for DRIVEWIRE.

### Memory Addressing ###

The board is configurable between 32k and 64k ram addressing
using jumper JP1. In most scenarios there is no reason to
disable the 64k option.

The upgrade to 256K needs the 4164s swapping for 41256s. The
pre-bridged jumper at JP5 needs cutting. The optional
components can then be fitted and should work without further
alteration.

## Substitutions ##

Many of the original components are simply unobtainable or
just very hard (and expensive) to locate. The transistors
will need modern substitutes as the BC141, BC212 and 2N2369
are all obsolete but thankfully these are fairly run-of-the-mill
transistors and shouldn't cause any particular issues.

The video op-amp SFC2318D at position IC10 is especially
hard to find and this one component can easily double the
price of populating the board if an original is used...
I've identified a Harris HA-5111 as a likely candidate, it
is an audio op-amp rated for upto 40MHz so plenty of
bandwitdh for a simple PAL/NTSC video signal. There are of
course lots of other single channel op-amps out there in a
dip-8 format but they tend to be expensive (as in *really*
expensive) possibly cheaper than a real 2318D but not by
much, some are stupidly expensive (nearly 100x that
2318D). The HA-5111 should be about £0.90

The CPU, SAM, PIAs and VDG are all fairly easy to obtain online
and possibly even new (MC6821s are still made and there
are lots of compatible alternatives). A and B rated components
should all be usable but make sure the processor is an "09e".
The Hitachi HD6309 is usable but may cause crashes in some
software due to lazy coding

The 4000 series logic chips are particularly tricky - some
have modern equivalents. The MC14053 and MC14050 can be
replaced with modern CD4000 series chips. The MC14529
was replaced with a CD4000 series logic chip but even that
is now obsolete with no valid replacement

The LM1889 is another hard to find chip but still reasonably
cheap online when found.

### The Future ###

As these parts become harder to find it is inevitable that
replacements and redesigns will be needed. Abandoning the
original composite video output circuits and moving to a
(more) modern RGB or VGA output instead removes a big
chunk of the more troublesome hardware, notably the LM1889
and SFC2318 along with a number of other common logic chips.
If a composite output is still required an ADR724J can be
used to generate the necessary signal, all in one chip

A cheat replacement for the 6847 exists, using a raspberry
pi pico but this could easily be reduced even further an
FPGA (assuming such chips are readily available again).

The one thing that isn't so quickly removed from the
equation is that MC14529 - a dual 4-channel data
selector. Onsemi and Harris used to made the CD4529
that replaced the original MC14529 and it is only fairly
recently that the chip became obsolete so there is
stock out there but the chip is somewhat specialised and
as such really isnt easily substituted even with a modern
SMD package.
