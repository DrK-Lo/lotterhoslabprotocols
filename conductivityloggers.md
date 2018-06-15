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

![""](/img/couplerlever.jpg)

8. This starts the logger and you should see a \'Installing device drive software\' message on your screen
9. When the software has been installed, it should then say \'USB Input Device\'
10. The device name in the lower left bar of the HOBOWare program should now be correct 
11. To get some basic information about the logger, go to \'Device\' in the menu bar, then choose \'Status\'
This gives basic information about the logger such as the device name, serial number, battery state, etc.
** You should use a Dixon standard (saltwater standard) to get an initial Conductivity reading form this Status pane before initializing**
12. To launch the logger, go to \'Device\' -> \'Launch\'
13. Change the name to something meaningful like \'20180615_Barnstable_conductivity\'
14. Choose the logging interval and when to start logging (when the logger will be deployed)
**THIS IS VERY IMPORTANT: When you choose the logging interval, check the \'Logs until\' time in the pane above it to see how long it will take before the storage runs out. If your interval is too small, the logger will fill up before you can offload the data and continue measuring**
15. Click \'Start\' and logger will launch
16. Unplug from the computer
17. **Place rubber cap that comes with the logger on cylindrical end to prevent scratches**

## Deploying loggers

#### Materials you'll need before deploying:
1. Cinderblock
2. Metal tubing straps to attach PVC fixed loggers to
3. Zipties
4. PVC pipe large and long enough to fit logger, \"swiss-cheesed\' with holes
**There must be enough holes for regular flow of water through the PVC pipe. The PVC pipe prevents large rocks and debris from damaging loggers**
5. Rope and buoy
6. Glass bottles and 50 mL Falcon tubes. See [this page](https://bmford11.github.io/lotterhoslabprotocols/watersampling/) for water sampling protocol
7. 

#### Before leaving for the field
1. Attach metal straps to cinder block
2. Attach PVC pipe to the metal rings that are fastened to the cinderblock
3. Label cinderblock, PVC pipe, buoy, and sensors with contact information (Katie's)
4. Make sure you've contacted local shellfish constable to make sure they can keep an eye on the sensor

### Deploying
Sensors should be deployed at low tide, so that we know they'll be constantly exposed to water while logging
1. Before deploying, attach sensor(s) to PVC using many zipties
2. Wade to waist-deep water at site of deployment
3. Deploy logger
4. Record time of deployment. If loggers start logging before they are deployed they give strange readings. It is good to know when the logger was actually deployed, so we know when logging was actually initiated
5. Record location using GPS
6. Take water samples

#### Last Steps
1. Add the geographic location, deployment time, and additional notes about site to the log file (should be a google doc- ask Katie)
2. Make sure field sample in glass bottle has been poisoned with Mecuric Chloride (Ries Lab) and place in freezer

## Offloading Data
Data from loggers should be off-loaded about every two weeks

#### Materials you'll need before going into the field for off-loading data
1. Glass bottle and 50mL Falcon tube fore water samples
2. HOBO Waterproof shuttle and correct coupler
3. Laptop with HOBOWare and USB cord (unless logger was deployed with a launched shuttle and HOBOWare Pro)
4. Kimwipes

### Off-loading Data
1. Retrieve logger
2. Make sure logger is completely dry before hooking up to shuttle and coupler 
3. Remove rubber cap
4. Connect logger to shuttle with coupler
5. Plug into computer
6. Open HOBOWare
7. Go to \'Device\' in menu bar and choose \'Readout\'
8. You should then be prompted with the message: 

\"The logger is currently logging. Do you wish to stop before reading out the logger?\"

9. Choose yes. 
10. Save readout to computer, choosing the appropriate settings
11. Disconnect logger and replace rubber cap
12. Relaunch (see \'Deploying\' above)
13. Record time of deployment
14. Take water samples
**When the shuttle is not connected to the computer, make sure the waterproof cap is properly sealed to prevent water from damaging the USB port**
. 
