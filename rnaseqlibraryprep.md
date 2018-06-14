---
layout: page
title: RNAseq Library Prep
subtitle: The protocol for doing a library prep for RNASeq
---

## Begin KAPA Stranded mRNA-Seq Kit using 1/2 rxn volumes
This should take 8-10 hours
Refer to manual during procedure (steps below are for notes and comments)

### Reagents 

KAPA Stranded mRNA-Seq Kit (KAPA #XXXXXX). This kit includes all the enzymes and buffers required for cDNA library preparation from  isolation of poly(A)-tailed RNA. Kits include reagents for RNA fragmentation, 1st strand cDNA synthesis and 2nd strand synthesis/marking, and cDNA library preparation, including A-tailing, ligation and library amplification. 

Steps in Library construction (Here I just want to be explicit where we use their reagents and where we use our reagents):

* mRNA capture using magnetic oligo-dT beads
* Fragmentation using heat and magnesium
* 1st Strand cDNA Synthesis using random priming
* 2nd Strand cDNA Synthesis and marking, which converts the cDNA:RNA hybrid to double-stranded cDNA (dscDNA) and incorporates dUTP in the second cDNA strand
* A-tailing to add dAMP to the 3′-ends of the dscDNA library fragments
* Adapter ligation, where dsDNA adapters with 3′-dTMP overhangs are ligated to A-tailed library insert fragments (HERE WE USE CUSTOM ADAPTERS, SEE BELOW)
* Library amplification to amplify library fragments carrying appropriate adapter sequences at both ends using high-fidelity, low-bias PCR; the strand marked with dUTP is not amplified.

### Additional reagents needed:

Annealing buffer stock (10X):

| Component| Concentration|
|----------|--------------|
| Tris HCl, pH 8| 100 mM|
| NaCl|500 mM|
| EDTA| 10 mM|

###Equipment 

###Custom Oligos needed to make adapters:

Jon can you add a figure here on the adapters... Illumina calls P1 P5 and P2 P7... just to avoid confusion for the eventual user of this protocol.

|Oligo Name| Sequence|
|----------|---------|
|RNA_P2.1_H3|P*CAAGCTTAGATCGGAAGAGCGAGAACAA
|RNA_P2.1_NC|P*CCCATGGAGATCGGAAGAGCGAGAACAA
|RNA_P2.1_SA|P*CGTCGACAGATCGGAAGAGCGAGAACAA
|RNA_P2.1_BS|P*CTGTACAAGATCGGAAGAGCGAGAACAA
|RNA_P2.2_H3|GTGACTGGAGTTCACACGTGTGCTCTTCCGATCTTTCGAAG*T
|RNA_P2.2_NC|GTGACTGGAGTTCACACGTGTGCTCTTCCGATCTGGTACCG*T
|RNA_P2.2_SA|GTGACTGGAGTTCACACGTGTGCTCTTCCGATCTCAGCTGG*T
|RNA_P2.2_BS|GTGACTGGAGTTCACACGTGTGCTCTTCCGATCTACATGTG*T
|RNA_P1.1_H3|ACACTCTTTCCCTACACGACGCTCTTCCGATCTAAGCTTG*T
|RNA_P1.1_NC|ACACTCTTTCCCTACACGACGCTCTTCCGATCTCCATGGG*T
|RNA_P1.1_SA|ACACTCTTTCCCTACACGACGCTCTTCCGATCTGTCGACG*T
|RNA_P1.1_BS|ACACTCTTTCCCTACACGACGCTCTTCCGATCTTGTACAG*T
|RNA_P1.2_H3|P*CTTCGAAATCGGAAGAGCGTCGTGTAGGGAAAGAGTGT
|RNA_P1.2_NC|P*CGGTACCATCGGAAGAGCGTCGTGTAGGGAAAGAGTGT
|RNA_P1.2_SA|P*CCAGCTGATCGGAAGAGCGTCGTGTAGGGAAAGAGTGT
|RNA_P1.2_BS|P*CACATGTATCGGAAGAGCGTCGTGTAGGGAAAGAGTGT 

### Anneal RNA Adapters
Single-stranded oligos need to be annealed with their appropriate partner before ligation. 
 
* To create Adapter P1, combine each oligo 1.1 with its complementary oligo 1.2 in a 1:1 ratio in working strength annealing buffer (final buffer concentration 1x) for a total annealed adapter concentration of 40uM (for example, if purchased oligos are resuspended to an initial concentration of 100uM, use 40ul oligo 1.1, 40ul oligo 1.2, 10ul 10x annealing buffer and 10ul nuclease-free water). Do the same for oligos 2.1 and 2.2 to create the common adapter P2. 
2.   In a thermocyler, incubate at 97.5°C for 2.5 minutes, and then cool at a rate of not greater than 3°C per minute until the solution reaches a temperature of 21°C. Hold at 4°C.
3.   Prepare final working strength concentrations of annealed adapters from this annealed stock (the appropriate working stock dilution for your experiment can be determined from our ligation molarity calculator-WILL PROBABLY HAVE TO ADD DETAILS). For convenience, it is possible to store the adapters at 4°C while in active use.

**Procedure:**
* Prepare mastermixes for 4 libraries
  * See tables in manual and tables below for guidelines:

|Component| Total Volume Needed for 4 RXNs|
|---------|--------------------|
|**1st Strand Synthesis Master Mix:**|--|
|1st Strand Synthesis Buffer|22 μl|
|KAPA Script|2 μl|
|**Total Master Mix Volume**| **24 μl**|
|**Final reaction composition:**|--|
|1st Strand Synthesis Master Mix| 5 μl|
|Fragmented, primed RNA|10 μl| 
|**Total Reaction Volume**| **15 μl**|

|Component| Total Volume Needed for 4 RXNs|
|---------|--------------------|
|**2nd Strand Synthesis and Marking Master Mix:**|--|
|2nd Strand Marking Buffer|62 μl|
|2nd Strand Synthesis Enzyme Mix|4 μl|
|**Total Master Mix Volume**| **66 μl**|
|**Final reaction composition:**|--|
|2nd Strand Synthesis and Marking Master Mix| 15 μl|
|Fragmented, primed RNA|15 μl| 
|**Total Reaction Volume**| **30 μl**|

|Component| Total Volume Needed for 4 RXNs (10% excess)|
|---------|--------------------|
|**A-Tailing Master Mix:**|--|
|Water|52.8 μl|
|10X KAPA A-Tailing Buffer|6.6 μl|
|KAPA A-Tailing Enzyme|6.6 μl|
|**Total Master Mix Volume**| **66 μl**|
|**Resuspend beads in a volume of:**|** 15 μl** |

|Component| Total Volume Needed for 4 RXNs|
|---------|--------------------|
|**Adapter Ligation Master Mix:**|--|
|Water|35.2 μl|
|5X KAPA Ligation Buffer| 30.8μl|
|KAPA T4 DNA Ligase|11 μl|
|**Total Master Mix Volume**| **77 μl**|
|**Final reaction composition:**|--|
|Beads with A-tailed DNA|15 μl|
|Adapter Ligation Master Mix|17.5 μl|
|Adapter (350 nM – 1400 nM, as appropriate)|2.5 μl|
|**Total Reaction Volume**| **35 μl**|

|Component| Total Volume Needed for 4 RXNs (10% excess)|
|---------|--------------------|
|**Library Ampli cation Master Mix:**|--|
|2X KAPA HiFi HotStart ReadyMix|55 μl|
|10X KAPA Library Amplication Primer Mix|11 μl|
|**Total Master Mix Volume**| **66 μl**|
|**Final reaction composition:**|--|
|Adapter-ligated library DNA|10 μl|
|Library Ampli cation Master Mix|15 μl|
|Balance of water (if required)|5 μl|
|**Total Reaction Volume**| **30 μl**|

###mRNA Capture
* Combine the following for each RNA sample to be captured:

|Component|Volume|
|---------|------|
|RNA sample (in RNase-free water)| 25 μl|
|KAPA mRNA Capture Beads| 25 μl|
|**Total Volume**| **50 μl**|

* Mix thoroughly by gently pipetting up and down several times.
* Place the plate/tube in a thermal cycler and carry out the 1st mRNA capture program as follows:

|Step|Temp.|Duration|
|----|-----|--------|
|1st mRNA capture|65 °C|2 min|
|Cool|20 °C|5 min|


* Place the plate/tube containing the mixture of KAPA mRNA Capture Beads and RNA on a magnet and incubate at room temperature until the solution is clear. Remove and discard the supernatant.
* Remove the plate/tube from the magnet and resuspend thoroughly in 100 μl of KAPA mRNA Bead Wash Buffer by pipetting up and down several times.
* Place the plate/tube on the magnet and incubate at room temperature until the solution is clear. Remove and discard the supernatant.
* Resuspend the beads in 25 μl of RNase-free water.
* Place the plate/tube in a thermal cycler and carry out the 2nd mRNA capture program as follows:

|Step|Temp.|Duration|
|----|-----|--------|
|2nd mRNA capture|70 °C|2 min|
|Cool|20 °C|5 min|

* Add 25 μl of KAPA Bead Binding Buffer to the mixture of KAPA mRNA Capture Beads and RNA and mix thoroughly by gently pipetting up and down several times.
* Incubate the plate/tube at 20 °C for 5 min.
* Place the plate/tube on the magnet and incubate at room temperature until the solution is clear. Remove and discard the supernatant.
* Remove the beads from the magnet and resuspend in 100 μl of KAPA mRNA Bead Wash Buffer by pipetting up and down several times.
* Place the plate/tube on the magnet and incubate at room temperature until the solution is clear. Remove and discard the entire volume of supernatant.
####mRNA Elution, Fragmentation and Priming
* Prepare the required volume of 1X Fragment, Prime and Elute Buffer as follows:

|Component|Volume per sample|
|---------|------|
|Water| 5.5 μl|
|Fragment, Prime and Elute Buffer (2X)| 5.5 μl|
|**Total Volume**| **11 μl**|

* Thoroughly resuspend the KAPA mRNA Capture Beads with captured mRNA prepared in Step 2.13 above in 11 μl of 1X Fragment, Prime and Elute Buffer.

###Safe Stopping Point
Resuspended beads with captured mRNA may be stored at 4 oC for up to 24 hours. Do not freeze the samples as this will damage the beads. When ready, proceed to step below.

* Place the plate/tubes in a thermal cycler and carry out the fragmentation and priming program as follows:

|Desired Fragment Size| Temp.| Duration|
|---------------------|------|---------|
|100 – 200 bp|94 °C|8 min|
|**200 – 300 bp**|**94 °C**|**6 min**|
|300 – 400 bp|85 °C|6 min|

**_We are planning on using 125 bp or 150 bp sequencing, so I think it makes sense to use the 200-300 range_**


* Immediately place the plate/tube on a magnet to capture the beads, and incubate until the liquid is clear. **Caution: To prevent hybridization of poly(A)- rich RNA to the capture beads, do not allow the sample to cool before placing on the magnet.**
* Carefully remove 10 μl of the supernatant containing the eluted, fragmented, and primed RNA into a separate plate or tube.
* Proceed immediately to **1st Strand Synthesis**.

###1st Strand Synthesis
* On ice, assemble the 1st Strand Synthesis reaction as follows:

|Component|Volume|
|---------|------|
|Fragmented, primed RNA eluted from beads| 10 μl|
|1st Strand Synthesis Master Mix| 5 μl|
|**Total Volume**| **15 μl**|

* Keeping the plate/tube on ice, mix thoroughly by gently pipetting the reaction up and down several times.
* Incubate the plate/tube using the following protocol:

|Step|Temp.|Duration|
|----|-----|--------|
|Primer extension|25 °C|10 min|
|1st Strand synthesis|42 °C|15 min|
|Enzyme inactivation|70 °C|15 min|
|HOLD|4 °C|∞|

* Place the plate/tube on ice and proceed immediately to **2nd Strand Synthesis and Marking**.

###2nd Strand Synthesis
* Assemble the 2nd Strand Synthesis and Marking reaction as follows:

|Component|Volume|
|---------|------|
|1st Strand cDNA| 15 μl|
|2nd Strand Synthesis and Marking Master Mix| 15 μl|
|**Total Volume**| **30 μl**|

* Mix thoroughly by gently pipetting the reaction up and down several times.
* Incubate the plate/tube using the following protocol:

|Step|Temp.|Duration|
|----|-----|--------|
|2nd Strand synthesis and marking|16 °C|60 min|
|HOLD|4 °C|∞|

* Place the plate/tube on ice and proceed immediately to **2nd Strand Synthesis and Marking Cleanup**.

###Cleanup

* Perform a 1.8X SPRI® cleanup by combining the following:

|Component|Volume|
|---------|------|
|2nd Strand Synthesis reaction product| 30 μl|
|Agencourt® AMPure® XP reagent| 54 μl|
|**Total Volume**| **84 μl**|

* Thoroughly resuspend the beads by pipetting up and down multiple times.
* Incubate the plate/tube at room temperature for 5 – 15 min to allow the DNA to bind to the beads.
* Place the plate/tube on a magnet to capture the beads. Incubate until the liquid is clear.
* Carefully remove and discard 74 μl of supernatant.
* Keeping the plate/tube on the magnet, add 200 μl of 80% ethanol.
* Incubate the plate/tube at room temperature for ≥30 sec.
* Carefully remove and discard the ethanol.
* Keeping the plate/tube on the magnet, add 200 μl of 80% ethanol.
* Incubate the plate/tube at room temperature for ≥30 sec.
* Carefully remove and discard the ethanol. Try to remove all residual ethanol without disturbing the beads.
* Dry the beads at room temperature, until all of the ethanol has evaporated. 
  * **Caution: over-drying the beads may result in dramatic yield loss.**
* Proceed immediately to **A-Tailing** immediately, or follow the Safe Stopping Point instructions below.

###SAFE STOPPING POINT
* Resuspend the beads in 15 μl 1X A-Tailing Buffer (Table 5B), cover the reaction and store at 4 oC for up to 24 hours. Do not freeze the samples as this will damage the AMPure® XP® beads. When ready, proceed to **A-Tailing after Safe Stopping Point**.

###A-Tailing
* A-Tailing is performed either directly after the 2nd Strand Synthesis and Marking Cleanup, or after the Safe Stopping Point, where beads were resuspended in 1X A-Tailing Buffer and stored at 4 °C for up to 24 hours. 

###A-Tailing immediately
* Assemble the A-Tailing reaction as follows:

|Component|Volume|
|---------|------|
|Beads with dscDNA| --|
|A-Tailing Master Mix| 15 μl|
|**Total Volume**| **15 μl**|

* Mix thoroughly by pipetting up and down several times.
* Incubate the plate/tube using the following protocol:

|Step|Temp.|Duration|
|----|-----|--------|
|A-Tailing|30 °C|30 min|
|Enzyme inactivation|60 °C|30 min|
|HOLD|4 °C|∞|

* Proceed immediately to **Adapter Ligation**.

###A-Tailing after safe stopping point
* To resume library preparation, combine the following reagents to perform A-Tailing:

|Component|Volume|
|---------|------|
|Beads with dscDNA (in 1X A-Tailing Buffer)| 7.5 μl |
|A-Tailing Master Mix after Safe Stopping Point| 7.5 μl|
|**Total Volume**| **15 μl**|

* Mix thoroughly by pipetting up and down several times.
* Incubate the plate/tube using the following protocol:

|Step|Temp.|Duration|
|----|-----|--------|
|A-Tailing|30 °C|30 min|
|Enzyme inactivation|60 °C|30 min|
|HOLD|4 °C|∞|

* Proceed immediately to **Adapter Ligation**.

###Adapter Ligation
* Set up the adapter ligation reactions as follows:

|Component|Volume|
|---------|------|
|Beads with A-tailed DNA| 15 μl |
|Adapter Ligation Master Mix| 17.5 μl |
|**Adapters***| 2.5 μl|
|**Total Volume**| **35 μl**|

####Adapter concentration will vary depending on overall RNA yield, see table below:
|Quantity of starting material|Adapter stock concentration|Adapter concentration in ligation reaction|
|----|----|-----|
|100 – 250 ng|140 nM| 10 nM|
|251 – 500 ng|350 nM|25 nM|
|501 – 2000 ng|700 nM|50 nM|
|2001 – 4000 ng|1400 nM|100 nM|

####This will be where we insert the custom adapters that are barcoded with RE sites

* Mix thoroughly by pipetting up and down several times to resuspend the beads.
* Incubate the plate/tube at 20 °C for 15 min.
* Proceed immediately to **1st Post-Ligation Cleanup**.

###Post-Ligation Cleanup

* Perform a 1X SPRI® cleanup by combining the following:

|Component|Volume|
|---------|------|
|Beads with adapter-ligated DNA| 35 μl|
|Agencourt® AMPure® XP reagent| 35 μl|
|**Total Volume**| **70 μl**|

* Thoroughly resuspend the beads by pipetting up and down multiple times.
* Incubate the plate/tube at room temperature for 5 – 15 min to allow the DNA to bind to the beads.
* Place the plate/tube on a magnet to capture the beads. Incubate until the liquid is clear.
* Carefully remove and discard 65 μl of supernatant.
* Keeping the plate/tube on the magnet, add 200 μl of 80% ethanol.
* Incubate the plate/tube at room temperature for ≥30 sec.
* Carefully remove and discard the ethanol.
* Keeping the plate/tube on the magnet, add 200 μl of 80% ethanol.
* Incubate the plate/tube at room temperature for ≥30 sec.
* Carefully remove and discard the ethanol. Try to remove all residual ethanol without disturbing the beads.
* Dry the beads at room temperature, until all of the ethanol has evaporated. **Caution: over-drying the beads may result in dramatic yield loss.**
* Remove the plate/tube from the magnet.
* Thoroughly resuspend the beads in 25 μl of 10 mM Tris-HCl (pH 8.0).
* Incubate the plate/tube at room temperature for 2 min to allow the DNA to elute off the beads

###Safe Stopping Point
The solution with resuspended beads can be stored at 4 °C for up to 24 hours. Do not freeze the beads, as this can result in dramatic loss of DNA. When ready, proceed to **2nd Post-Ligation Cleanup**.

###2nd Post-Ligation Cleanup

* Perform a 1X SPRI® cleanup by combining the following:

|Component|Volume|
|---------|------|
|Beads with puri ed, adapter-ligated DNA| 25 μl|
|Agencourt® AMPure® XP reagent| 25 μl|
|**Total Volume**| **50 μl**|

* Thoroughly resuspend the beads by pipetting up and down multiple times.
* Incubate the plate/tube at room temperature for 5 – 15 min to allow the DNA to bind to the beads.
* Place the plate/tube on a magnet to capture the beads. Incubate until the liquid is clear.
* Carefully remove and discard 45 μl of supernatant.
* Keeping the plate/tube on the magnet, add 200 μl of 80% ethanol.
* Incubate the plate/tube at room temperature for ≥30 sec.
* Carefully remove and discard the ethanol.
* Keeping the plate/tube on the magnet, add 200 μl of 80% ethanol.
* Incubate the plate/tube at room temperature for ≥30 sec.
* Carefully remove and discard the ethanol. Try to remove all residual ethanol without disturbing the beads.
* Dry the beads at room temperature, until all of the ethanol has evaporated. **Caution: over-drying the beads may result in dramatic yield loss.**
* Remove the plate/tube from the magnet.
* Thoroughly resuspend the beads in 11.25 μl of 10 mM Tris-HCl (pH 8.0).
* Incubate the plate/tube at room temperature for 2 min to allow the DNA to elute off the beads.
* Place the plate/tube on a magnet to capture the beads. Incubate until the liquid is clear.
* Transfer 20 μl of the clear supernatant to a new plate/tube and proceed to *Library Amplication*.

###SAFE STOPPING POINT
The purified, adapter-ligated library DNA may be stored at 4 °C for up to 1 week, or frozen at -20 °C for up to 1 month. When ready, proceed to **Library Amplification**.

###Library Amplificiation

* Assemble each library ampli cation reaction as follows:

|Component|Volume|
|---------|------|
|Purified, adapter-ligated DNA| 10 μl|
|Library Amplification Master Mix| 15 μl|
|**Total Volume**| **25 μl**|

* Mix well by pipetting up and down several times
* Amplify the library using the following thermal cycling protocol:

|Step|Temp|Duration|Cycles|
|----|----|--------|------|
|Initial denaturation|98 °C|45 sec|1|
|Denaturation|98 °C|15 sec|16|
|Annealing*|60 °C|30 sec|16|
|Extension|72 °C|30 sec|16|
|Final Extension|72 °C|5 min|1|
|Hold|10 °C | ∞|1|


##NEEDS TO BE TESTED
*Annealing temperature may need to be optimized*

I think that 8 cycles should be enough.  It's half the maximum recommended number for the kit, and given the that we have another PCR step after DSN, I don't think we need to maximize here

* Place the plate/tube on ice and proceed to **Library Amplification Cleanup**

###Library Amplification Cleanup

* Perform a 1X SPRI® cleanup by combining the following

|Component|Volume|
|---------|------|
|Amplified library DNA| 25 μl|
|Agencourt® AMPure® XP reagent| 25 μl|
|**Total Volume**| **50 μl**|

* Mix thoroughly by pipetting up and down several times.
* Incubate the plate/tube at room temperature for 5 – 15 min to allow the DNA to bind to the beads.
* Place the plate/tube on a magnet to capture the beads. Incubate until the liquid is clear.
* Carefully remove and discard 45 μl of supernatant.
* Keeping the plate/tube on the magnet, add 200 μl of 80% ethanol.
* Incubate the plate/tube at room temperature for ≥30 sec.
* Carefully remove and discard the ethanol.
* Keeping the plate/tube on the magnet, add 200 μl of 80% ethanol.
* Incubate the plate/tube at room temperature for ≥30 sec.
* Carefully remove and discard the ethanol. Try to remove all residual ethanol without disturbing the beads.
* Dry the beads at room temperature, until all of the ethanol has evaporated. **Caution: over-drying the beads may result in dramatic yield loss.**
* Remove the plate/tube from the magnet.
* Thoroughly resuspend the dried beads in 22 μl of 10 mM Tris-HCl (pH 8.0).
* Incubate the plate/tube at room temperature for 2 min to allow the DNA to elute off the beads.
* Place the plate/tube on a magnet to capture the beads. Incubate until the liquid is clear.
Transfer 20 μl of the clear supernatant to a new plate/tube.
