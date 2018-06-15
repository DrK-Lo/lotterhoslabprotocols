---
layout: page
title: Conductivity Loggers
subtitle: The protocol for calibrating/initializing, deploying, and offloading Data for conductivity loggers
---

## Initializing Loggers
We use the [HOBO Salt Water Conductivity/Salinity Data Logger](http://www.onsetcomp.com/products/data-loggers/u24-002-c) to measure local changes in salinity, conductivity, and temperature where we sample oysters.

To initialize the sensor:
1. First, make sure you have the [Hobo Waterproof Shuttle](http://www.onsetcomp.com/products/communications/u-dtw-1) and appropriate coupler (Blue COUPLER2-C for U22/U24/U26/U20L) 
2. Make sure you have HOBOWare downloaded to your computer
3. Attach conductivity logger to the shuttle with the coupler. Align the arrows between the logger and shuttle coupler for proper connection
4. Use miniUSB to connect the logger to the computer. Unscrew white cap on shuttle to access the cord port
5. Open HoboWare
6. In the bottom left bar of the program you will see that the software recognizes your device (\'Dev: HOBO Waterproof Shuttle U-DTW-1...\'). It will 1 device connected in lower right bar.  **This does not mean the shuttle has been properly started and connected**
7. To properly start and connect the logger press the coupler lever

INSERT IMAGE

8. This starts the logger and you should see a \'Installing device drive software\' message on your screen
9. When the software has been installed, it should then say \'USB Input Device\'
10. The device name in the lower left bar of the HOBOWare program should now be correct 
11. To get some basic information about the logger, go to \'Device\' in the menu bar, then choose \'Status\'
This gives basic information about the logger such as the device name, serial number, battery state, etc.
** You should use a Dixon standard (saltwater standard) to get an initial Conductivity reading form this Status pane before initializing**
12. To launch the logger, go to \'Device\' -> \'Launch\'
13. Change the name to something meaningful like \'20180615_Barnstable_conductivity\'
14. Choose the logging interval and when to start logging (when the logger will be deployed)
15. Click \'Start\' and logger will launch

## Deploying loggers
