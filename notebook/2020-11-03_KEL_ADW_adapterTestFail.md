# 20201103 - KAPA HyperPlus Kit Failed Test

[Original Report](https://github.com/epigeneticstoocean/2018OAExp_larvae/blob/master/notebook/20201020_KAPAHyperPrepTest_customPrimers.md)

## Summary
In October Alan tried testing some of our Y-adapters with the KAPA HyperPlus library prep kit (**Will need to go to the lab to get details here**) and the PCR reaction failed. The failed PCR may have been due to user error, kit contamination, or a problem an issue with the adapters.

## Major Steps

### Making Adapter and Primer Stocks

In the test to minimize the likelihood that the adapters and primers were contaminated Alan made new adapter and primer working stocks using molecular grade H2O. Both adapters and primers were created from our original stocks stored in the -80. These oligos are either stored at 500um (adapters) or 100uM (primers). 

Stocks created:

| Adapter | Top | Bottom | Final Conc. |
|:------:|:------:|:------:|:------:|
| `Yinline-nobarcode` | `Yinline-nobarcodea` | `Yinline-nobarcodeb` | 15uM |

Standard annealing protocol followed (see link for details).

| Primer | Type | Final Conc. |
|:------:|:------:|:------:|
|`i5_PCRprimer_L5_D505_CTTCGCCT ` | i5 | 20uM |
| `I5_A508_6bp_picoMethyl_A` | i5 | 20uM |
| `PCR2_09_GATCAG` | i7 | 20uM |

### Library Prep

Standard manufacturers protocol was follow (see link for details). Alan used approx 55 ng of unmethylated lambda DNA sheared to 150bp per sample. The test were performed using three samples:

| Sample | Adapter | Primer i5 | Primer i7 | Details |
|:------:|:------:|:------:|:------:|:------:|
| Sample 1 | y-inline_nobarcode | PrimerMix (10x) |  PrimerMix (10x) | Control using KAPA HyperPlus Kit provided primers |
| Sample 2 | y-inline_nobarcode | `i5_PCRprimer_L5_D505_CTTCGCCT ` | `PCR2_09_GATCAG` | Used original PCR primers (ones that worked for Sara) |
| Sample 3 | y-inline_nobarcode | `I5_A508_6bp_picoMethyl_A` | `PCR2_09_GATCAG` | New i5 primers designed for Pico Methylation Kit |

**Deviations from Standard Manufacturers Protocol**

* The lambda DNA was initially quantified at 5 ng/ul prior to sonication but not post. Quantification of the DNA post sonication (performed after the library prep) indicated that the concentration was approximately 2.8 ng/ul. The corrected amount of starting DNA template is updated above.
* Alan was unable to complete the prep in a single day, sampes were held after the A-tailing step at 4C (the fridge) overnight before proceeding to the ligation step.

### Quantification


Results from Qubit HS dsDNA:

| Sample | Step | Conc. (ng/ul) |
|:------:|:------:|:------:|
| Sample 1 | Post Adapter Ligation | 1.07 |
| Sample 2 | Post Adapter Ligation | 1.69 |
| Sample 3 | Post Adapter Ligation | 2.24 |
| Sample 1 | Post PCR (final) | 0.549 |
| Sample 2 | Post PCR (final) | 8.40 |
| Sample 3 | Post PCR (final) | 3.10 |

Based on the Qubit results it appeared that `Sample 1` clearly did not amplify properly, but Sample 2 and 3 may have worked. To conserve reagents Alan focused on running `Sample 2` and `Sample 3`. Specifically, Alan ran both post ligation and post PCR products from `Sample 2` and just the post PCR product from `Sample 3`.

[Tapestation Results](https://github.com/epigeneticstoocean/2018OAExp_larvae/blob/master/labwork/sequencing%20reports/2020-10-21-02.D1000_i5_L1LotterhosLab_KAPATEST.pdf)


### Summary 

It appears that the amplification was not successfull using the KAPA Hyper prep kit following standard manufacturers instructions. From the tapestation we still see the final product in S2 and S3 (the original custom i5 and the new short custom i5,respectively) were the same as the target size of the sheared DNA (150bp). There is also a spike at small bp (~70-80bp) which indicates that some dimer might be present.
