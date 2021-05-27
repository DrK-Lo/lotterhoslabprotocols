---
layout: page
title: ddRDA Library Prep
subtitle: The protocol for doing a library prep for ddRAD
---

*Note: This protocol is outdated*

# Background 

**D**ouble **d**igest **R**estriction-site **A**ssociated **D**NA **seq**uencing (ddRADseq; Peterson et al. 2012) is a popular approach which uses two restriction enzymes in combination with next generation sequencing to produce inexpensive genome-wide datasets. It does this by; first, using two separate restriction enyzmes that cleave DNA at designated Restriction sites located haphazardly along the genome (F.1A). Second, using a series of steps, labels are attached only to DNA fragments that were specifically cut with each enzyme (F.1B). Lastly, the remaining labeled fragments can be pooled (combined with other similarly treated DNA samples) then be sent away for sequencing (F.1C). Pooling is possible through the use of unique barcodes, which can be used to differentiate sequenced fragments by sample using downstream bioinformatics tools.
FIGURE HERE

Important Considerations:

LIST HERE

Applications:

LIST HERE

Examples:

LIST HERE

# Materials and Equipment

## Reagents and Consumables
* Note that we chose these enzymes because they were not sensitive to methylation.
* Restriction Enzyme 1: (depends) SphI-HF (NEB, 20,000 units/ml) R3182S
* Restriction Enyzme 2: (depends) MspI (R0106S), HpaII (R0171S) or (MluCI NEB, 10,000 units/mL R0538S)
* 10x Concentrate Enzyme Buffer (part of the enzyme package)
* T4 DNA Ligase (NEB, 400,000 units/mL) M0202L
* 10x T4 buffer (part of the Ligase package)
* BioRad Iproof High Fidelity DNA polymerase Cat # 172-5301 (424 for 250 uL [500 units])
* DMSO (part of the package of the Iproof polymerase)
* MgCl2 (part of the package of the Iproof polymerase)
* 1 mg/mL BSA (BSA may not be needed, it is now incorporated in the enzyme buffer, but we keep it in anyway) Cat # BP675-1 Fisher
* 1 M NaCl (follow reagent recipe)
* dNTP Cat # R0181 Thermo Scientific
* SphI-HF adaptors (add page number for ordering adaptors)
* MluCI adaptors (add page number for ordering adaptors)
* Milli-Q Water
* 96 well plates and strip caps or PCR strip tubes Cat # AB-0600 Thermo Scientific
* 1.5 microcentrifuge tubes for PCR mixes (any 1.5 microcentrifuge would work)
* 0.1X TE
* SPRI or Homemade DNA beads (please see the Home made bead protocol if you need to make them)
* EtOH molecular grade 

### Equipment

