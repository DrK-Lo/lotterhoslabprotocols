---
layout: page
title: Accessing and Using Defiance Cluster
subtitle: Notes on how to access and use the defiance cluster
---

# Note we no longer use this resource.

To use the defiance cluster you need to contact Stefan (graduate student in Vollmer lab; S.Kaluziak@northeastern.edu) and request access

You'll need to send Stefan your public key. Public keys can be created following the steps here: <https://confluence.atlassian.com/bitbucketserver/creating-ssh-keys-776639788.html>
And is described in ![this pdf](img/RSAKeys.pdf)

Ask Stefan to give you access to `/shared_lab` directory

Stefan has pre-installed a lot of packages on compliance. [Click here](/installedpackages.md) for a complete list, including version numbers.  


If you require additional programs while using cluster, you'll need to ask Stefan to install it. E-mail him the software and version, and he should have it installed within 24 hours.

### Description of defiance
Defiance is set up with a main node (where you log in) and compute nodes
Not all files/folder map perfectly across the main node and compute nodes
Each user has their own remote repository that is private

### Accessing Cluster
**After Gaining Access from Stefan**
Log onto cluster by opening Terminal and typing: `ssh username@defiance.neu.edu` (e.g. `ssh br.ford@defiance.neu.edu`)
You'll then log onto a computing node. The basic outline of computing nodes is below:

`comp5` (Lotterhos)
`comp6`
`comp7` (Bowen)
`comp8`

Log onto comp5 by typing: `ssh comp5`

**You can only access the `/shared_lab` directory by logging on to one of the computing nodes (comp5)**

To transfer files from your computer to a defiance remote directory:
First, go to the folder on your computer with the file in it. Then transfer the file(s) into a remote folder
`my_laptop\$ scp ./my_file br.ford@defiance.neu.edu:/home/br.ford/br.ford_remote/my_folder`

Or to download to your personal computer from defiance, go to the folder on your computer where you want the file, then:
`my_laptop\$ scp br.ford@defiance.neu.edu:/home/br.ford/br.ford_remote/my_folder/my_file .`

To download the file to a different directory than the one you are currently in, simply replace the '.' at the end of the command with the path to that directory.

`/shared_lab` cannot be accessed with `scp`, so you'll need to move (`mv`) things to your remote repository before downloading to your personal computer


### Checking and managing resource usage on defiance

Defiance is a shared resource, so it is important to monitor the resources being used in order to avoid overloading the server. Before beginning any resource-intensive analysis, you should log into comp5 and enter the command `htop` to bring up the following interface:


<img src="../img/htop_screenshot.png" alt="htop example" />


One way to immediately get a sense of whether too many resources are being used is to look at the load average, circled in red in this image. These 3 numbers represent the CPU load over the past minute, 5 minutes, and 15 minutes (from left to right). The higher the load average and the longer it has been high, the more concerned you should be. A spike in the load average for the past minute may be ok, but a sustained high load for the past 15 minutes means some processes need to be killed before the server crashes. How high is too high? A common rule of thumb is 0.70 x total number of CPUs. Since we have 72 CPUs on comp5, if you see the <b>load above or approaching 50.0 you should wait for other jobs to finish</b> before starting any new ones.

There is also a lot more information htop gives you that you can take into account. The top portion of the screen shows a real-time representation of how much load is on each of the 72 CPUs. In this image you can see that 2.0% of the total capacity of CPU number 38 is being used and none of the others are in use. Directly below the CPU grid is a bar showing the memory usage. 2.92 of 252 GB of memory is being used in this image. The bottom half of the htop display shows a list of processes currently running, the user they belong to, and information about the resources they are using. 


If you want to check on your jobs only, you can use `htop -u` followed by your username (ex: `htop -u freeman.k`) to show only jobs started by your username. This can be useful to check how long your jobs have been running, to make sure they still are running and haven't been terminated, or to see how much of the server's capacity you are using.

If you would like to run a resource-intensive job without slowing down other jobs on the server, you can use the command `nice` when you start the job. `nice -n 19 <your_program>` will start your program with a "niceness" value of 19, meaning it will defer to all other processes when competing for CPU resources. The default niceness value is 0, 19 gives the lowest priority, and -20 gives the highest priority. Only the root user can run processes with negative niceness values.


 
