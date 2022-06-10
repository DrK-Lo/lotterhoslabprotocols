#  Bioinformatics resources

## Data Skills

Vince Buffalo's _Bioinformatic Data Skills_ is a great book to build skills. Katie has a set of great readings for learning, contact her for more info.

## RAD seq

https://radcamp.github.io/NYC2019/RADCamp-PartII-Day1-AM.html

https://github.com/dereneaton/ipyrad/blob/master/newdocs/assembly_guidelines.rst

http://www.popgen.dk/software/index.php/PCAngsd handle genotype likelihoods

## VCF files and population structure

What is a VCF? https://samtools.github.io/hts-specs/VCFv4.2.pdf

Katie also has some lectures on VCF files.

### Filter VCF table and produce a PCA plot

When getting started, it's best to filter for relatedness and linkage disequilibrium, so that you have a quasi-independent set of individuals and SNPs. 

Check related individuals with vcf using vcftools (--relatedness)

Filter the VCF file. Use VCF tools to do this: http://vcftools.sourceforge.net/
- for minor alleles < 0.05 (if you have a lot of SNPs, or 0.01 if you don't have a lot of SNPs)
- for missing data at SNPs (keep SNPs in at least X% of individuals in all dataset)
- for missing data at population level (keeps SNPs with calls in X% or higher of individuals per population)
- for individuals with low SNP count (keep individuals with higher than X% of SNPs called)
- Depending on the context, X% might be 80% or might be 100%

To use the bigsnpr R package, you will have to change your data from the VCF format to a genotype matrix with 0/1/2 counts of the alternate allele.
[Transform from vcf to (plink to) raw](https://github.com/laurabenestan/RDA_outlier). See the first steps in this tutorial. 

The presence of LD can bias principal components. This [paper](https://academic.oup.com/bioinformatics/article/36/16/4449/5838185?login=true) explains the problem.  Read about [filtering for LD with pruning and clumping](https://privefl.github.io/bigsnpr/articles/pruning-vs-clumping.html)

[Filter the raw data using snp_autoSVD (it’s at the end of the tutorial)](https://privefl.github.io/bigsnpr/articles/how-to-PCA.html)
This tutorial also teaches you how to do a PCA.


### Run an RDA

Before you run an RDA and do some of the things in these tutorials, talk to Dr. L about your plan. Outlier SNP analysis with RDA have a lot of false positives, but the individual scores are very useful.

https://popgen.nescent.org/2018-03-27_RDA_GEA.html

https://github.com/laurabenestan/RDA_outlier

Katie also has some RDA code on simulations and oyster data.

### Run a GWAS or GEA

Genotype-phenotype association: LFMM2. [Read the paper lfmm2](https://academic.oup.com/mbe/article/36/4/852/5290100) and [LEA3](https://onlinelibrary.wiley.com/doi/10.1111/1755-0998.13366)

[LFMM2 functions](https://rdrr.io/bioc/LEA/man/lfmm2.html)

[LEA installation](http://www.bioconductor.org/packages/3.3/bioc/html/LEA.html) Check with Katie this is correct before running

### Other resources

[Marine Omics working group](https://marineomics.github.io/index.html)



