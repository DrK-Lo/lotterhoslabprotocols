---
layout: page
title: Determining Barcodes and Indexes for Illumina Sequencing
subtitle: Tips for determining barcodes and indexes for Illumina Sequencing
---

First, you should make a plan for the adapters that you are going to use for each sample. As you choose adapters, you want to ensure that there is not low diversity in the indexes or in the first 5-6 bases of every read.  Low diversity can result in high error rates because of an unbalanced color scheme as explained here by Illumina:

[Illumina Low Plex Pooling Guidelines](https://www.illumina.com/documents/products/technotes/technote-nextera-rapid-capture-low-plex-pooling-guidelines.pdf)

The term “nucleotide diversity” describes the proportion of each nucleotide (A, T, C, and G) at each position in a sequencing library. A “balanced” or “diverse” library has equal proportions of A, C, G, and T nucleotides at each base position in a sequencing library. In particular, nucleotide diversity is key during the first 4–7 cycles of Read 1 for all Illumina sequencing systems. The sequencing software uses images from these early cycles to identify the location of each cluster in a process called template generation. This results in overclustering. Overclustering creates image analysis problems, including loss of focus, poor template generation, and issues with cluster registration. The increased overall signal brightness of the  flow cell makes it difficult for the sequencer to read and find the appropriate focal plane. 

[Illumina Consequences of Overclustering](https://support.illumina.com/content/dam/illumina-marketing/documents/products/other/miseq-overclustering-primer-770-2014-038.pdf)

Next, and especially if you are doing library prep for the first time, I suggest that you draw out what is happening to the DNA or RNA at every step of the process:

[Example Genomic Library Prep with p5 inline barcode and index in p7 PCR Primer](https://docs.google.com/spreadsheets/d/1VSqr03MbtS0hFzgnOu3-oHL2fzf4qL5jfEEyDE76bv4/edit#gid=0)

[Example Library prep with inline barcodes and dual indexes](https://docs.google.com/document/d/1xr99sMucP-x2rK6K61vtGHKNahl9UYFwh_oEb0AtHX8/edit)

For genomic DNA library prep, we are now working with inline barcodes on the P5 (left) adapter and indexes on the P7 (right) adapter. See above figure for details (note: KEL thinks there is issues with this system and this may change). These can give up to 12*12 = 144 unique barcodes. But, keep in mind that every sample can't have the same barcode (e.g., can't have 12 samples with 1 barcode and 12 indexes), and every sample can't have the same index (e.g., can't have 12 samples with 12 barcodes and 1 index) because of the low-diversity problem.

Also, note that the indexes will also demultiplex with Illumina's software at the sequencing facility. But after you receive them, the reads will need to be further demultiplexed using the inline barcodes with a program such as STACKS.

[Lotterhos adapter and primer database](https://docs.google.com/spreadsheets/d/1bro9DbuJB9zH8KtIUH3H7FHrlVO2gZYbIsUbx7yax70/edit#gid=0)
[Lotterhos y-adapters with inline barcodes and dual indexes](https://docs.google.com/spreadsheets/d/1Ok9EEkloK6RCCpKsc4tjklF4UygO8SnATWK8HGLgpvY/edit#gid=0)
