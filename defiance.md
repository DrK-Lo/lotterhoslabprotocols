---
layout: page
title: Accessing and Using Defiance Cluster
subtitle: Notes on how to access and use the defiance cluster
---

To use the defiance cluster you need to contact Stefan (graduate student in Vollmer lab; S.Kaluziak@northeastern.edu) and request access
You'll need to send Stefan your public key. Public keys can be created following the steps [here:] (https://confluence.atlassian.com/bitbucketserver/creating-ssh-keys-776639788.html)
Ask Stefan to give you access to /shared_lab directory
If you require additional programs while using cluster, you'll need to ask Stefan to install it. E-mail him the software and version, and he should have it installed within 24 hours.

### Description of defiance
Defiance is set up with a main node (where you log in) and compute nodes
Not all files/folder map perfectly across the main node and compute nodes
Each user has their own remote repository that is private

### Accessing Cluster
**After Gaining Access from Stefan**
Log onto cluster by opening Terminal and typing: ssh username@defiance.neu.edu (e.g. br.ford@defiance.neu.edu)
You'll then log onto a computing node. The basic outline of computing nodes is below:

comp5 (Lotterhos)
comp6
comp7 (Bowen)
comp8

Log onto comp5 by typing: ssh comp5

**You can only access the /shared_lab directory by logging on to one of the computing nodes (comp5)**

T transfer files from my computer to defiance remote directory:
First, go to folder on computer with file in it. Then transfer file(s) into personal folder
my_laptop\$ scp ./my_file br.ford@defiance.neu.edu:/home/br.ford/br.ford_remote/my_folder

Or to download to personal computer from defiance, go to folder on your computer where you want the file, then:
my_laptop\$ scp br.ford@defiance.neu.edu:/home/br.ford/br.ford_remote/my_folder/my_file .

shared_lab can not be accessed with scp, so you'll need to move (mv) things to your remote repository before downloading to personal computer