* Vortexer
* Pipets (ranges from 2uL-1000uL)
* Thermal Cyclers
* Full plate centrifuge (if using a full plate)
* Qubit (we used the Qubit 3.0 Cat #Q33216) and special tubes Qubit Cat # Q32856 or
VWR Cat # PCR-05-C

## DNA quantification
1. Qubit Reagents
2. Bioanalyzer chip

### DNA quantification

1. see ""Link""

# Overview

Genomic DNA is first digested with two restriction enzymes. This results in a pool of
fragments that have the sticky- ended restriction cut sites on either end, and these ends
provide a template for ligation of the customized adaptor sequences. The adaptor
sequences contain the Illumina adaptors and primer sequences for multiplexing sequencing
(and hence provide a binding site for the Illumina PCR primers), and the first barcodes of
5-8 base pairs are incorporated to the left adaptor. The bases at one of the end of each
adaptor oligo correspond to the ligation site; that is, they match the restriction cut site.
NOTE THAT WE MAKE SURE OUR BARCODE DESIGN DOES NOT RE-CREATE
THE RESTRICTION SITE. This can be important when using MspI, which is not
inactivated by heat. The ligation reaction is pooled and concentrated with a bead wash in
preparation for the size selection step. Size selection allows the fragments that are too
small or oversized to be removed. The fragments of the appropriate size are amplied
through a Polymerase Chain Reaction where the fragments with the left and right
adapters get amplied (fragments that carry the wrong combination of adapters won`t
amplify due to the selectiveness of the right adapter). The amplied products now have 2
barcodes, and they can be pooled and concentrated with a bead wash. The nal library is
good for paired-end sequencing.
In January 2016 we ordered new adapters and made some modications. The rst
modication was to use the Peterson protocol, instead of a mix of dierent protocols. The
second modication was the adapters. Both the p5 and p7 adapters were designed to be
oset by a 0-2 bp insertion. For both reads, this will oset the sequencer at the restriction
site so that it is not blinded by the laser. The p7 adapter (right) was designed to also
contain a 4-bp degenerate base sequence that we can use to identify PCR duplicates. This
sequence was accompanied by another 4-bp that were designed to make sure the
adapters anneal together well.
FOR DDRAD, YOU SHOULD CHOOSE ENZYMES THAT ARE NOT SENSITIVE
TO DNA METHYLATION.


## Restriction Enzymes

| Enzyme | Sequence |
|--------|----------|
| SphI | ![SphICutSite](https://www.neb.com/~/media/Catalog/All-Products/52FC70BA01D1413EB2F4396F7375707F/Cut%20Site%20Image/Sph-I-cutsite_1.gif) |
| MspI | ![MSpICutSite](https://www.neb.com/~/media/Catalog/All-Products/C7394B3BC98246FAAF04C42D33CC646A/Cut%20Site%20Image/Msp-I-cutsite_1.gif) |

# Protocol

## Before you start
* Make sure the adaptors are annealed, and also make sure the adaptors and the primer mix are easily accessible in plate format. Please see the section above.
* Be familiar with the Pippin Prep and how to use it.
* Know what size range you want to select - see details in size selection section. To do this, you should have a plan for sequencing.
* Make sure all of the supplies needed for the protocol are present and are sufficient for the number of samples that you will be processing. This protocol is long and it has few stopping steps.
* Make sure the enzyme combination is the best for your organisms. The types of enzymes and the digestion length should be checked at least one time prior this protocol.

## Restriction Digest
From NEB website: There are several key factors to consider when setting up a restriction
endonuclease digestion. Using the proper amounts of DNA, enzyme and buffer components in the
correct reaction volume will allow you to achieve optimal digestion. By definition, 1 unit of
restriction enzyme will completely digest 1 ug of substrate DNA in a 50 ul reaction in 60 minutes.
This enzyme : DNA : reaction volume ratio can be used as a guide when designing reactions.
However, most researchers follow the "typical" reaction conditions listed, where a 5:10 fold
overdigestion is recommended to overcome variability in DNA source, quantity and purity. NEB
offers the following tips to help you to achieve maximal success in your restriction endonuclease
reactions. NEB recommends 10 units restriction enzyme, 1g DNA, 1X NEB Buer (5L), and 1
hour incubation time.
DNA (measured with the Qubit) should ideally be at a minimum total amoung of 1.5 g and
no more than 2.5 g. For example, you could use 10L of 150-250 ng/L of DNA. Keep on ice.
Note that your DNA needs to be concentrated at least 125 ng/L for this protocol (2,500 ng
desired/125ng/L = 20L + may need 5-7uL master mix depending on enzymes).
For each sample prepare a master mix I (Table 1), mix by vortexing and then centrifuge. For
these and all other reactions make sure to prepare an excess of mix to accommodate multiple
rounds of pipetting, particularly if you are working with whole plates. Because the enzymes are
stored in glycerol and other viscous solutions, a substantial volume is lost through adhesion to the
outside of pipette tips. We suggest making more than what you think you will need (this may be
overkill, if you have fewer columns than just do one extra per column).

| Reagent | Number of samples 1X (uL) |
|---------|---------------------------|
| 20 units of Enzyme 1 | (Calc) |
| 20 units of Enzyme 2 | (Calc) |
| (10x Concentrate Enzyme Buffer) | 3uL |
| Genomic DNA (1.5-2.5 ug) | (Calc) |
| Molecular grade H20 to make a final volume of 30 uL | (Calc) |

Note: The original protocol listed 10xT4 Buer instead of the 10X Concentrate Enzyme Buer.
We think this may have been a typo. 10xT4 Buer is designed to work with the Ligase (we use
Ligase in the following section) and the 10x Concentrate Enzyme Buer is designed to optimize
the enzyme. See NEB website.
1. Incubate samples at 37C overnight. NOTE THAT MspI CANNOT BE KILLED BY HEAT.
SUGGEST PROCEEDING IMMEDIATELY TO BEAD WASH.
2. After incubation, let reaction cool to room temperature during this time also remove the
AMPURE XP beads from the fridge and let them warm to room temperature
3. Add 45 uL of AMPURE XP to each reaction, mix with pipetting 10 times, and then let
incubate for 5 mins on the bench
4. Place plate onto the magnet plate and let the beads separate for 5 mins
5. Carefully remove the supernatant from each well and discard
6. Note that you will not be able to remove all of the supernatant without disturbing the
beads. It's best to leave about 5 uL remaining in each well
7. Leaving the plate in the magnet, wash the reaction by adding 200 uL of FRESH 70%
ethanol 70% ethanol should be mixed that day!
8. Remove and discard ethanol and repeat with a second ethanol wash. (From Gold Lab
Protocol: Puritz prefers to use only 150 uL of ethanol for second wash. Hollenbeck prefers
to use only 1 wash step)
9. After nal wash, let plates air dry for 5-10 mins. All ethanol needs to be evaporated, but
beads should not be overdried.
10. Remove plate from magnet and add 30 uL of molecular grade H2O to each well and incubate
for 5 mins. Make sure that water comes into contact with beads by mixing well with pipet
11. Place plate back on magnet and let it separate for 2 minutes, then remove supernatant and
transfer to clean plate
12. If doing a second set of digestion, repeat steps 4-11.

## DNA Quantification 

Check quantication of DNA on Qubit. For extra accuracy, reread standards every 48 samples.
These numbers will be used in next step.

## Adaptor Ligation ( approx. 7 hours) - proceed directly to pooling after

**Note: if performing bs-ddRADseq please remember to incorporate specific methylated adapters!**

1. Thaw adaptors (or the L and R adaptors). Have these adaptors annealed and easily
accessible in plate format.
2. For each sample, calculate the amount of template needed for 100 ng of DNA and calculate
the amount of H20 to add to this amount by using the formula 22.2-(ul of Template)= uL of
H20 (total final volume should be 22.2 uL). If samples are of low DNA concentration, this
can be adjusted to 31.2-(ul of Template)= uL of H20 for all samples.
3. Place the correct amount of H20 and then DNA into ligation plate A. This will take some
time. Take out T4 ligase buffer to thaw during this time.
4. Transfer 2 uL of \left" adapter to each reaction. PAY ATTENTION TO YOUR DESIGN.
5. Create ligation master mix as follows:

| Reagent | Number of samples 1X (uL) |
|---------|---------------------------|
| DNA template | 22.2 |
| (NEB Buffer #4 10X) ligation buffer | 3 uL |
| "right universal adapter | 2 uL |
| T4 ligase (Add this last | 0.8 uL |

6. Add 5.8 uL of master mix to each reaction, as quickly as possible
7. Incubate on bench top for one hour, then place in thermocycler and heat-kill at 65C for 10
min. After the heat-kill, cool the solution at 2C per 90 seconds until it reaches room
temperature. Hold at 4C or place in fridge.

## Pooling and Beadwash
Set up your pools for size selection on the Pippin Prep. You should have experience using the
Pippin before you perform this step.
1. After ligation, it is safe to pool samples within one index. Collect all 30 uL from each well
and place it into a single 1.5 mL tube (Use a 2.0 mL tube if using 40 uL ligations). If you
are using 16 barcodes within an index, this is 16*30 = 480 uL.
2. Mix each pool with pipetting or gentle vortexing. If it is a large volume split each into equal
aliquots according to the number of replicate size selections. (These replicates will be
combined in last step. It doesn't aect the total amount of beads used, and you can choose
to do fewer if you don't have a lot of product).
3. Add 1.5X uL of AMPURE XP to each aliquot, mix with pipetting 10 times, and then let
incubate for 5 mins on the bench. For instance, if you did two replicate size selections of a
pool with 16 barcodes, each one would be 480ul/4 = 120 uL of template and 180 uL of
beads.
4. Place tube onto the magnet bar and let the beads separate for 5 mins
5. Carefully remove the supernatant from each tube and discard
6. Sometimes pulling tube upwards and tilting bottom towards the magnet allows for complete
supernatant removal. If not, leave a few uL.
7. Leaving the tubes in the magnet, wash the reaction by adding 500 uL of FRESH 70%
ethanol 70% ethanol should be mixed that day!. Volume is approximate but should
cover all beads
8. Remove ethanol, let tubes air dry for 2 mins. All excess ethanol needs to be evaporated, but
shiny beads are OK and beads should not be overdried. Pippin is sensitive to EtOH so err
on side of more dry.
9. IF DOING REPLICATES: Remove tubes from magnet and add 30 uL of molecular grade
H2O to each tube and incubate for 5 mins. Make sure that water comes into contact with
beads by mixing well with pipet or gentle vortexing.
10. IF NOT DOING REPLICATES: Remove tubes from magnet and add 30 uL of TE to each
tube and incubate for 5 mins. Make sure that water comes into contact with beads by
mixing well with pipet or gentle vortexing. (We use TE here because it helps the DNA stay
in the well of the Pippin Prep).
11. Place tubes back on magnet and let beads separate for 2 minutes, then remove supernatant
and transfer to a clean 1.5 mL tube. If you used replicates, pool within each index. This
means going from multiple aliquots to one tube for each index.
12. IF YOU USED REPLICATES, DO THE FOLLOWING STEPS TO POOL. IF NOT, YOU
ARE DONE. If you used replicates, add 1.5X uL of AMPURE XP to each tube, mix with
pipetting 10 times, and then let incubate for 5 mins on the bench.
13. Place tubes onto the magnet bar and let the beads separate for 5 mins
14. Carefully remove the supernatant from each tube and discard. Sometimes pulling tube
upwards and tilting bottom towards the magnet allows for complete supernatant removal. If
not, leave a few uL.
15. Leaving the tubes in the magnet, wash the reaction by adding 500 uL of FRESH 70%
ethanol. Volume is approximate but should cover all beads
16. Remove and discard ethanol, and let plates air dry for 2 mins
17. All ethanol needs to be evaporated, but beads should not be overdried. Pippin is sensitive
to EtOH so err on side of more dry.
18. Remove tubes from magnet and add 20 uL of TE to each tube and incubate for 5 mins A.
Make sure that water comes into contact with beads by mixing well with pipet or gentle
vortexing. We use TE here because it helps the DNA stay in the well for the pippin.
19. Place tubes back on magnet and let beads separate for 2 minutes, then remove supernatant
and transfer to a clean 1.5 mL tube.

SAFE STOP POINT. Store at 4C for a month, or -20C for longer. It is important to
save this, as all of this product is not used for the PCR, and if the results of the PCR do not look
good, you can start again from this step.

<img src="http://rs870.pbsrc.com/albums/ab261/rainbowquery/STOP.gif~c200" width="30">

## Size selection (approx. 2 hours)

We use a Pippin Prep to do size selection. Pippin works in a similar way to typical gel
electrophoresis, but uses standardized gel cassettes and automated size selection, rather than a
hand-poured gel and manual excision of fragments from a gel. It is necessary to specify a size
range of fragments that you would like represented in the nal genomic library for sequencing.
The target size range can be adjusted to modify the number of fragments expected for
sequencing. Because techniques such as this typically result in a negative relationship between
fragment size and number, selecting larger fragments should decrease the nal number of
fragments in the template and increase the coverage depth of these regions after sequencing.
Similarly, decreasing the size interval selected will also reduce the number of fragments and
increase coverage. The number of fragments produced is also in part a function of genome size, so
awareness of your organism`s genome size is helpful in making an appropriate choice for size
selection (see Fig. 3 of Alex`s protocol, and Figure 1 in SCHWEYEN 2014). We have typically
used a 100-150 bp range somewhere between 250 and 500 bp in total fragment length (meaning
that we might select, as an example, fragments that are 300 - 400 bp in length).
Dr Lotterhos has an R script that can be used to do an in silico digest of a genome. It is called
ddRADoysterdigestion.R (for C. gigas oyster) but can be applied to any genome. The basic code
is in a post on her blog. You should calculate your size range based on the the number of
fragments in your selected size range, and your plan for sequencing (the number of paired-end
reads and their read length and the total number of bases captured).

## Targeted Index PCR Amplication (8 hours including checking on gel and
nal beadwash)
Following Ligation, pooled groups of samples with individual left adapters are amplied with a
unique right adapter. The right adapter would add a unique barcode to the right side that would
allow all of the pools to be pooled in one lane for sequencing. To ameliorate stochastic dierences
in PCR production of fragments in reactions, we run 3-8 replicate reactions per right barcode
group, and later combine them. NOTE THAT WE USE IPROOF HF-TAQ, which is cheaper than
the Phusion Taq that most people are using. There are alternative polymerases for ddRAD-seq
libraries that may be equally or more eective than Iproof Taq. NEB has good alternatives.
1. Pool all the individuals that have individual left barcodes (the samples would most likely be
already pooled from the size selection step). This protocol was original made to amplify a
total of 10-72ng NEED TO DOUBLE CHECK THIS of DNA, so grab a representative
amount of DNA within this size range.
2. Prepare the following Master Mix. Prepare an individual master mix for each individual
right adapter according to the number of replicate PCRs that you want to run. WE
SUGGEST 6 REPLICATES.

| Reagent | Number of samples 1X (uL) |
|---------|---------------------------|
| ddH2O | 1.75 ( or calc ) |
| 5x Iproof buffer| 4 |
| dNTP (10 nM) | 0.4 |
| Mg Cl2 (50 mM) | 0.5 |
| PCR Primer 1 (10uM) universal | 2 |
| PCR Primer 2 (10uM) index specific | 2 |
| Iproof Taq | 0.2 |
| DMSO | 0.15 |
| DNA pooled template (after size selection) | 5 (or calc) |

3. Thermocycler prole for this PCR: 98C for 1min; 12 cycles of: 98C for 10s, 62C for 30s, 72C
for 30s; nal extension at 72C for 10 min. Hold at 4C.
4. Check if the amplication of the PCR product has gone well by running 2ul of the PCR product in a 2% agarose gel (you can use the same gel to run the nal pooled PCR product
cleaned made in the following step).

## Final beadwash and pooling of PCR products
1. Combine the replicate PCR reactions into a single 1.5 mL tube (6 * 16ul = 96 uL)
2. Add 144 uL (96*1.5 uL) of AMPURE XP to each aliquot, mix with pipetting 10 times, and
then let incubate for 5 mins on the bench.
3. Place tube onto the magnet bar and let the beads separate for 5 mins
4. Carefully remove the supernatant from each tube and discard. Sometimes pulling tube
upwards and tilting bottom towards the magnet allows for complete supernatant removal. If
not, leave a few uL.
5. Leaving the tubes in the magnet, wash the reaction by adding 500 uL of FRESH 70%
ethanol A. 70% ethanol should be mixed that day! Volume is approximate but should cover
all beads
6. Remove ethanol and repeat wash
7. Remove ethanol, let tubes air dry for 5-10 mins. All ethanol needs to be evaporated, but
beads should not be overdried
8. Remove tubes from magnet and add 30 uL of molecular grade H2O to each tube and
incubate for 5 mins
9. Make sure that water comes into contact with beads by mixing well with pipet or gentle
vortexing
10. Place tubes back on magnet and let beads separate for 2 minutes, then remove supernatant
and transfer each index to a clean 1.5 mL tube.
11. These four tubes are your nal library
12. Prepare working solution for the Qubit by combining 199 uL of stock solution with 1 uL of
dye for every reaction.
13. Collect 0.5 ml sample tubes, one for every reaction and two for standards
14. Prepare standards by combing 190 uL of working stock with 10 uL of standard (stored in
refrigerator)
15. Turn on Qubit by touching screen and press button to read new standards. Follow prompts
on screen.
16. Prepare 6 samples for quantication by putting 199 uL of working stock with 1 uL of
sample in a 0.5ml tube
17. Use Qubit to measure DNA content, remembering to press button to calculate stock
concentration and to press button to save data before switching tube and pressing \read
new sample"
18. If each index is between 5-100 ng/uL, celebrate. You are finished.

## Check libraries on Bioanalyzer
