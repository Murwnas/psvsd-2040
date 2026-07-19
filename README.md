# PSVSD 2040

![KiCad 3D render](/assets/psvsd-gif.gif)

This is a module based on [Yinfanlu's PSVSD adapter](https://github.com/yifanlu/psvsd/). Last year, I took the original Eagle Autodesk files and adapted them to a [KiCad EDA source](https://github.com/Murwnas/psvsd-kicad). This repo code is based on my adaptation. 

One of the problems with the original PSVSD is the out-of-production Genesys chip. Apparently, from my research, all that chip does is expose a connected SD card as a USB Mass Storage device, which the Yinfanlu driver uses to interface with the PSVSD module. 

From my understanding, the Genesys chip can be replaced with any SD-USB bridge with *one* caveat---USB power is always on, so the chip must support a low-power standby mode. A little research online tells me that people have already adapted these modules to use newer USB-3.0 chips. I'm not sure how true that is because I couldn't find any PCB sources or listings that specifically make this claim.

My own fun, and kind of dumb, idea was to re-design the adapter with an RP2040 chip (Raspberry Pi Pico). The reason this isn't the greatest idea is because RP2040 only supports USB 1.1 Full Speed, which tops at 12 Mbps. I imagine this would make for a pretty sluggish experience. 

But hey, why not? Plus, this actually allows for a PSVSD adapter that's programmable. You can theoretically make it do anything as long as its within the internal USB controller's capabilities. And unlike those SD-to-USB bridges, RP2040 chips are cheap and everywhere. I don't imagine they'll go anywhere anytime soon.

Although the main PCB has been designed and mostly layed out as of the present, it hasn't been fabricated and tested. For this reason, I also haven't written any firmware. This is just very early work. I advise against reproducing, else you might fry your PS Vita!
