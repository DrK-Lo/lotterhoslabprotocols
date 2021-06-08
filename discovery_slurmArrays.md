# Parallelization with `--array`


## Overview

Brief review of using the `#SBATCH --array` slurm argument to restrict the number of jobs running in parallel on Discovery. Arrays seem to be most effective when you have a large number of jobs that all require the same number of resources and the user wants to limit the amount of the computing resource being used at a particular time. This guide follows the same template format from the lotterhos wiki, which reads through and leverages a reference file that contains a number of file names corresponding to files you wish to process. For example, this cod contain a list of raw sequence files (e.g., `fq.gz`) that you with to perform trimming and qc on.

### Breaking down the `--array` argument

The `--array` argument can take a single integer,`1`, or a range, `1-32`, of integers that the slurm script will iterate through. Following the range of integers you specify the number of these values you wish to process simultaneously using the `%` operator. For example, if you wish to iterate through the range of integers in batches of 4 you could code: `#SBATCH --array=1-32%4`

**Other options**

```
# A job array with array tasks numbered 1, 2, 5, 19, 27.
#SBATCH --array=1,2,5,19,27

# A job array with array tasks numbered 1, 3, 5 and 7.
#SBATCH --array=1-7:2
```

### Using the `--array` argument in your script

Including the above example (`#SBATCH --array=1-32%4`) in your slurm script will effectively iterate through your slurm script 32 times, by running 4 simultaneous instances (or jobs) of the script at a time on Discovery. However, running the same script with identical parameters (or files) may not be particularly useful. Instead we probably want to run the same script but apply it to a different set of data or use different parameters. At the very least we want to be able to create unique outputs for each iteration!

Conviently, the `--array` argument creats a unix variable - `SLURM_ARRAY_TASK_ID`, which in the case above references the specific integer that corresponds to the particular instances of the script. For example, the first iteration of your slurm script will have `SLURM_ARRAY_TASK_ID=1`.

This could be leveraged in multiple ways, but one option is using this index to extract specific lines from a reference script. The data on these lines could be anything, but having file names is a particular useful approach if you want to apply your script to multiple files.

**Short illustration**

```
VARNAME=`sed "${SLURM_ARRAY_TASK_ID}q;d" path/to/reference/reference.txt`

file1 = path/to/data/${VARNAME}

echo '${file1}'
```

Example of reference file:
```
datafile1.csv
datafile2.csv
datafile3.csv
```

Example output in `.out` file
```
datafile1.csv
datafile2.csv
datafile3.csv
```

### Pratical example

Script performs bismark mapping, `bismark` on list of files based on the file names in a reference text file, `sample_files.txt`. Based on the `--array` argument, I am peforming the mapping on 32 samples, processing 4 samples at a time.

```
    #!/bin/bash

    #SBATCH --job-name=DNAMethylation_mapping
    #SBATCH --mem=100Gb
    #SBATCH --mail-user=downey-wall.a@northeastern.edu
    #SBATCH --mail-type=FAIL
    #SBATCH --partition=lotterhos
    #SBATCH --nodes=1
    #SBATCH --cpus-per-task=32
    #SBATCH --array=1-32%2
    #SBATCH --output=/work/lotterhos/2018OALarvae_DNAm/slurm_log/DNAm_mapping_%j.out
    #SBATCH --error=/work/lotterhos/2018OALarvae_DNAm/slurm_log/DNAm_mapping_%j.err

    ## Store name of individual sample
    VARNAME=`sed "${SLURM_ARRAY_TASK_ID}q;d" 2018OALarvae_DNAm/RAW/sample_files.txt`

    ## Code for running bismark (DNA methylation sequence mapper)

    i=$(ls 2018OALarvae_DNAm/trimmed_files/${VARNAME}_R1*fq.gz | rev | cut -d'/' -f 1 | rev) 
    j=$(ls 2018OALarvae_DNAm/trimmed_files/${VARNAME}_R2*fq.gz | rev | cut -d'/' -f 1 | rev)

    # Run Bismark
    bismark --non_directional \
    --parallel 32 \
    --genome oyster_references/haplo_tig_genome \
    --score_min L,0,-0.4 \
    --bowtie2 \
    -1 2018OALarvae_DNAm/trimmed_files/${i} \
    -2 2018OALarvae_DNAm/trimmed_files/${j} \
    -o 2018OALarvae_DNAm/mapped_files
```
