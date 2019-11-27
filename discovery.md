# Connecting to the Discovery cluster

* Discovery account. Apply by opening a Service-Now ticket with an access request (https://rc.northeastern.edu/support/contact/).

* Login by typing `ssh lotterhos@login.discovery.neu.edu`

* [NU's Getting started on Discovery](https://cpb-us-w2.wpmucdn.com/express.northeastern.edu/dist/1/43/files/2019/08/GettingStartedGuide-1.pdf)


## Software on Discovery for Lotterhos Lab

* We have a software module on Discovery for the lab's research
```
module show lotterhos/2019-11-15
module load lotterhos/2019-11-15
```

* In the future we hope to work on Docker containers for loading R packages and developing containers for specific projects.
A container allows you to create the same environment that you were using when you analyzed the data.

## Open OnDemand

* Check on the Open On Demand - R studio and Jupyter notebooks! Open OnDemand (ood.discovery.neu.edu)
  * You also open a JupyterHub interface (jupyterhub.discovery.neu.edu)
  
* To view your home directory on Discovery with OOD, you have to log in to Discovery at the command line / Terminal first

* Previous workshop materials are available at `/shared/rc/training`. For example, the latest one research computing did focused on introduction to Slurm and Discovery as well as how to set up python environments. 
  * You can copy it to your home directory by typing the following command (at the command line): `cp -r /shared/rc/training/training_111219 ~`
  * You can then view it via Open OnDemand
  
* Although OOD allows file transfer, this is not recommended because there are no automatic checks for file corruption. Use Globus instead.
  
## Lotterhos Lab Storage on Discovery

* We have **active** storage (10 TB) that should be used for 'active' projects, and **archival** storage for storing 
raw files and outputs from projects. Please be smart about how you use archival storage and work with Dr. Lotterhos to 
make sure only relevant files are being archived.

* In addition each user has a home directory and a scratch directory.

* **Active Lotterho Lab storage** (10 TB for lab).  
  * Path: `/research/lotterhos/`

* **Archival Lotterho Lab storage** (25 TB for lab). Northeastern NESE collection. 
  * Path: `/lotterhosarchive/`

* **Your home directory on Discovery**.  NEED TO CHECK
  * Path: `/~/`
  
* **Your scratch directory on Discovery**. Use this for intermediate outputs that are not backed up. NEED TO CHECK
  * Path: `/scratch/username`

## Globus File Transfer

* Globus is a system for transferring files. The pros:
  * It's fast
  * If your connection gets interrupted, it automatically picks up where it left off
  * It automatically checks that your files were not corrupted during the transfer
  * Globus is already integrated with Discovery and our lab files.
  * It makes transferring files among your laptop, your collaborator(s), and Discovery easy.
  
* **Getting started with Globus**
  * 


