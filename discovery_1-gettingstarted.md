# Connecting to the Discovery cluster

Intro to Discovery (how to set up and run SLURM jobs ) tutorial video:
https://rc.northeastern.edu/support/training/

* Discovery account. Apply by opening a Service-Now ticket with an access request (https://rc.northeastern.edu/support/contact/).

* Login by typing e.g. `ssh lotterhos@login.discovery.neu.edu`, but use your own username

* Read [NU's Getting started on Discovery](https://cpb-us-w2.wpmucdn.com/express.northeastern.edu/dist/1/43/files/2019/08/GettingStartedGuide-1.pdf) (this link is outdated, need to find new location)

* Check out [NU Discovery research computing docs](https://rc-docs.northeastern.edu/en/latest/)

* Need help? Create a ticket automatically by emailing rchelp@northeastern.edu
    * RC bookings
https://outlook.office365.com/owa/calendar/ResearchComputing2@northeastern.onmicrosoft.com/bookings/



## Software on Discovery for Lotterhos Lab

### Conda environments

We use conda environments to load software on Discovery.

See this site for more information on how to load environments and update the `yml` files.

If you create a `yml` for your analysis, be sure to talk with Dr. L about sharing it with the group.

[Shared Lotterhos Group Environments with Research Computing](https://github.com/neu-rc-admin/lotterhos_group)
```  
    lotterhos_R.yml
    lotterhos_RADseq.yml
    lotterhos_RNAseq.yml
    lotterhos_aligners.yml
    lotterhos_gatk.yml
    lotterhos_methylation.yml
    lotterhos_popgen.yml
    lotterhos_utils.yml
    lotterhos_variantCallers.yml
```


Use `conda deactivate` to change conda environments


### information about outdated modules
When we first started using Discovery, we had modules set up for our research

* We have a software module on Discovery for the lab's research
* There are some programs loaded in modules, and others loaded in conda environments. If you are working
in a conda environment, it won't detect programs loaded in the module outside that environment
* One conda environment is `lotterhos-py38`, which is running python 3.8. Note that many bioinformatics programs are not updated for this environment. Slim 3.3.2 is in this environment.
* Another conda environment is `ddocent2`, which is running python 3.7 and all of the ddocent dependencies
```
module show lotterhos/2020-08-24
module load lotterhos/2020-08-24
source activate ddocent2
conda list
```
Use the `module avail` command to show a list of the most currently available software on Discovery.

sratoolkit/2.10.8 was added as a seperate module that was then added to your module, while ddocent-2.7.8 was added to the conda environment "lotterhos-py38" within the anaconda3/L2020-03 module

Old module: lotterhos/2019-11-15, lotterhos/2020-03-18, lotterhos/2020-07-21

* In the future we hope to work on Docker containers for loading R packages and developing containers for specific projects.
A container allows you to create the same environment that you were using when you analyzed the data.

### PackRat environments for R

PackRat environments can be great for using on OOD or Discovery

[Create PackRat environments for R](https://rc-docs.northeastern.edu/en/latest/software/software.html)

## Using Lotterhos nodes on Discovery

There is a lotterhos unix group, which you need to request Dr. L to add you to. It takes a day for the change to propagate so you should be able to see you are part of the ‘lotterhos’ group when typing `groups $USER` in the terminal.
Once you confirm you are part of the unix group and have access to the nodes, you can submit regular jobs using the `--partition lotterhos`

There are 2 nodes each with 36 cores, so we can run parallel programs with up to 36 cores, and serial on up to 72 cores. 
Our nodes are d3037 and d3038. Please communicate with Dr. L about your project and the best way to use resources, so that everyone in the lab has access if they need it.

To get info on the nodes type `sinfo -p lotterhos`, which gives the node IDs, and `lscpu #####` to get info on the CPUs for that node.

`scontrol show partition lotterhos` shows what we can do. There are no limits on job submissions, the default time is 7 days with a max of 30 days. When you type the code, you can see MaxTime=30-00:00:00

`squeue -p lotterhos` shows what is current running. You definitely want to check this before you try to `srun` (see below) or submit jobs!

There is 5GB of memory on each core, with 36 cores/node and 72 cores total across both. So it should be possible to submit an array with 140 jobs at a time, each with 2.5 GB memory, but I haven't tried it yet.

If you are on campus, or offcampus using NU's VPN, you can use this webpage to view resources: https://xdmod.rc.northeastern.edu/

## Troubleshooting and trying code
To develop code and troubleshoot, there is a `debug` partition. You can also use the `lotterhos` partition.
Use the `srun` command with the `--pty` option will output the results of your code on the screen

To run on the lotterhos partition:

`srun -p lotterhos -N 1 --pty /bin/bash`

OR For 20 minutes on the debug partition:

`srun -p debug -N 1 --pty /bin/bash`

[See this page for information about default times on different partitions](https://rc-docs.northeastern.edu/en/latest/hardware/partitions.html#introduction)


## Overview presentation

Here is a presentation from Research Computing on terminology and optimizing workflows in the lab:
[Optimization_Lotterhos_labmeeting_Sekar-V2.pdf](img/Optimization_Lotterhos_labmeeting_Sekar-V2.pdf)

