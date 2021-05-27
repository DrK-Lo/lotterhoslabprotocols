#  Optimizing

Here is a presentation from Research Computing on terminology and optimizing workflows in the lab:
[Optimization_Lotterhos_labmeeting_Sekar-V2.pdf](img/Optimization_Lotterhos_labmeeting_Sekar-V2.pdf)

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

## Make sure to optimize on the paritition that you will use

For example, the `lotterhos` partition runs a lot faster than the `short` partition

If you optimize on the  `lotterhos` partition, then your jobs will run out of time on the `short` partition
