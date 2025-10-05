# Dragon Rev 3 Build Instructions #

## Introduction ##

This is a rough guide on how to assemble the 
Dragon Rev 3 board. It assumes you have 
collected together all the parts you will need 
using the bill of materials in the project 
repository.

## Preparation ##

Any big PCB build requires planning and 
preparation to make things go smoothly. The 
Dragon Rev 3 needs a significant number of 
components, some of them can be hard to obtain.

The choice of video and SAM components make a
substantial difference to how the board is built
and it is worth starting here and working back
from these choices.

Clean the mainboard to remove contaminants, soapy
water first, dry and then a wipe down with 
isopropyl alcohol.

Make sure you have a good supply of solder, a
temperature controlled soldering iron. If you
are using lead based solder set the temperature
to between 320C and 370C - this depends on the 
exact solder composition and the iron being used. 
The board can tolerate higher for lead-free solder.

A ready supply of solder flux can be really
helpful if you find yourself having to remove a
component from the board.

You will need short tipped, angled wire cutters
for trimming the component leads after soldering.
Don't cut the leads right down to the board or deep
into the solder.

It is also a good idea to have a multimeter on hand
to check component values and test for any shorts
after soldering.

The project repository on GitHub includes an
interactive Bill Of Materials that allows you to
cross-reference components against position on
the board (and mark off all the parts that you've
fitted). To use this download the ibom.html file
to your computer and open it from the local file
system (this should open up a web browser).

If you can't or don't want to use the iBOM it is
a good idea to print off the Dragon Assembly 
PDF on to large form paper and mark the positions 
off from there as they are fitted to help avoid
getting lost.

## Build Order ##

It is advised to work with the lowest profile
components first - resistors, then diodes, then 
capacitors, transistors, etc.

Leaving the chip sockets until last helps as they 
tend to get in the way when fitting other items.

### Build Options ###

The board can be built to three different 
configurations:

    1. 64K with standard SAM
    2. 256K with updated 74LS785 SAM
    3. 512K with SAMx8

### SMD Parts ###

Build option 1 and 2 require that the surface
mount resistors North of the SAM position must
be fitted.

For option 2 the capacitors at C12 and C10 are
required.

RN1 is not required if RN2 is fitted (and
vice-versa).

The remaining SMD parts are required for all
three build options.

### Through Hole Resistors ###

Fit resistors first making sure the solder is
forming on both sides of the board, not just
the bottom.

Regardless of board configuration all of the
resistors should be fitted.

Save the two potentiometer resistors RV1 and RV2
for later.

### Diodes ###

Fit all 9 diodes in much the same way as the
resistors but making sure the polarity marking
matches the board. D4, D5 and D6 all require
the cathode to face up. The cathode should be
connected to the pad labelled K

### Inductors ###

If you want to have the option of two button
joysticks (non-standard but used in some
CoCo games) then you'll need to fit all 4
inductors (L1-L4).

If you only want single button joysticks you
only need to fit L1 and L2.

Soldering is the same as for resistors.

### Through Hole Capacitors ###

If you are building option 1 or 2, C14
to C21 must be fitted.

Other than this fit all capacitors making 
sure that the tantalum and electrolytic
capacitors are fitted the right way around.

Tantalum capacitors have a + symbol next to
the positive side. Electrolytic capacitors
have an arrow pointing to the negative side.

The board is marked to show a + next to the
positive side and a filled semicircle on the
negative side.

It is worth saving two of the long legs
after trimming the legs back. You can use
these for securing the crystals.

Save the trim pot capacitor C7 for later.

### Transistors ###

TR1 is an NPN transistor driving the coil of
the cassette remote relay. It uses a wide
TO-92 footprint.

Make sure the transistor is fitted the
right way around according to the outline
printed on the board.

### Jumper Posts ###

The board has 5 sets of jumpers that
need to be fitted with clips.

JP1 sets the RAM size if the board is
to be used as a Dragon 32.

JP2 controls whether the printer strobe
signal is inverted or not. For regular
printer use the "printer" option must
be used. If the strobe is to be used as
a bit-bang serial port (for drivewire
or CoCo compatibility), the "parallel"
option must be used.

JP3 allows you to control pin A15 of the
ROM. This is only relevant if the ROM
is a 27C512.

JP6 controls pin A14 of the ROM. There are
3 options, high, low or PIA controlled.
The PIA controlled setting is used by the
Dragon 64. This is only of use for a
27C256 or 27C512 rom.

JP8 configures the keyboard matrix
connections to switch between Dragon
and CoCo standards (using a Dragon
keyboard).

### Solder Jumpers ###

JP5 is used to fix the signal to Z8.
This is useful if 64k chips are used or
256k chips need to be used without a
74LS785 SAM.

### Connectors ###

The keyboard connector can be vertical or
a horizontal as desired. Original boards
used a vertical orientation but later boards
and the D64 moved to horizontal to avoid 
clashing with the keyboard itself. I
recommend using the horizontal option as
it leaves more space for connectors.

The joystick, serial and cassette port 
connectors have an overlapping design, if 
you want to get them nicely lined up start 
with the 5-pin cassette socket and tack it 
in place on a single pin.

You can then do the same with the two
joystick ports (6-pin or 270deg 5-pin)
and align them to the edge of the board.
This can be a tricky task so don't rush
it.

