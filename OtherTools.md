# Introduction #

This page contains a listing of other known ZigBee and 802.15.4 targeting security tools, as well as links to them, their maintainers descriptions of the tools, and our updates as to the current state of the tools (last we checked them).

The Api-do project aims to make use of existing tools when possible, and not duplicate effort. In this regard, we also will sometimes write why our tool differs from a specific project, and why we feel that the Api-do tool offers an advantage.


# Other 802.15.4/ZigBee Security Projects #

## 15dot4-tools, by c\_oflynn ##
http://sourceforge.net/projects/dot4-tools/
  * "A group of useful tools for working with 802.15.4 networks. Currently includes a sniffer that interfaces with Wireshark in Windows/Linux (and maybe Mac OS X too), allowing you to do 802.15.4, ZigBee, and 6LoWPAN Sniffing."
  * Have not tested. Appears to have a named pipe for Wireshark, as well as a GUI application allowing for setup of sniffing and a "spectrum analyzer" graph showing RSSI on different channels.
  * We provide this frame->Wireshark functionality in KillerBee via the standard zbwireshark tool.

## Wireshark Zigbee Utility, alpha, by jakobt ##
http://sourceforge.net/projects/wiresharkzigbee/
  * "Utility enabling easy capture and monitoring of Zigbee frames in Wireshark. This simple utility program implements a named pipe between Wireshark and the Freescale MC1322x USB dongle (support for other devices can relatively easily be added)."
  * We provide this frame->Wireshark functionality in KillerBee via the standard zbwireshark tool.

## WSN Analyzer - NSniffer, by nsniffer1, wjianqiang6 ##
http://sourceforge.net/projects/nsniffer/
  * "NSniffer is a platform independent packet analyzer for IEEE 802.15.4, Zigbee, 6LowPan, SimpliciTI, SimpLink, MiWi, ANT etc. mainstream short range wireless protocol for wireless sensor network."
Have not tested. Unclear what is implemented and what hardware capture devices are supported. Is written in Java.

## zigbee sniffer, alpha, by vpanov ##
http://sourceforge.net/projects/zsniffer/
  * "software to capture 802.15.4 packages from the air and show all frames decoded with ZigBee Pro specification. chipcon cc2420 board is supported, loading Daintree and Chipcon capture files. Linux and windows are tested to built."
  * Have not tested. Appears to be a GUI package, getting data off the CC2420 board, and doing a Wireshark-like decoding and display of packets.


# 802.15.4/ZigBee Network Stacks #

## Universal ZigBee Stack, by brandon\_cho, shban, youyoungchang ##
http://sourceforge.net/projects/zigzagbee/
  * "The purpose of this project is to implement ZigBee Phy, Mac, Network, Security and Application Stack on LINUX Kernel and 8Bit Microcontoller firmware."

## ZigBee stack for Linux, alpha, by alexbluesman, lumag, maximosipov ##
http://sourceforge.net/projects/linux-zigbee/
  * "ZigBee stack for Linux covers IEEE 802.15.4 PHY and MAC layers as well as ZigBee Alliance NWK and (partially) APL layers of protocol."