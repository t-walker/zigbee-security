# Introduction #

This is intended as a brief guide. Full documentation should be obtained from the datasheet, user guide, common sense, the source code, or asking for assistance.

The Api-Mote base platform was designed with a number of thoughts (enumerated below) in mind, as well as experience from both lab-research and field assessments.

## Current Status ##

A test run of 15 boards have been received and are populated. An initial firmware version based on the GoodFET project is completed. KillerBee support will be provided. I expect that adding TinyOS or Contiki support will be relatively simple for someone to do.

## Why a New Device? ##

Almost three years after beginning to work with IEEE 802.15.4 and ZigBee research and security assessments, I've gotten tired of the hardware available to interact with these protocols. There are a number of tools out there -- but none that I've worked with support all of a few core criteria:
  * inexpensive (for hackers, researchers, students, and companies alike)
  * easy to program (firmware updates should be possible via USB, not a special in-circuit-programmer)
  * available and up-to-date (in production and using modern microcontroller versions)
  * support for expansion modules and battery-power
  * support for an external antenna
  * support for cutting-edge RF research (low-level registers exposed, in support of PIP, POOP, etc)

Of the hardware that we currently support in the KillerBee project, the Atmel RZUSBSTICK requires a custom programmer, does not support battery power, and lacks an external antenna connection. The TelosB/Tmote Sky/etc provide battery power, expansion, and USB programming, but are no longer in production and use an outdated MSP430 microprocessor and FTDI chip. Further, the inclusion of humidity, temperature, and light sensors are nice for some development, but are unneeded in the base design if the focus is on RF research, security, etc. For similar reasons, as well as availability and cost, I'm not enthusiastic about the Z1 mote for this type of research. Finally, the soon-to-be-released Kisbee from Mike Kershaw will offer some nice sniffing capabilities, but some research techniques as Packets-in-Packets and Packets-out-of-Packets take advantage or registers exposed in the CC2420. Don't get me wrong -- all of that hardware has it's place -- even for use with the KillerBee project. But, as I'm developing new capabilities and proofs-of-concept for assessments, something new was needed.

# Compile and Flash GoodFET Firmware #

  1. Update/checkout to GoodFET SVN trunk (`svn co https://goodfet.svn.sourceforge.net/svnroot/goodfet goodfet`)
  1. Set parameters, make, and flash the GoodFET code:
```
$ cd goodfet/trunk/firmware
$ export board=apimote1
$ make clean install
$ ../client/goodfet.bsl --speed=38400 --swap-reset-test -e -p goodfet.hex
```

# Known Issues #

This is a first hardware revision board. If you have an error not seen here, please file a ticket or contact us.

  * Under Linux, the FTDI chip may be recognized (`lsusb`) but does not show up as a serial device. This is likely due to the Apimote utilizing a modern FTDI chip, requiring a newer Linux kernel. Ubuntu 11.10 and later, for example, come with already installed drivers that support the new FTDI. According to FTDI: "Support for the FTDI X chips has been built into the Linux kernel since the 3.0.0 release."
  * The Linux FTDI X drivers are a bit flaky. OS X FTDI drivers have no issues. We will be working with Travis to roll out a linux patch.