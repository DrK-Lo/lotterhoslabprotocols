---
layout: page
title: TapeStation Library Check
subtitle: The protocol for checking libraries on the TapeStation
bigimg: /img/tapestation.JPG
---

## Background
The Agilent TapeStation provides an accurate, efficient quantification and quality assessment of RNA, DNA and protein samples. RIN numbers are given to RNA samples and quantification can be done on each individual band in your sample. Output comes as both a gel image and a size distribution electropharogram. Can handle strip tubes or plates. 

## Equipment & Reagents
* 2200 TapeStation (Agilent Cat # G2965AA) 
* Loading Tips (1pk = 384 tips, Agilent Cat # 5067-5153) ** must use their tips    
* Optical Tube Strips (Agilent Cat # 401428) ** can use other tubes with exact same dimensions     
* Strip capes (Agilent Cat # 401425) ** can use other caps not needed for actual machine run     
* Kits:    
1. **D1000**                                            
   * ScreenTape (Agilent Cat # 5067-5582)                
   * Reagents (Agilent Cat # 5067-5583)      
2. **High Sensitivity D1000**
   * ScreenTape (Agilent Cat # 5067-5584)
   * Reagents (Agilent Cat # 5067-5585)       
3. **D5000**
   * ScreenTape (Agilent Cat # 5067-5588) 
   * Reagents (Agilent Cat # 5067-5589)   
4. **High Sensitivity D5000**      
   * ScreenTape (Agilent Cat # 5067-5592)
   * Reagents (Agilent Cat # 5067-5593)
 
**Store all tapes in their box with the label facing towards you (Fig 1 below)**   

![alt text][logo]

[logo]: https://docs.google.com/drawings/d/1t0-f8TKZFptM4MrDHA_w4AtsOcy_YRR7boeD1aCk2mg/pub?w=1429&h=495

## Important Notes **READ BEFORE USING**: 

* RNA Reagent kits and tapes will be GREEN and DNA Reagent kits and tapes will be BLUE double check before you get started
* Make sure you use the correct tape and buffers for the size fragments that you are looking at: 
* Pairs only EVEN number of samples because the two probes move together. If you have 3 samples fill a 4th with buffer 
* Tapes can only do up to 16 samples at a time (2 columns of a 96 well plate or 2 strip tubes)
* If you are doing a 96 well plate you need to replace the Tape after the 16 samples are complete. Computer program will notify you when this is okay to do. 

* **NEVER OPEN TAPESTATION WHILE RUNNING SAMPLES** unless you want to start over! This will throw out all your data because it completes calculations after it runs through every sample.
* Always wear gloves when handling the tapes, oils on your hands can impact the accuracy of the reads

## Things to do before starting

* Set XXX reagent on counter for 30 minutes to bring to room temperature 
* Label strip tubes or plate for your samples
* Login to machine using the sticker log in information on the computer

## Protocol

* Load tips into machine with multi-channel pipette
  * If you are doing a plate, you will need to refill tips after each set of 16 samples completes. The program will alert you when it is time to refill them.
* After tape has come to room temperature, flick out any air bubbles from the lanes
  * Usually only happens if the tape has had some lanes used before
* Insert tape in the appropriate slot

![alt text][fig2]

[fig2]: https://docs.google.com/drawings/d/1ajGI6Yz1gpO-WCYh8056qCoPAlh_n4mYoNaOQg73TOc/pub?w=465&h=336
 
  * Tapes have a barcode that needs to be read by the machine
  * If in the wrong orientation, the computer will spit back an error
  * Save the wrapping if you aren’t using all the lanes to place tape back in for storage after run
* Highlight where your samples are and name them via the spreadsheet on the right
  * CSV file with names can be uploaded

![alt text][fig3]

[fig3]: https://docs.google.com/drawings/d/1joVrT3Hetfx3kbLPvPmTcUZlsE-SD004qC5AmqHDxq8/pub?w=239&h=283


* Vortex and spin down reagents that you will be using for run
* Add 3 uL of buffer and 1 uL of ladder or sample to each well that you will be using
  * Only one well needs to be used for the ladder and it doesn’t matter which well you use just make sure to label properly in the spreadsheet
* Spin for 1 min on fancy vortexer with caps on
* Remove caps
* Place in machine in the orientation that you filled the spreadsheet out as
* Double check tips are in
* Click Start
* Once complete File  Open your file
* You can view the results as both a gel image and an electropherogram
* Click the electropherogram button and then scale to sample 
  * All concentrations are outputted as a table below the electropherogram 
* Set upper and lower markers by right clicking on peaks
* To zoom into a peak, highlight the region on the electropharogram
* You can also compare results between different files by clicking the comparison tab
* Open the files that you wish to compare
  * NOTE you can only compare those DNA to DNA or RNA to RNA AND they must be from the same kit
* You can make a report of all of your data by clicking File  Make a report 
  * Check off the items you want in the report and change the order you want them to appear by using the arrows 
