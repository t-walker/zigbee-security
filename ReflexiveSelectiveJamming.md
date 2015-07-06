# Introduction #

The Reflexive Jamming code is written for the Tmote Sky / TelosB platform, and is available in GoodFET and KillerBee on the those devices.

The Selective Jamming code is written for USRP2 devices currently, although we are programming it to be on microcontrollers.

# Reflexive Jamming #

Currently our reflexive jamming (aka collision) implementation (on a Tmote/TelosB device) can jam a frame on the 8th byte (aka works for any frames this long, which are all frames except ACK), and will _cause the FCS to be invalid and thus a receiving radio will drop the frame_ if it has AUTOCRC (or similar) enabled, which should be all commercial devices (aka anything except sniffers). For more questions, please contact us.

# Selective Jamming #

If you'd like the USRP2 code, including a proof-of-concept on association response frames like we demoed at ShmooCon, email us.

We've also implemented this on micro-controllers, specifically via the GoodFET platform. The only selection criteria available currently is time, which can be precisely controlled to correlate to the length of the frame. Basically, frames over a certain length can be selectively jammed due to a delay before jamming injection. This works very well against targets which are vulnerable to length-based traffic analysis. For other targets, we're working on other techniques.