
# Workflow parallelization approaches
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

# Parallelizing your R script

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
