# Connecting to the Discovery cluster

* Discovery account. Apply by opening a Service-Now ticket with an access request (https://rc.northeastern.edu/support/contact/).

* Login by typing e.g. `ssh lotterhos@login.discovery.neu.edu`, but use your own username

* Read [NU's Getting started on Discovery](https://cpb-us-w2.wpmucdn.com/express.northeastern.edu/dist/1/43/files/2019/08/GettingStartedGuide-1.pdf) (this link is outdated, need to find new location)

* Check out [NU Discovery research computing docs](https://rc-docs.northeastern.edu/en/latest/)

* Need help? Create a ticket automatically by emailing rchelp@northeastern.edu


## Software on Discovery for Lotterhos Lab

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

Use `conda deactivate` to change conda environments

[Create PackRat environments for R](https://rc-docs.northeastern.edu/en/latest/software/software.html)

sratoolkit/2.10.8 was added as a seperate module that was then added to your module, while ddocent-2.7.8 was added to the conda environment "lotterhos-py38" within the anaconda3/L2020-03 module

Old module: lotterhos/2019-11-15, lotterhos/2020-03-18, lotterhos/2020-07-21


* In the future we hope to work on Docker containers for loading R packages and developing containers for specific projects.
A container allows you to create the same environment that you were using when you analyzed the data.

## Using Lotterhos nodes on Discovery

There is a lotterhos unix group, which you need to request Dr. L to add you to. It takes a day for the change to propagate so you should be able to see you are part of the ‘lotterhos’ group when typing `groups $USER` in the terminal.
Once you confirm you are part of the unix group and have access to the nodes, you can submit regular jobs using the `--partition lotterhos`

There are 2 nodes each with 36 cores, so we can run parallel programs with up to 36 cores, and serial on up to 72 cores. 
Our nodes are d3037 and d3038. Please communicate with Dr. L about your project and the best way to use resources, so that everyone in the lab has access if they need it.

To get info on the nodes type `sinfo -p lotterhos`, which gives the node IDs, and `lscpu #####` to get info on the CPUs for that node.


`scontrol show partition lotterhos` shows what we can do. There are no limits on job submissions, the default time is 7 days with a max of 30 days.

`squeue -p lotterhos` shows what is current running. You definitely want to check this before you try to `srun` (see below) or submit jobs!

## Troubleshooting and trying code
To develop code and troubleshoot, there is a `debug` partition. You can also use the `lotterhos` partition.
Use the `srun` command with the `--pty` option will output the results of your code on the screen

To run on the lotterhos partition:

`srun -p lotterhos -N 1 --pty /bin/bash`

OR For 20 minutes on the debug partition:

`srun -p debug -N 1 --pty /bin/bash`

[See this page for information about default times on different partitions](https://rc-docs.northeastern.edu/en/latest/hardware/partitions.html#introduction)

## Example submission scripts
TO DO - put together a folder


## Workflow parallelization approaches
Workflow parallelization approaches:

*a. One the shared resources*, limits on each partition are determined according to the following table: https://rc-docs.northeastern.edu/en/latest/hardware/partitions.html#introduction. If your jobs have exceeded those limits, this may have been the cause of job terminations.

*b. On the “lotterhos” partition*, you do not have any restrictions on number of submitted jobs, or requested cpus. To submit to the lotterhos partition, simply set the SLURM flag for this partition:

For an interactive job (example): `srun -p lotterhos --nodes=1 --cpus-per-task=1 --pty --time=24:00:00 /bin/bash`

This example will allocate a single node with 1 CPU (and --ntasks=1 by default, but alternatively, you can also use this instead:

`srun -p lotterhos --nodes=1 --ntasks =1 --pty --time=24:00:00 /bin/bash` for 24 hours, and flag `--pty` will set all output to be printed to the screen. `/bin/bash` is the command to be run for this job, so any bash command after this will be executed.

If you run this command, you can type: `lscpu` to get the hardware info (such as core count).

For a batch (background) job, adding the following to your bash script is equivalent:
```
#SBATCH -p lotterhos
#SBATCH --nodes=1
#SBATCH --cpus-per-task=1
#SBATCH --time=24:00:00
```
If your shell script looks the same, and the only thing changing is a particular parameter, for example:
```
#SBATCH -p lotterhos
#SBATCH --nodes=1
#SBATCH --cpus-per-task=1
#SBATCH --time=24:00:00
program input-X output-X
```
Then you can also take advantage of the job-array structure to submit multiple jobs at a time. Each SLURM job that is defined as array will have several bash variables associated with this that are defined once the job is submitted. The main important variable that can be useful is: `$SLURM_ARRAY_TASK_ID`
For example, if you create a SLURM array job with 10 jobs in the array, then the values `$SLURM_ARRAY_TASK_ID` will get are: 1,…,10 (each job in the array will be assigned with a number 1-10, and can be distinguished this way). Here, %10 means all 10 jobs are set to run together. Setting %1 means they will run one after another.
```
#SBATCH -p lotterhos
#SBATCH --nodes=1
#SBATCH --cpus-per-task=1
#SBATCH --time=24:00:00
#SBATCH --array=1-10:%10
program input-$SLURM_ARRAY_TASK_ID output-$SLURM_ARRAY_TASK_ID
```
This setup will run the program on a specific input file based on the $SLURM_ARRAY_TASK_ID  value (input-1,input-2,…,input-10) and will output the results to output file named based on the value of $SLURM_ARRAY_TASK_ID  (output-1,output-2,…,output-10).

*c. Parallelizing your R script:* You can also leverage the entire 36 cores on each on the lotterhos nodes in a single job by using a threading parallelization scheme. Specifically, you can use the parallel processing R libraries such as “foreach” to increase the efficiency of your loops. You can then parallelize specific chunks of your code (mainly, loops) by importing the parallel libraries. For example, if your r code is this:
```
#import packages
library(foreach)
library(doParallel)
#number of iterations
iters<-1e4
#setup parallel backend to use 8 processors
cl<-makeCluster(36)
registerDoParallel(cl)
#start time
strt<-Sys.time()
#loop
ls<-foreach(icount(iters)) %dopar% {
    to.ls<-rnorm(1e6)
    to.ls<-summary(to.ls)
    to.ls
    }
print(Sys.time()-strt)
stopCluster(cl)
```
source: https://beckmw.wordpress.com/2014/01/21/a-brief-foray-into-parallel-processing-with-r/

Then, you can set up an array job that looks like this:
```
#SBATCH -p lotterhos
#SBATCH --nodes=1
#SBATCH --cpus-per-task=36
#SBATCH --time=24:00:00
#SBATCH --array=1-10:%10
r-parallel-program  input-$SLURM_ARRAY_TASK_ID  output-$SLURM_ARRAY_TASK_ID
```

## Optimizing
To view your recent jobs, use `acct -S 2020-08-01 -u lotterhos` will list all jobs since that date for user lotterhos

To learn about how much memory a job used, type `seff jobID` - will give memory for the job that was requested and how much was used.

*Check job efficiency and performance:*

*a. R code in part c from Workflow parralelization approaches shows an example of how you can capture the run time of a particular job*, or a parallel segment by printing out the time difference it takes to calculate a particular part. You can also modify this to calculate the total time it took to run your code. To find the best performance, I would recommend to benchmark the calculations on (for example) 1,24,8,16,32 cores and see if at some point it levels off in terms of run time, this may mean that there would be no benefit to request more cores beyond that. Research Computing can discuss performance testing, just schedule another consultation time.

*b. You can also look at the efficiency and memory usage of your jobs by looking at the completed jobs from your slurm history*, by typing: `acct -S 2020-08-10 -u albecker` Then, selecting a particular job (might be beneficial to have a small script that runs through all jobs, since you had over 100,000 jobs this month, I can help with that too if needed) and using the seff command to extract the efficiency. For example:

```
$ seff 13291706
Job ID: 13291706
Cluster: discovery
User/Group: albecker/users
State: COMPLETED (exit code 0)
Cores: 1
CPU Utilized: 00:01:58
CPU Efficiency: 99.16% of 00:01:59 core-walltime
Job Wall-clock time: 00:01:59
Memory Utilized: 284.50 MB
Memory Efficiency: 0.56% of 50.00 GB
```

Here, you can see that the CPU efficiency was very high at 99%, but you ended up using less than 1% of the memory you requested (284.50 MB out of 50.00 GB). This information is useful to better allocate and utilize resources in the future.

*c. It is also recommended to perform short testing prior to submit long jobs to the cluster.* You can use the “debug”, “express” or the “lotterhos” partition and you can run the job interactively. For example, this will give you resources on the debug partition (up to 20 minutes). `srun -p debug --nodes=1 --ntasks=16 --pty /bin/bash`


## Open OnDemand

* Check on the Open On Demand - R studio and Jupyter notebooks! Open OnDemand [ood.discovery.neu.edu](ood.discovery.neu.edu)
  * You also open a JupyterHub interface (jupyterhub.discovery.neu.edu)
  
* To view your home directory on Discovery with OOD, you have to log in to Discovery at the command line / Terminal first

* Previous workshop materials are available at `/shared/rc/training`. For example, the latest one research computing did focused on introduction to Slurm and Discovery as well as how to set up python environments. 
  * You can copy it to your home directory by typing the following command (at the command line): `cp -r /shared/rc/training/training_111219 ~`
  * You can then view it via Open OnDemand
  
* Although OOD allows file transfer, this is not recommended because there are no automatic checks for file corruption. Use Globus instead.


## Globus File Transfer

* Globus is a system for transferring files. The pros:
  * It's fast
  * If your connection gets interrupted, it automatically picks up where it left off
  * It automatically checks that your files were not corrupted during the transfer
  * Globus is already integrated with Discovery and our lab files.
  * It makes transferring files among your laptop, your collaborator(s), and Discovery easy.
  * A __Globus endpoint__ is a folder on a computer that you want to transfer files to or from
  * A __Globus Collection__ is a folder on a computer that contains a collection of files. You may create several endpoints within a collection to share with specific people.
  
#### Getting started with Globus on Discovery

  * Go to [globus.org](globus.org)
  * Click on "Login", from the dropdown list choose "Northeastern University", login with your NU credentials
  * Click on "File Manager" and the Search Icon. In the Search Box type "Northeastern". Choose "northeastern#discovery". This is your home directory on Discovery. Click on the Bookmark Icon to add this to your bookmarks.
  * Dr. Lotterhos will share through Globus the specific folders that you will have access to on the Discovery Lab Storage
  
#### Getting started with Globus on your laptop

  * Download [Globus Connect Personal](https://www.globus.org/globus-connect-personal) for your laptop and follow the instructions to setup and configure your laptop as an endpoint
  * Make sure to save your setup key, you'll need it again to open the Globus App on your computer
  * If you get error messages, try restarting your Terminal
  
#### Transferring files in Globus
 * Click on "File Manager"
 * In the upper right, click on the Double-Panel Icon. This will open two panels - choose the collections that you would like to transfer files between, and drag and drop!
 
 - can view other's scratch directories and copy files, but not edit
 - other users can view /research/lotterhos and edit/delete files
 - 
  
#### Sharing endpoints

  * A __Globus endpoint__ is a folder on a computer that you want to transfer files to or from. In Globus, click on the folder ("Collection") that you would like to allow file transfer to or from.
  * To let someone download files in that folder, give them access to "read" the files
  * To let someone upload files to that folder, give them access to "read and write" to the folder
    * Note that if you allow the person you are sharing with to write to the folder, this gives the person you are sharing with the opportunity to delete or replace any files within that folder, so proceed with caution. I recommend creating a specific "sharedwith_X" folder for having someone transfer files to you.
  * Steps
    * In Globus, click on the folder ("Collection") that you would like to allow file transfer to or from.
    * Click on "Share", "Add a Shared Endpoint"
    * To view your shared endpoints, click on "endpoints", “shareable by you”
      * click on the endpoint and the "sharing" tab
      * click on "Add Permissions - share with" and enter the email associated with the globus account you want to share with
  
  
 Question for research computing - can we link Globus with Google drive? https://docs.globus.org/how-to/access-google-drive/

  
## Lotterhos Lab vs. Personal Storage on Discovery

* We have **active** storage (10 TB) that should be used for 'active' projects, and **archival** storage for storing 
raw files and outputs from projects. Please be smart about how you use archival storage and work with Dr. Lotterhos to 
make sure only relevant files are being archived.

* In addition each user has a home directory and a scratch directory.

* **Active Lotterhos Lab storage** 
  * Ask Katie to share a Globus endpoint with you. The endpoint with include the words "smb Volumes/lotterhos"
  * Within this storage space we have a shared folder for each project, that only the people on that project have access to.

* **Archival Lotterhos Lab storage** (25 TB for lab). Northeastern NESE collection. 
  * Path: `/lotterhosarchive/`
  * Within this storage space we will have a shared folder for each project, that only the people on that project will have access to.

* **Your home directory on Discovery**.  
  * Path: `/~/`
  * Note that only you have access to these files.
  
* **Your scratch directory on Discovery**. Use this for intermediate outputs that are not backed up. 
  * Path: `/scratch/username`
   * Note that only you have access to these files.

* **Active Lotterhos Lab storage: more information** (? TB for lab).  
  * smb://nunet.neu.edu/rc-shares/lotterhos/
  * Within this storage space we have a shared folder for each project, that only the people on that project have access to.
  * Because accessing this server is done through a computer, it makes transferring files specific to the computer that the server is mapped to. Typically, you will ask Katie to share the Globus endpoint for this server that is set up through the lab iMac. As long as the server is mapped to the computer (typically lab iMac) and that connection is not interrupted, you should have no problems. 
   * From a laptop or over wifi, transfers of large files are very slow. This is why we map to the server through the iMac. The point of all the steps we outline below is so we can use Globus to transfer files from the smb drive to Discovery.
  * To connect to the smb server, follow these directions to map to the server on a computer [this document](accessing_shared_storage_2020.pdf) (typically Katie only)
  * Setting up a Globus endpoint for the folder to share (typically Katie only)
   * _Intitial step if Globus personal endpoint for the computer is not set up_: Download and install the Globus Connect Personal App. In Globus web app, click on "Add a personal endpoint" and enter the key in the Desktop app.
   * _Intial setup if working from a home laptop_: Use GlobalProtect to establish a VPN connection (vpn.northeastern.edu) (if you are having trouble establishing the VPN connection on a Mac, check your Security and Permissions settings and give the app permissions, see image). Then you should be able to map to the server. 
    * ![](globalprotectgetittowork.png) 
   * Step 1: In the Globus Desktop App, then go to Preferences-> Access and click the "+" sign. On a Mac, at the top center click on the bar, click on the name of the computer, and you should see the mapped server there as a volume `Volumes/lotterhos`. Click on it and add it to the list.
    * ![](howtofindvolumeinglobusconnect.png)
   * Step 2: In the Globus Web App, go to the endpoint for the computer. Then type `Volumes/lotterhos/` in the path. Save it as a bookmark.
   * Step 3: Before you can conduct file transfers from a personal endpoint, you need to have a "Globus Plus Account". Email James Macalino at NU research computing to get added. You will then receive an email.
  


