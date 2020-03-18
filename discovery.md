# Connecting to the Discovery cluster

* Discovery account. Apply by opening a Service-Now ticket with an access request (https://rc.northeastern.edu/support/contact/).

* Login by typing `ssh lotterhos@login.discovery.neu.edu`

* [NU's Getting started on Discovery](https://cpb-us-w2.wpmucdn.com/express.northeastern.edu/dist/1/43/files/2019/08/GettingStartedGuide-1.pdf)

* [NU Discovery research computing docs](https://rc-docs.northeastern.edu/en/latest/)


## Software on Discovery for Lotterhos Lab

* We have a software module on Discovery for the lab's research
```
module show lotterhos/2019-11-15
module load lotterhos/2019-11-15
```

* In the future we hope to work on Docker containers for loading R packages and developing containers for specific projects.
A container allows you to create the same environment that you were using when you analyzed the data.

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

* **Active Lotterhos Lab storage** (? TB for lab).  
  * smb://nunet.neu.edu/rc-shares/lotterhos/
  * Within this storage space we have a shared folder for each project, that only the people on that project have access to.
  * Because accessing this server is done through a computer, it makes transferring files specific to the computer that the server is mapped to. Typically, you will ask Katie to share the Globus endpoint for this server that is set up through the lab iMac. As long as the server is mapped to the computer (typically lab iMac) and that connection is not interrupted, you should have no problems. 
   * From a laptop or over wifi, transfers of large files are very slow. This is why we map to the server through the iMac. The point of all the steps we outline below is so we can use Globus to transfer files from the smb drive to Discovery.
  * To connect to the smb server, follow these directions to map to the server on a computer [this document](link) (typically Katie only)
  * Setting up a Globus endpoint for the folder to share (typically Katie only)
   * _Intitial step if Globus personal endpoint for the computer is not set up_: Download and install the Globus Connect Personal App. In Globus web app, click on "Add a personal endpoint" and enter the key in the Desktop app.
   * _Intial setup if working from a home laptop_: Use GlobalProtect to establish a VPN connection (vpn.northeastern.edu) (if you are having trouble establishing the VPN connection on a Mac, check your Security and Permissions settings and give the app permissions). Then you should be able to map to the server. 
   * Step 1: In the Globus Desktop App, then go to Preferences-> Access and click the "+" sign. On a Mac, at the top center click on the bar, click on the name of the computer, and you should see the mapped server there as a volume `Volumes/lotterhos`. Click on it and add it to the list.
   * Step 2: In the Globus Web App, go to the endpoint for the computer. Then type `Volumes/lotterhos/` in the path. Save it as a bookmark.
   * Step 3: Before you can conduct file transfers from a personal endpoint, you need to have a "Globus Plus Account". Email James Macalino at NU research computing to get the account.
  
* **Archival Lotterhos Lab storage** (25 TB for lab). Northeastern NESE collection. 
  * Path: `/lotterhosarchive/`
  * Within this storage space we will have a shared folder for each project, that only the people on that project will have access to.

* **Your home directory on Discovery**.  
  * Path: `/~/`
  * Note that only you have access to these files.
  
* **Your scratch directory on Discovery**. Use this for intermediate outputs that are not backed up. 
  * Path: `/scratch/username`
   * Note that only you have access to these files.