The power board connector needs to be 
fitted with the vertical guide towards
the bottom of the board (assuming you
don't have a plain pin header).

The cartridge port connector can be very
entertaining to fit. The pins like to
bend in transit so you'll likely find
yours do not line up on the first attempt.
It is very easy to bend the pins on the
cheaper connectors resulting in the pin
not fitting properly. Double check that
all pins have fitted through the mounting
holes on the board before soldering.

### Variable Components ###

RV3 needs to be fitted at an angle if
it is adjusted from the side.

### Crystals ###

Assuming you have the larger housed
crystals you will need to bend the legs
so the crystal lies flush with the board.
This is not essential but it is 
recommended. Two additional solder points
are provided for each crystal to allow a
wire to be formed over the body and 
prevent the crystal being moved. A
convenient source for the wire to do this
is the long legged capacitors you 
hopefully saved earlier.

### Sockets ###

When fitting the sockets make sure the
orientation is correct and the notch of
the socket matches the outline on the
board.

Most of the chips are aligned with the 
notch to the top of the board but RAM, ROM
and SAM chips have the notch towards
the bottom of the board.

As with the header pins it can be a 
little tricky to get the sockets to fit
flush and aligned. Tacking one pin at 
each end of the socket to hold it in
place and then heating one pin while
adjusting the position gives a good
result.

Be very careful to avoid bridging the
pins on the socket while soldering.
It is worth checking with a multimeter
to double check as the pins can 
bridge on the top of the board, hidden
underneath the socket.

### Before Fitting Chips ###

As a precaution, before fitting the
chips to the board it is worth making
sure none of the voltage pins of the
power board connector are shorted to
ground (that would be bad).

### Fitting Chips ###

Make sure you have a grounding strap on your
wrist (or ankle) and it is actually connected
to a proven ground point (radiators are a 
good source). The LM1889 and DRAM chips are
very susceptible to static discharge! Leave
these until last.

Fit all your chips paying very careful attention
to orientation, notches must match with the
board. Fitting chips the wrong way round will 
likely destroy them when the power is switched
on.

### Keyboard Connection ###

The keyboard must be fitted to the right of
the arrow on PL1. The two pins to the left
are used for providing power to the keyboard.

### First Power Up ###

When powering on for the first time always be
prepared to turn the power off in a hurry. 

If anything smokes or looks to be getting hot, turn
the power off immediately. You most likely have a 
short (you did check for shorts?) or a polarised
capacitor in backwards.

### Troubleshooting ###

If the relay doesn't click on powering up (assuming
you fitted one) and there is no picture at all, the
chances are the CPU is not cycling. Either it hasn't
come out of reset or is being locked up by another
line.

A bad PIA can cause the CPU to run very, very slowly
by generating interrupt requests at high frequency.
Try removing the PIAs and try running without them.

Check the reset line is going high (about 5V) and the
same again for halt, mrdy, extal, xtal, bs and ba pins.
If any of these are low it can stop the CPU operating.

Check the Q and E pins are oscillating at (about) 
0.9MHz, no clock means no CPU. You can also check
the SAM is receiving the full 14MHz clock from the
crystal.

If all is well with those pins, test the address and
data lines with an oscilloscope or logic probe. You
should see activity with the lines moving from high
to low.

If the CPU is doing nothing it may be faulty, either
test the CPU in a known good machine or try a different
CPU.

If the CPU is proven good you can turn your attention
to the SAM, this governs the CPU activity and memory
addressing. I've yet to see one fail but if it does
you have no hope of getting the computer to work until
it is replaced. More likely the SAM is not getting 
the input signals it needs to operate.

Check the clock input and the Q/E output of the SAM.
If the clock is present and correct, check the SAM 
is generating RAM addressing signals on the Z lines 
and RAS/CAS lines.

The SAM also decides what device is being addressed
it does this though a multiplexer at IC33. Check the
operation of this chip carefully. 

## Options ##

### Keyboard ###

If there is no need to support a CoCo keyboard setup
the GAL at U2 can be omitted. Instead just connect
the pins across the chip. Don't connect the top pair
as these are power and ground. RN1/2 can also be
omitted.

If it is required the GAL can be a 16V8 or 22V10, in
both cases the chip must be fitted to the left end
of the socket. RN1 or RN2 must be fitted if a GAL is
used.

### Serial Port ###

The RS232 setup can be omitted if the board is to
be used as a Dragon 32 or CoCo. In this scenario
U1, U12, IC38, IC39, XL3 and PL9 can all be omitted from
the build.

### Video ###

The board is designed to work with separate plug-in
video boards. At the simplest end these are either
NTSC or PAL composite output. More complex solutions
can be switched between formats, include the lower-case
extension or extended video options.

The video board is *not* part of this design and needs
to be obtained separately.

### SAM ###

The original SN74LS783 / MC6883 SAM chip limits the 
board to using 4164 64kb x 1 DRAM chips with 128 
row refresh (256 row refresh will not work).

A later, optional, version of the SAM chip is
available. Still with the Motorola MC6883 code but
with the logic identifier SN74LS785. These extend
the compatibility options to use 256 row refresh
DRAM chips. This version of the SAM chip is needed
for the 256kb x 1 DRAM chips. Obtaining this version
of the SAM can be tricky, if you plan to build the
256k version of the board please make sure you have
the chip first to avoid disappointment.

It is possible to use a modern replacement for the
SAM courtesy of Ciaran Anscomb. The preferred 
option is the SAMx8 plugin board that replaces the
SAM chip completely (and RAM).

See https://www.6809.org.uk/dragon/samx8/ for more
details.
