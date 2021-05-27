---
layout: page
title: Illumina Library Prep
subtitle: The protocol for doing a library prep using Illumina kit
---

*Note: This protocol is unfinished*

## Background

Before you start this, you should [determine the barcodes and index scheme for your library.](https://bmford11.github.io/lotterhoslabprotocols/barcodesnindexes/)

Then, you should draw an outline of what is happening at each step in this protocol:

[Example Genomic Library Prep with inline barcodes and dual indexes](https://docs.google.com/document/d/1xr99sMucP-x2rK6K61vtGHKNahl9UYFwh_oEb0AtHX8/edit)

This protocol is based on the KAPA Hyper Prep Kit [protocol](https://rochesequencingstore.com/wp-content/uploads/2017/10/KAPA-HyperPrep-Kit_KR0961-%E2%80%93-v7.19.pdf) with added notes from both Jon Puritz and Sara Schaal. We performed the protocol using half reactions of everything compared to the original protocol.

## Kits used  
* KAPA Hyper Prep Kit (Kit Code: KK8505) 
 
## Materials needed  
* 500 ng of DNA in 25 uL of RNAse free water that is sheared to the size appropriate for your library
* Primers at 15 uM (aliquots of i5 and i7 custom primers if using)
* Adapters at 15 uM (aliquots of annealed custom adapters if using)
* KAPA beads (or other beads)  

## Equipment needed  
* Thermo Mixer set at 20C and 400 rpm (this can be done in the thermocycler as well if you don't have a thermo Mixer)
* Thermocycler - preprogrammed to have all thermocycler steps already set up: End Repair and A-Tailing and PCR. 
* Magnetic Bead Rack   

## Tips & Exposables  
* filtered 10 uL 
* filtered 20-200 uL 
* Strip tubes or individual tubes depending on how many libraries you are prepping

## Protocol

### End Repair & A-tailing
* Assemble each end repair and A-tailing reaction in a tube or well of a PCR plate as follows:   

| Component                      | Volume |
|--------------------------------|--------|
| Fragmented Double Stranded DNA | 25 uL  |
| End Repair & A-tailing Buffer  | 3.5 uL |
| End Repair & A-tailing Enzyme  | 1.5 uL |
| Total Volume                   | 30 uL  |

Depending on how many libraries you are prepping, you can make a master mix of the buffer and enzyme to add to each sample well. If you do this, be sure to add about 10% volume of each component due to pipetting error. 

* Vortex gently and spin down briefly. Return the plate/tube(s) to ice. Proceed immediately to the next step.
* Incubate libraries in thermocycler set to the following protocol: 

| Step                    | Temp | Time   |
|-------------------------|------|--------|
| End Repair & A-Tailing  | 20 C | 30 min |
| ''                      | 65 C | 30 min |
| HOLD                    | 4 C  | *      |


* Proceed immediately to Adapter Ligation

### Adapter Ligation
* In the same plate/tube(s) in which end repair and A-tailing was performed, assemble each adapter ligation reaction as follows:  

| Component                                 | Volume |
|-------------------------------------------|--------|
| End Repair & A-Tailing Reaction Product   | 30 uL  |
| Adapter stock (concentration as required) | 2.5 uL |
| PCR-grade water                           | 2.5 uL |
| Ligation Buffer                           | 15 uL  |
| DNA Ligase                                | 5 uL   |
| Total Volume                              | 55 uL  |

Again, at this step you can make a master mix of the buffer, Ligase enzyme and water. If you do this, be sure to add about 10% volume of each component due to pipetting error. 

* Mix thoroughly by pipetting up and down 15 times and centrifuge briefly. 
* Incubate at 20C for 60 minutes on the ThermoMixer with the rotations set at 400 rpm. 
* After incubation, proceed immediately to the next step

### Post-Ligation Cleanup

### PCR

### Post-PCR Cleanup

### spot check libraries on a tapestation before qPCR

