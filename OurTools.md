# Introduction #

This page lists the current Api-do tools, and explains their uses.

# KillerBee #

KillerBee is a Python based framework and tool set for exploring and exploiting the security of ZigBee and IEEE 802.15.4 networks. Using KillerBee tools and a compatible IEEE 802.15.4 radio interface, you can eavesdrop on ZigBee networks, replay traffic, attack cryptosystems and much more. Using the KillerBee framework, you can build your own tools, implement ZigBee fuzzing, emulate and attack end-devices, routers and coordinators and much more.

This is kept in a separate repository, and can be accessed at:
  * http://code.google.com/p/killerbee/
  * `svn checkout http://killerbee.googlecode.com/svn/trunk/ killerbee-read-only `

The KillerBee framework was launched by Joshua Wright, and has undergone major updates by Ricky and Ryan of the Api-do project. It is currently considered the main toolkit of the Api-do project.


# Scapy dot15d4 #

We have added support for the IEEE 802.15.4 layer to the popular Scapy packet manipulation software. The file is `layers/dot15d4.py` which is currently maintained in the `scapy-com` (community) repository.
  * http://hg.secdev.org/scapy-com
  * Uses [Mercurial](http://mercurial.selenic.com/): `hg clone http://hg.secdev.org/scapy-com`

(This layer has also been used as the basis for the 6lowWPAN layer added to Scapy by another maintainer.)


# KillerBee "Extras" Tools #

_In this repository, under_ `tools_killerbee_extras`.

These are tools developed on the KillerBee framework, but which may have extra requirements, are in alpha, or otherwise do not belong in the main KillerBee repository.

## OpenEar ##

OpenEar seeks to assist in data capture where devices are operating
on multiple channels, or fast-frequency-hopping, etc. It expects
multiple interfaces, preferably one per 802.15.4 channel, to use
and assigns them sequentially across all channels. It optionally
interfaces with a gpsd daemon (reading from a standard serial GPS
device) to add GPS data.

## zbWarDrive ##

zbWarDrive is a tool that seeks to achieve optimal coverage of networks
with using only the available capture interfaces. It discovers
available interfaces and uses one to inject beacon requests
and listen for respones across channels. Once a network is found
on a channel, it assigns another device to continuously capture
traffic on that channel to a PCAP file.