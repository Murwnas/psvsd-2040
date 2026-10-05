# PSVSD 2040

![KiCad 3D render](/assets/psvsd.gif)

This is a module based on [Yinfanlu's PSVSD adapter](https://github.com/yifanlu/psvsd/). Last year, I took the original Eagle Autodesk files and adapted them to a [KiCad EDA source](https://github.com/Murwnas/psvsd-kicad). This repo code is based on my adaptation. 

One of the problems with the original PSVSD is the out-of-production Genesys chip, which appears to be a generic USB-to-SD bridge that simply exposes Mass Storage. It's theoretically possible to use any such bridge chip in its place, but anyone who has read Yinfanlu's write-up on this will also know that power consumption is the main problem behind those adapters. The PS Vita's modem port never switches off power to the modem port. Therefore, these adapters consume power even when the console is off.

My own fun idea was to recreate this adapter using my favorite chip: The RP2040. It has a USB interface, fast GPIO lines, and very low power consumption---with the potential to go into deep-sleep-like states to draw very small amounts. 

The main downside is USB 1.1 speeds, which theoretically cap at 1.2 MB/s. 

Right now, a board has been designed and fabricated, but I have not had the time to assemble and test it. Whether this is a viable concept will remain to be seen.

Do not attempt to reproduce this unless you are fine with potentially making a faulty board that may or may not fry your PS Vita! 


