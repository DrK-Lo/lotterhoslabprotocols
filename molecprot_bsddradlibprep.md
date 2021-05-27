---
layout: page
title: bs RAD Library Prep
subtitle: The protocol for doing a library prep for bs ddRAD
---

*Note: this protocol is outdated. Not sure if it works*

# Background

# Materials and Equipment
## 1. DNA Extractions
 * For oyster extractions see: [3a DNA Extraction C. virginica - Materials and Equipment](https://github.com/DrK-Lo/lab-wiki/wiki/3a-DNA-Extraction---C.-virginica-(oyster)#materials-and-equipment)

## 2. RAD digestion, Adapter ligation, Size Selection and ddRAD library prep

* See [ddRADseq Material and Methods](https://github.com/DrK-Lo/lab-wiki/wiki/5---ddRAD-library-prep#materials-and-equipment)

## 3. BiSulfite Conversion 
(based on 96 well plate conversion)

**Cells-to-CpG BiSulfite Conversion Kit (2x96 = 550$)**

| Item | Amount |
|------|----------|
| Binding Buffer | 1 x 192-rxn bottle |
| Binding Plates | 2 plates |
| Conversion Buffer | 10 mL |
| Conversion Reagent | 2 x 96-rxn bottles |
| Denaturation Reagent | 1.mL |
| Desulfonation Reagent | 1 x 192-rxn bottle |
| Elution Buffer | 20 mL | 
| Elution Plates | 2 plates |
| Lysis Enhancer | 2 x 0.5 mL |
| Wash Buffer | 2 x 96-rxn bottles |

**Other Materials**

| Item | # Needed | Cost |
|------|----------|------|
| MicroAmp Clear Adhesive Film |||
| MicroAmp Optical Film Compression Pad |||
| Nuclease-free Water (not DEPC-treated) (1x500mL) |||
| Reaction Plates |||
| Ethanol, molecular grade, >99.5% or 200 proof |||
| Isopropyl alcohol, ACS, reagent grade, >99.5% |||
| Microcentrifuge tubes (Size) |||
| Pipette tips, nuclease-free (Sizes) ||| 

**Equipment**

| Items|
|------|
| ThermoMixer|
| Microcentrifuge |
| Pipettors (sizes) |
| Vortex |
| Water bath 60<sup>o</sup>C |

## 4. BiSulfite PCR

**KAPA HiFi HotStart Uracil+ ReadyMix**

| Item | Amount Total | Amount per Kit | 
|------|--------------|----------------|
| 2X KAPA HiFi HotStart Uracil+ ReadyMix | 1.25mL (50x50uL) or 6.25mL (250x50uL) | 12.5 uL per single reaction | 

**Other Materials**

| Item | # Needed | Cost |
|------|----------|------|
| MicroAmp Clear Adhesive Film |||
| MicroAmp Optical Film Compression Pad |||
| Nuclease-free Water (not DEPC-treated) (1x500mL) |||
| Ethanol, molecular grade, >99.5% or 200 proof |||
| Microcentrifuge tubes (Size) |||
| Pipette tips, nuclease-free (Sizes) ||| 

**Equipment**

| Items|
|------|
| Thermocycler |
| Microcentrifuge |
| Pipettors (sizes) |
| Vortex |

## 6. Quality Control Steps

# Overview
## 1. DNA Extractions
 * See [3 DNA Extraction - Overview](https://github.com/DrK-Lo/lab-wiki/wiki/3-DNA-extraction)

## 2. RAD digestion, Adapter ligation, and Size Selection
 * See [ddRADseq - Overview](https://github.com/DrK-Lo/lab-wiki/wiki/5---ddRAD-library-prep#overview)

## 3. BiSulfite Conversion
![BiSulfite Conversion](https://tools.thermofisher.com/content/sfs/gallery/high/bisulfite1.jpg)

## 4. Bisulfite PCR
KAPA HiFi HotStart is a novel B-family DNA polymerase,
engineered to have increased affinity for DNA, without the
need for accessory proteins or DNA-binding domains.
The intrinsic high processivity of the enzyme results in
significant improvement in yield, speed and sensitivity
when compared with wild-type B-family DNA polymerases
and polymerase blends. When used for the amplification
of next-generation sequencing (NGS) libraries, KAPA
HiFi HotStart DNA Polymerase exhibits high yields with
minimal amplification bias and provides extremely uniform
sequence coverage.

The read-ahead function of proofreading DNA polymerases
detects pro-mutagenic uracil residues in the template
strand and prevents further strand extension, thereby
reducing or completely inhibiting PCR amplification. In
KAPA HiFi HotStart Uracil+ DNA Polymerase, this uracilbinding
pocket is inactivated to enable the amplification
of uracil-containing DNA. The enzyme shows the same
high yield, low GC-bias and coverage uniformity as the
unmodified KAPA HiFi HotStart DNA Polymerase, making
it particularly advantageous for applications employing
bisulfite DNA conversion, which typically produces low
concentrations of AT-rich DNA.

KAPA HiFi HotStart Uracil+ DNA Polymerase has 5’g3’
polymerase and 3’g5’ exonuclease (proofreading) activity,
but no 5’g3’ exonuclease activity. The strong 3’g5’
exonuclease activity results in superior accuracy during
DNA amplification. A proprietary antibody inactivates the
polymerase until the first cycle of denaturation, minimizing
spurious amplification products that may result from
nonspecific priming events during reaction setup and
initiation, and increasing overall reaction efficiency.
KAPA HiFi HotStart Uracil+ ReadyMix (2X) is a ready-touse
cocktail containing all components required for PCR,
except primers and template. The ReadyMix contains
0.2 mM of each dNTP (dATP, dCTP, dGTP, dTTP), and
does not contain dUTP.

## 5. Pooling
 * See [ddRADseq - Overview](https://github.com/DrK-Lo/lab-wiki/wiki/5---ddRAD-library-prep#overview)

## 6. Quality Control Steps

# Protocol
## 1. DNA Extractions

 for oyster extractions see [3a DNA Extraction C. virginica - Protocol](https://github.com/DrK-Lo/lab-wiki/wiki/3a-DNA-Extraction---C.-virginica-(oyster)#protocol)

## 2. RAD digestion

see ['5 ddRAD seq'](https://github.com/DrK-Lo/lab-wiki/wiki/5---ddRAD-library-prep) for details on ddRAD digest.

## 3. Adapter Ligation

SPECIAL NOTES:
Using specific methylated adapters!!!

## 4. BiSulfite Conversion

Link to [bisulfite conversion kit.](https://tools.thermofisher.com/content/sfs/manuals/cms_088098.pdf)

### Acceptable sample types and recommended input amounts

|Input type | Optimal input amount | Minimum input amount | Maximum input amount |
|-----------|----------------------|----------------------|----------------------|
| Purified gDNA | 100 ng to 1ug | 50 pg | 5ug |
| Cultured cells | 5000 cells to 10<sup>5</sup> cells | 10 cells | 10<sup>5</sup> cells |
| Blood | 2.5 uL | 1uL | 5 uL |
--

### Prepare the reagents (for new kits)

Before you use a new kit, prepare the Binding Buffer, Wash Buffer, and Desulfonation Reagent.

1. Add 50 mL isopropyl alcohol (>99.5%) to the bottle of Binding Buffer, then swirl the bottle to mix.
2. Add 120 mL ethanol (>99.5% or 200 proof) to each bottle of Wash Buffer, then swirl the bottles to mix.
3. Add 45 mL ethanol (99.5% or 200 proof) to each bottle of Desulfonation Reagent, then swirl the bottles to mix.

After you prepare the reagents, you will have sufficient reagents for 192 reactions (two 96-well plates).

### Prepare the conversion reagent

For optimal results, prepare the Conversion Reagent immediately before performing the bisulfite conversion.

1. Add Denaturation Reagent and water to the powder in the Conversion Reagent bottle, then mix well:

| Component | Volumne |
|-----------|---------|
| Denaturation Reagent | 260 uL |
| Water | 8 mL |

2. Add 500 uL Conversion Buffer to the Conversion Reagent bottle, then mix again.
3. To improve solubility of the powder, place the Conversion Reagent bottle in a 60<sup>o</sup>C water bath for 10 minutes.
4. Mix by vortexing 2 or 3 times during the 10-minute incubation.

**Note:** It is normal to see trace amounts of undissolved powder in the Conversion Reagent.

After you prepare the bisulfite conversion reactions, you can store and remaining Conversion reagent at -20<sup>o</sup>C for up to one month. Before use, thaw the Conversion Reagent at 50<sup>o</sup>C for 10 minutes, then vortex.

### Denature the DNA

1. Set up the PCR reaction plate. For each sample:
  * Pipet 45 uL into a PCR reaction plate.
2. Denature the DNA in the reaction plate:
  * Add 5 uL Denaturation Reagent to 45 uL gDNA, then pipet up and down.
  * Incubate at 50<sup>o</sup>C for 10 minutes.

### Perform bisulfite conversion of the denatured DNA

Convert unmethylated cytosines to uracil in the denatured DNA samples.

1. Add 100 uL prepared Conversion Reagent to each denatured sample for a total reaction volume of 150 uL, then mix the reaction.

   **Note:** The reaction should not contain any undissolved Conversion Reagent powder after mixing.

2. Incubate the sample in a thermal cycler, selecting the appropriate thermal cycling conditions for your samples:
  * For gDNA input between **100ng and 2ug**, use the general thermal cycling conditions with acceptable recovery and conversion:

   | Temp | Time |
   |------|------|
   | 65<sup>o</sup>C | 30 minutes |
   | 95<sup>o</sup>C | 1.5 minutes |
   | 65<sup>o</sup>C | 30 minutes |
   | 95<sup>o</sup>C | 1.5 minutes |
   | 65<sup>o</sup>C | 30 minutes |
   | 4<sup>o</sup>C | up to 4 hours |

  * For gDNA input between **50pg and 100ng**, use the thermal cycling conditions optimal for recovery but with decreased conversion rates for high sample input:

   | Temp | Time |
   |------|------|
   | 65<sup>o</sup>C | 30 minutes |
   | 95<sup>o</sup>C | 0.5 minutes |
   | 65<sup>o</sup>C | 30 minutes |
   | 95<sup>o</sup>C | 0.5 minutes |
   | 65<sup>o</sup>C | 30 minutes |
   | 4<sup>o</sup>C | up to 4 hours |

  * For crude gDNA input **>2 ug**, use thermal cycling conditions optimal for conversion but with slightly decreased recovery for long amplicons:

   | Temp | Time |
   |------|------|
   | 95<sup>o</sup>C | 3 minutes |
   | 65<sup>o</sup>C | 60 minutes |
   | 95<sup>o</sup>C | 3 minutes |
   | 65<sup>o</sup>C | 30 minutes |
   | 4<sup>o</sup>C | up to 4 hours |

**STOPPING POINT:** If you cannot proceed with desalting and desulfonation immediately, you can store the converted sample at -20<sup>o</sup>C for up to 2 days. Thaw the samples at room temp, then proceed with desalting and desulfonation.

<img src="http://rs870.pbsrc.com/albums/ab261/rainbowquery/STOP.gif~c200" width="30">

### Desalt and desulfonate the samples

Remove salts from the DNA samples, then desulfonate the DNA to remove the sulfonic groups.

1. Combine the DNA samples with Binding Buffer:
  * Add 600 uL of Binding Buffer to wells of a 2-mL 96-well deep block.
  * Transfer each converted sample (150uL) to the corresponding well in the block.
  * Mix by pipetting up and down with a multichannel pipettor.

2. Load the samples onto the Binding Plate:
  * Place a Binding Plate on top of a PureLink 96 Receiver Plate.
  * Load each mixed sample onto the corresponding column in the Binding Plate.
  * Spin the stacked plates at 3100 x g for 3 minutes.
  * Discard the flowthrough.

3. Wash the samples to remove salts:
  * Restack the Binding Plate on top of the 96-well Reciever Plate.
  * Add 600 uL of Wash Buffer to each appropriate column in the Binding Plate.
  * Spin the stacked plates at 3100 x g for 3 minutes, or until all the Wash Buffer passes through the columns.
  * Discard the flowthrough.

4. Desulfonate the DNA:
  * Restack the Binding Plate on top of the 96-well Receiver Plate.
  * Add 200 uL of Desulfonation Reagent to each appropriate column in the Binding Plate.
  * Cover the Binding Plate with adhesive foil, then let plate stand at room temperature (20-30<sup>o</sup>C) for 20 minutes.
  * Spin the stacked plates at 3100 x g for 3 minutes.
  * Discard the flowthrough.

5. Wash the DNA two times. For each wash:
  * Restack the Binding Plate on top of the 96-well Receiver Plate.
  * Add 400 uL of Wash Buffer to each appropriate column in the Binding Plate.
  * Spin the stacked plates at 3100 x g for 3 minutes.
  * Discard the flowthrough.

6. Remove any residual Wash Buffer:
  * Restack the Binding Plate on top of the 96-well Receiver Plate.
  * Spin the stacked plates at 3100 x g for 20 minutes.

   **Important!** Trace amounts of Wash Buffer could inhibit downstream reactions.

  * Discard the flowthrough and the 96-well Receiver Plate.

7. Elute the DNA:
  * Place the Binding Plate on top of a new Elution Plate.
  * Add 100 uL of Elution Buffer directly to the center of each appropriate column in the Binding Plate.
   **Note:** If you started with less than 10ng gDNA, you can reduce the elution volume to 50 uL.
  * Let the plate stand at room temp (20-30<sup>o</sup>C) for 5 minutes.
  * Spin the stacked plates for 3100 x g for 5 minutes.

**STOPPING POINT** Store the converted DNA at 4<sup>o</sup>C for up to 6 months. For long-term storage, store at -20<sup>o</sup>C or -70<sup>o</sup>C. Store aliquots to avoid multiple freeze-thaw cycles.

<img src="http://rs870.pbsrc.com/albums/ab261/rainbowquery/STOP.gif~c200" width="30">

### Assess the yield and quality of the bisulfite-converted DNA


## 5. KAPA HiFi Hotstart Uracil+ PCR 

**IMPORTANT!** The KAPA HiFi HotStart Uracil+ ReadyMix contains an engineered B-family (proofreading) DNA polymerase and uniquely-formulated buffers, and requires specialized reaction conditions. If these conditions are not adhered to, reaction failure is likely. Refer to Important Parameters for more information.

### 1. Prepare the PCR master mix

1.1 KAPA HiFi HotStart Uracil+ reactions MUST be set up on ice since the high proofreading activity of
the enzyme will result in rapid primer degradation at room temperature.

1.2 Ensure that all reagents are properly thawed and mixed.

1.3 Prepare a PCR master mix containing the appropriate volume of all reaction components
common to all or a subset of reactions to be performed.

1.4 Calculate the required volumes of each component based on the following table:

| Component | 25 uL reaction | Final conc. |
|-----------|----------------|-------------|
| PCR-grade water | Up to 25 uL | N/A |
| 2X KAPA HiFi Hotstart Uracil+ ReadyMix | 12.5 uL | 1X |
| 10 uM Forward Primer | 0.75 uL | 0.3 uM |
| 10 uM Reverse Primer | 0.75 uL | 0.3 uM |
| Template DNA | As required | As required |

### 2. Set up individual reactions
2.1 Transfer the appropriate volumes of PCR master
mix, template and primer to individual PCR tubes
or wells of a PCR plate.
2.2 Cap or seal individual reactions, mix and centrifuge
briefly.

### 3. Run the PCR

3.1 Perform PCR with the following cycling protocol:

| Step | Temp. | Duration | Cycles |
|------|-------|----------|--------|
| Initial denaturation | 95<sup>o</sup>C | 3 min | 1 |
| Denaturation | 98<sup>o</sup>C | 20 sec | 15-36 |
| Annealing | 60<sup>o</sup>C-75<sup>o</sup>C | 15 sec | 15-35 |
| Extension | 72<sup>o</sup>C | 15-60 sec/kb | 15-35 |
| Final Extension | 72<sup>o</sup>C | 1 min/kb | 1 |
| Hold | 4<sup>o</sup>C | Infinite | 1 |

### 4. Notes and troubleshooting

##### Amplification of bisulfite-converted DNA

Amplification of bisulfite-treated DNA can be problematic due to DNA damage arising from the harsh conditions required for near-complete conversion of unmethylated cytosines. Conversion conditions should be optimized
to minimize the extent of DNA damage while ensuring
sufficient conversion efficiency.
Because bisulfite treatment converts cytosines to uracils,
which are subsequently substituted with thymines during
PCR, bisulfite-converted DNA is typically much more
AT-rich than the original source DNA. This should be
considered carefully when designing PCR primers, and
cycling parameters such as annealing temperature may
require special attention.

##### MgCl2 concentration

KAPA HiFi HotStart Uracil+ ReadyMix contains a final
(1X) MgCl2 concentration of 2.5 mM, which is sufficient
for most applications. Applications which are likely to
require higher MgCl2 concentrations include long PCR
(>10 kb) and AT-rich PCR, as well as amplification using
primers with a low GC content (<40%). Note that bisulfiteconverted
DNA is typically very AT-rich, as are the primers
used for amplification of these templates; this application
may therefore require additional MgCl2.

##### Prevention of amplicon contamination with UDG

For effective removal of carryover contamination, dUTP
must be added routinely to PCR reactions with KAPA HiFi
HotStart Uracil+ ReadyMix. Typically, dUTP is added to
a concentration of 0.2 mM, but short AT-poor amplicons
may require up to 0.3 mM dUTP for effective removal using
UDG. For amplicons >600 bp, a lower dUTP concentration
(≤ 0.1 mM) may be required for efficient amplification. Low
amplification efficiencies may result from incomplete UDG
inactivation, in which case a longer initial denaturation may
be required to inactivate the UDG prior to cycling. Refer
to the manufacturer’s recommendations for optimal UDG
concentration, and incubation/inactivation conditions.

##### Denaturation

Due to the high salt concentration of the KAPA HiFi HotStart
Uracil+ ReadyMix, it is important to use appropriate
denaturation parameters. An initial denaturation time of
2–5 min at 95°C is recommended to ensure that complex
template DNA is fully denatured before the first primer
annealing step. Use 5 min for complex, genomic DNA and/
or GC-rich targets, and at least 45 sec for less complex
templates such as purified viral or plasmid DNA.

##### Annealing temperature

Due to the high salt concentration of the KAPA HiFi
HotStart Uracil+ ReadyMix, the optimal annealing
temperature for a given primer set is usually different when
compared with other PCR buffer systems. When using the
kit with a specific primer pair for the first time, determine
the optimal annealing temperature with annealing
temperature gradient PCR. We recommend a gradient
from 60–72°C, although some assays may require even
higher annealing temperatures. For assays with optimal
annealing temperatures of 68°C or higher, 2-step cycling
may be performed at the optimal annealing temperature.
Optimal annealing temperatures below 60°C are typically
rare, but may be necessary when using primers with a
high AT content, as is often the case with amplification of
bisulfite-converted DNA.
If a gradient PCR is not feasible, use an annealing
temperature of 60°C as a first approach, and adjust the
annealing temperature based on the results obtained:
• If a low yield of only the specific product is obtained,
lower the annealing temperature in 1–2°C increments.
• If nonspecific products are formed in addition to the
specific product, increase the annealing temperature
in 1–2°C increments.
• If no product is formed (specific or nonspecific), reduce
the annealing temperature by 5°C. MgCl2 concentration
may have to be increased.
If only nonspecific products are formed (in a ladder-like
pattern), increase the annealing temperature by 5°C.

##### Amplicon length

KAPA HiFi HotStart Uracil+ ReadyMix can amplify targets
up to 18 kb in length from simple purified template such
as plasmid DNA, and up to 15 kb in length from high
quality (i.e. not bisulfite-treated), complex genomic DNA.
For efficient amplification of fragments ≥10 kb, higher
template concentrations, and optimization of the Mg2+
concentration, may be required.

##### Primer and template DNA quality

Primers should be designed to minimize the possibility
of primer-dimer formation, self-priming, or nonspecific
priming. Primer pairs should have similar theoretical
melting temperatures (Tm), and should have a GC content
of 40–60%, although this may not be feasible for bisulfite-converted
template DNA. Primers with a GC content
60% may require higher denaturation temperatures
or longer denaturation times, while primers with a GC
content 40% may require lower annealing temperatures
and increased MgCl2 concentrations.
Template DNA quality has a significant impact on the
success of PCR amplification. Degraded, damaged,
or sheared template DNA is usually problematic. While
KAPA HiFi HotStart Uracil+ ReadyMix tolerates uracil,
deamination of dCMP to dUMP in the DNA template will
generate G/C to A/T mutations during amplification.
NOTE: Always dilute and store primers and DNA in
a buffered solution (e.g. 10 mM Tris-HCl, pH 8.0 – 8.5)
instead of PCR-grade water, and minimize freeze-thaw
cycles to limit degradation and maintain primer quality.

##### Cycle number

Excessive library amplification should be avoided to
minimize the following adverse effects:
• increased duplicate reads
• uneven coverage depth and sequence dropout
• chimeric library inserts
• nucleotide substitutions
• heteroduplex formation
To minimize over-amplification and associated unwanted
artifacts, the number of amplification cycles should be
optimized to ensure a sufficient amount of amplified library
for the next step in the workflow (capture or sequencing),
plus the amount needed for library QC and/or archiving.
Depending on the sequencing application and degree
of multiplexing, 100 ng – 1.5 μg of amplified library is
typically required.
The number of cycles typically required will vary, depending
on input amount and quality. Size selection of libraries
at any part in the library construction process results in
significant loss of material and as a result, 2–4 additional
cycles are required for workflows which include a sizeselection
step prior to library amplification.

##### Primer depletion and library over-amplification

In library amplification reactions (set up according to the
recommended protocol), primers are typically depleted
before dNTPs. When DNA synthesis can no longer take
place due to primer depletion, subsequent rounds of
DNA denaturation and annealing result in the separation
of complementary DNA strands, followed by imperfect
annealing to non-complementary partners. This
presumably results in the formation of so-called “daisychains”
or tangled knots, comprising large assemblies
of improperly annealed, partially double-stranded,
heteroduplex DNA. These species migrate slower and
are observed as secondary, higher molecular weight
peaks during the electrophoretic analysis of amplified
libraries. However, they are typically comprised of library
molecules of the desired length, which are separated
during denaturation prior to target enrichment (capture)
or cluster amplification. Since these heteroduplexes
contain significant portions of single-stranded DNA,
over-amplification leads to the under-quantification of
library molecules with assays employing dsDNA-binding
dyes. qPCR-based library quantification methods, such
as that employed by the KAPA Library Quantification
Kit, quantify DNA by denaturation and amplification,
thereby providing a more accurate measurement of the
amount of adapter-ligated molecules—even if the library
was over-amplified.

## 6. Pooling
## 7. Quality Control Steps
