---
layout: page
title: PicoGreen Assay
subtitle: The protocol for checking quantification of DNA using the PicoGreen Assay on the Plate Reader 
---

## Background
PicoGreen dsDNA Quantitation Reagent is an ultra-sensitive fluorescent nucleic acid stain for quantitating double-stranded DNA (dsDNA) in molecular biological procedures such as cDNA synthesis for library production and DNA fragment purification for subcloning, as well as diagnostic applications, such as quantitating DNA amplification products and primer extension assays. 
The most commonly used technique for measuring nucleic acid concentration is the determination of absorbance at 260 nm (A260).

## Equipment & Reagents
* flat bottom black Costar 96-well plate (Fisher Cat #: 07-200-627) (FIND OUT IF AUTOCLAVE SAFE)
* two - 15 mL Falcon tubes
* two - 0.2 mL snap cap tubes for ladder dilutions
* samples diluted to appropriate concentration to be read on the plate reader
* 20X TE Buffer (comes with PicoGreen Kit)
* PicoGreen Dye (comes with PicoGreen Kit)
* DNA Ladder 100 ug/mL (comes with PicoGreen Kit)

* Synergy HTX plate reader in shared molecular space

## Important Notes 
* Plate reader can read samples between 25 pg/mL - 1,000 ng/mL (or 0.000025 - 1 ng/uL). To be conservative we make the highest concentration for our ladder 500 ng/mL.
* Samples should be diluted to be read within this range. For example, typical quantifications for Atlantic cod DNA extractions using a spin column plate is between 10 - 200 ng/uL. Therefore, you should do a 1:10 dilution because the reaction does a 1:100 dilution in the reaction itself. This brings the final DNA concentration to 10 - 200 ng/mL which is well within the range of the assay.
* PicoGreen dye is a solid when stored at 4C. Allow the dye to come to room temperature before use. Take out the kit and leave on the counter before starting protocol to ensure it becomes a liquid. You can pipette TE and samples while it is coming to room temp.
* The first column of your plate needs to be saved for the ladder standards. Therefore if you are using 6 standards as recommended in this protocol, the most samples you could run on a plate is 90.

## Protocol
* Dilute your 20X TE to 1X TE by pipetting 9.5 mL of Molecular Grade H2O and 0.5 mL of 20X TE into a 15mL falcon tube. This solution is stable long term so you can make more than you will need and store for later use. If you will not be using frequently, you can also calculate exactly how much you need and just make enough for that use.
* Create your ladder standards using Table 1. The stock ladder is at 100 ug/mL. So for example, to make Dilution 1 at 2 ug/mL, combine 1 uL of stock ladder with 49 uL of 1X TE.
* Pipette 49 uL of 1X TE in all sample wells and the appropriate volume of 1X TE into each standard well according to Table 2. For example for standard 1 pipette 25 uL of 1X TE in the appropriate well.
* Add 1 uL of sample to each of the sample wells and the appropriate amount of each ladder to the standard wells according to Table 2. For example, add 25 uL of Ladder Dilution 1 to standard 1 well.
* At this point your PicoGreen should be at room temperature. Create your Diluted PicoGreen and use Equation 1 to determine how much stock PicoGreen dye you need for the number of samples/standards you are running. Then use that value to calculate the amount of 1X TE this should be added to for a 200 times dilution using Equation 2. 
* Pipette diluted PicoGreen to each well with each well getting 50 uL of the 200 times diluted PicoGreen. When adding the diluted PicoGreen pipette up and down at least 20 times to mix sample, TE and PicoGreen together.
* Use a plate cover and briefly spin down the plate to get all liquid to the bottom of the well.
* Run plate on a Plate Reader using the Gen5 software. First turn on the machine to warm up (takes ~2-3 minutes)
* Open Gen5 software and on the opening window make sure you are on the "Run Now" option on the left side column and click on the PicoGreen Assay full plate file. 
* This will open another window with a full plate already loaded just click "cancel"
* Click "Plate Layout" on the top bar which will open a new window to edit with your standard curve and sample wells
* Clear plate by highlighting "EMPTY" on the left panel and click and drag across whole plate
* Then right click on the "STD" and click "edit" to change your standard curve values to what you set up for your plate when you are done editing click okay
* Highlight the first standard curve value in the left panel and click on the appropriate well where that value is located. You can click and drag down the column if they are all in a row.
* Highlight the first sample (SP1) from the left panel and click on the well with your first sample well and drag across the plate until all wells you want readings for are filled. ** You do not need to put water in empty wells can just leave empty **
* When this is done click okay and the machine will have a bulb warm up period after which it will ask you to load your plate. You do not need to close the drawer it will close automatically after you load the plate and click "okay". 
* The run should take ~2-3 minutes, then click on the "Statistics" tab and output that spreadsheet to an excel file by copy and pasting. 
* Finally use XXX spreadsheet to convert absorbance values to associated concentrations. 

### Equation 1 
(1.1 * (50 uL diluted PicoGreen * (#samples + #standards))/200 = vol of Stock PicoGreen 

### Equation 2 
199 * vol of Stock PicoGreen = vol of 1x TE 

### TABLE 1 

| Ladder Type | Concentration (ug/mL) | Ladder Type | Ladder Vol (uL) | 1X TE Vol (uL) | 
|-------------|-----------------------|-------------|-----------------|----------------| 
| D1          | 2                     | Stock       | 1               | 49             | 
| D2          | 0.2                   | D1          | 1               | 9              | 

### TABLE 2 

| Standards | Concentration (ng/mL) | Ladder Type | Ladder Vol (uL) | 1X TE Vol (uL) | Diluted PicoGreen Vol (uL) | 
|-----------|-----------------------|-------------|-----------------|----------------|----------------------------| 
| 1         | 500                   | D1          | 25              | 25             | 50                         | 
| 2         | 250                   | D1          | 12.5            | 37.5           | 50                         | 
| 3         | 100                   | D1          | 5               | 45             | 50                         | 
| 4         | 10                    | D2          | 5               | 45             | 50                         | 
| 5         | 4                     | D2          | 2               | 48             | 50                         | 
| blank     | 0                     | -           | -               | 50             | 50                         | 

### TABLE 3

| Reagent | Volume (uL) |
|---------|-------------|
| 1X TE   | 49          |
| sample  | 1           |
| dil PG  | 50          |
