# SFS-Laptop

![](https://github.com/bobbybudnick/SFS-Laptop/blob/master/WIN_20171210_101950.JPG)
![](https://github.com/bobbybudnick/SFS-Laptop/blob/master/WIN_20171210_102306.JPG)
![](https://github.com/bobbybudnick/SFS-Laptop/blob/master/WIN_20171210_102521.JPG)
(Github does not handle EXIF orientation data correctly)
TM1 running Devuan with Steam and TM2 running Freebsd  

TM1 design goals
-----
The goal was to use the best possible desktop hardware for building a laptop.  This meant using an AMD APU for simplicity and speed.   The 1366x768 resolution monitor was chosen first for it's size but it also makes ultra settings possible on most games.  There is a full size PCI express slot and probably just enough room for a low profile graphics card.  A graphics card would send the heat and power budget through the roof and would require a fan and power supply redesign.  The screen closes flush with the case like an actual laptop.  The use case for this computer is a gaming laptop.

TM2 design goals
-----
The goal was to salvage existing desktop hardware from previous builds that have been left sitting because I prefer to not build or operate desktops anymore.  The motherboard does not include a full size PCI express slot but does have a small slot to accomodate a business class graphics card for a future upgrade.  Extensive fan modifications would be required for the screen to close completely flush but it is close enough using just the stock AMD CPU fan.  The use case for this computer is a Unix workstation.

TM1 hardware
-----
Asrock AB350 Gaming Mini ITX - 5 USB type A, USB-C, 2 HDMI  
AMD A12-9800E APU  
2x8GB PNY Anarchy DDR4  
1x Sandisk 120GB SSD  

TM2 hardware
-----
Zotac 880G-ITX Mini ITX - 6 USB type A, HDMI, DVI  
AMD Phenom II 945 (95W, AM2+)  
1x8GB PNY DDR3  
2x Sandisk 120GB SSD (ZFS mirror configuration)

Extra software
-----
The OS software itself has not been heavily customized.  
These scripts implement basic power management - read the source carefully:  
https://github.com/bobbybudnick/SFS-Laptop/blob/master/LAPTOP_POWER  
https://github.com/bobbybudnick/SFS-Laptop/blob/master/LAPTOP_POWER_STUB

Common hardware
-----
Sceptre 16" 1366x768 monitor  
BUD Industries CU-712-A aluminum box  
Permanent Industry 20cm FPV flat HDMI cable  
2x Philmore DC extension cord (male-charge cable,male-internal,female-charge port)
HTRC 100W touch screen multi charger  
Drok 3W micro audio amplifier  
right angle 3.5mm audio cable (chopped in half)  
Bulushi 60x30mm blower fan  
Witbot 40x40x10mm square fan  
small speaker (any kind will do)  
up or down or left or right angled micro USB (for keyboard charge)  
Rii Mini K12 keyboard with touchpad  
Vandesail ATX power supply kit (wires and buttons)  
PicoPSU WI-25 120W unregulated input DC-DC power supply  
Drok .28" voltmeter  
Monoprice P4 to ATX power supply adapter  
Cable matters molex to SATA power supply adapter  
Sienoc molex y splitter  
2x Home Depot heavy duty door hinges  
2x Duracell SLAA12-5.1A 5.1AH SLA batteries

Hardware notes
-----
You do not have to have all the hardware listed.  Just substitute what you have that you think will work.  A car battery charger instead of the fancy charger or a paper box you made instead of the fancy aluminum box.

Hinge notes
-----
place in vice and grind off 1/3" from one hinge  
place in vice and bend both hinges at central hole to about 30 degrees  
place in vice and drill a 1/8" hole 1/3" above central hole between tip  
place in vice and crush with the help of a breaker pipe to increase friction  
(may be necessary to use a small screw between vice teeth and hinge)  
make hole in wrap and attach hinges to monitor with 1 screw each  
lay hinge flat below monitor and tape accounting for any case unevenness  
carefully bond monitor/hinge assembly square to case and attach wires

Wiring notes
-----
1.  Battery cap cover removed for clearance and tape partially placed over battery vent holes.  Batteries wired in parallel with silver wire and gold connectors and the connectors are bent and the batteries are then carefully squeezed together.  This allows the battery assembly to barely fit between the side of the case and the edge of the motherboard.  Wire the voltmeter, male barrel plug, and female barrel plug in parallel with the batteries also.
2.  Wire the other male plug to the battery charger.
3.  You can save space and manually cut the connectors and wire everything in like in TM1 or use a series of Y cables and splices such as in TM2.  Particularly the micro USB for charging the keyboard should be wired to 5V (red), the audio amplifier wired to 5V (red), and the chopped monitor power plug wired to 12V (yellow).  You can take apart the plug that powers the Pico PSU and steal that to drive the P4 plug or you can buy a molex to P4 connector but you will need one or the other.  Without a graphics card, the extra 4 pins on the 24 pin connector and/or any 8 pin connectors are not needed.  You may not have enough connectors for fans on such a small motherboard so wire those in to the appropriate power supply as well.

Dual monitor notes
-----
The monitor is a lesser and different aspect ratio than most TVs.  Additionally xrandr cannot drive 1366x768 on the monitor with a second monitor connected for some reason. This command will clone both monitors and attempt to show the full 1920x1080 TV image in a compromise 1024x768 resolution on the monitor:  
xrandr --output HDMI-0 --mode 1024x768 --scale-from 1920x1080 --same-as DVI-0

3D printing
-----
This model requires an extension to the case to accomodate the monitor height.  It is created in the form of a decorative 3D printed palmrest.  The pieces are sized for a typical 3D printer and should be glued together and then glued to the front of the case.  See the geometry problem section for more information.  
https://github.com/bobbybudnick/SFS-Laptop/blob/master/SFS-Laptop-Keyboard-Support-6.stl - Print x1  
https://github.com/bobbybudnick/SFS-Laptop/blob/master/SFS-Laptop-Keyboard-Support-7.stl - Print x2


Storm clouds on the horizon
-----
4k with APU will be difficult  
continued availability of 16" monitors

Future hardware
-----
device to measure battery voltage and export to OS as USB UPS  
affordable 12v lithium iron battery in a compatible form factor  
Ryzen APU  
mini antennas for the built in wifi and Bluetooth

Tools required
-----
philips screwdriver  
wire stripper  
ultra heavy duty vise  
metal cutting shears  
soldering gun  
drill  
scissors  
3M 30 PSI mounting tape  
electrical tape  
thermal tape  
chrome mirror silver vinyl wrap  
shielded wire  
1/4" spade connectors  
dremel or grinder

The geometry problem  
-----
the premise is that a laptop monitor entirely covers the base  
most new monitors are 16:9 instead of 4:3  
motherboard is 7x7 inches square instead of rectangular like a laptop  
keyboard must go in front of case instead of top for cooling and space  
this means monitor height must be 7 + X inches for the keyboard  
a normal keyboard is 7 inches long  
this means monitor height must be 14 inches  
this equals about a 21 inch monitor which is too big heavy and powerful  
a short keyboard is 3.5 inches long  
this means monitor height must be about 10.5 inches  
this equals about a 16 inch monitor which is ok for laptop gaming  
a 16 inch monitor is about 15 inches wide so the case must be also  
this is less of a problem with 4:3 but modern games expect a 16:9

Geometry problem part deux
-----
case should be at least 7" long for motherboard and wide enough for gaming monitor  
15-16" monitors are in the 9-10" height range so exceed the motherboard length  
even a 12" monitor is slightly large at 7.4"  
so the case or keyboard/case must be longer to accommodate a gaming monitor  
keyboard can go in front of case to increase length but this comes with problems:  
looks like a 70-80s luggable PC  
keyboard must be extra short  
keyboard must be tilted to save space even when extra short to be in the 3" range  
monitor does not close flush with keyboard when tilted  
(keyboard on top comes with the problem of fitment between case and screen)  
this leaves a choice:  
build with keyboard in front and tilted?  
or  
build with keyboard on top and size case appropriately/add 3d printed extension?

Geometry problem implications
-----
a netbook device can be built with an 11" screen and no palm rest extension  
for the 16" device the keyboard on top idea won out - too awkward to mount in front

Extended high load dilemma
-----
Problem: long freebsd compiles fail with various shutdowns and reboots  
red herrings:  
any other step down converter - wi-25 integrates this  
higher power picopsu - wi-25 is not overloaded  
knacro 144w stabilizer - failed - high pitched noise and voltage drop  
drok 150w stabilizer - failed - loose connectors and voltage drop  
step up/down converters (stabilizers) in parallel - not necessary  
larger charger - will not overcome inadequate wiring  
solutions:  
tm-1 failed because of inadequate charger - needs 5 amps only had 3.75 amps  
tm-2 failed because of inadequate wiring - needs 14 awg only had 18 awg  
BONUS - high power 80mm fan review:  
sanyo denki sanace 80mmx25  
b-gears bblaster 80mmx25  
vantec tornado 80mmx38  
Delta TFB0812UHE Sidewinder 80mmx38

