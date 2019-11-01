---
layout: page
title: Basic Unix Commands 
subtitle: A resources for useful lines when coding
---

## Table of Contents
1) [`cd` - Changing Directories](#cd)  
2) [`find` - Finding files](#find)  
3) [`ls` - Listing files](#ls)  
4) [`sed` - Replacing texts in a file name](#sed)  
5) [`chmod`- Changing file or folder permissions](#chmod)  
6) [`wc` - Count words,lines, or columns of a file](#wc)  
  

## Change directory - `cd` <a name="cd"></a>

**Description** - Command allows you to change your directory.

Simple directory change:
```
cd /path/to/desired/directory
```

Additional ways to change your current directory:
```
# One level up in the path
cd ..
# Can be done more than one to move mutiple levels
cd ../../..
# Provided with no path information it will change directory to the base directory
cd
```

**Changing directory with click and drag method**

<img src="../img/quickdirectory.gif" style="width:100%;" alt="Quick Directory Access" />


## Find target files - `find` <a name="find"></a>

**Description** - The `find` command in UNIX is a command line utility for walking a file hierarchy. It can be used to find files and directories and perform subsequent operations on them. It supports searching by file, folder, name, creation date, modification date, owner and permissions. By using the `- exec` other UNIX commands can be executed on files or folders found. (from https://shapeshed.com/unix-find/)

* Additional Information
     * [Extended Tutorial](https://shapeshed.com/unix-find/)  
     * [`find` manual](https://linux.die.net/man/1/find)  

**Simple Find**
```
find ./directory/path/ -name FileExample.txt
```
This will with find file `./directory/path/FileExample.txt`

**Remove files created before a certain date with find**
```
find /home/br.ford/br.ford_remote/slim/results/ -ctime +14 -print -exec rm {} \;
```

This finds all files in the `.../results/` directory that are older than 14 days and removes them

You can also be more specific. For example, if you want to remove only txt files older than two days:
```
find /home/br.ford/br.ford_remote/slim/results/*.txt -ctime +2 -print -exec mv {} finished_results \;
```


## Listing files and directories - `ls` <a name="ls"></a>

**List just subdirectories in the current directory**
```
ls -d */
```

## Replacing characters in a txt file -`sed` <a name="sed"></a>
```
sed -i '' 's/["]//g' test.txt
```

The -i argument says to use in-place editing (edit and return file without making another copy), the empty quotes identifies extension of backup file (none, unless you want a backup file), the statement in the quotes specifies: to substitute (s/) quotations ([“]) with nothing (//) globally (g’) in test.txt

## Changing Permission - `chmod` <a name="chmod"></a>


**Want to change permissions to a directory and all subdirectories, but are not sure which `chmod` arguments to use to do so recursively?**

Use mac GUI:
<img src="../img/changepermissions.gif" style="width:100%;" alt="Change Permissions" />

## Counting words, lines, or columns - `wc` <a name="wc"></a>

Count the lines:
```
wc -l myfile.txt
```

Count the columns:
```
awk -F'\t' '{print NF; exit}' myfile.txt
```

-F'\t' tells awk that your columns are tab delimited, you can switch this for another character depending on your dataset. For example, if the data is comma separated just use -F',' instead. To print the column count for every line instead of just the first one, leave out 'exit'.

#### Still editting below this point (possibly moving to new file since this is not a basic unix command)

**Want to rename lots of files at once?**

Say you have a directory with the following images:

pic1.png

pic2.png

pic3.png

...

pic27.png

You decide that they should have a more descriptive name, so you want to change them to 'oyster_pic1.png', 'oyster_pic2.png', 'oyster_pic3.png'....


You don't have to move them individually, just use the bash command 'rename' with a regular expression!

```
$ rename 's/pic/oyster_pic/g' *
```


- 's' at the begining tells the command to **s**ubstitute a string with another string

- /pic/ is the string you want to replace

- /oyster_pic/ is the string to replace it with

- 'g' is the **g**lobal flag -- this means replace every instance of the 1st string with the 2nd. Ex, pic1pic.png would become oyster1oyster.png. This may or may not be desirable depending on what you want to do.

- \* after the regex just tells rename what to rename - in this case everything in the directory


The rename command uses perl regular expressions - you can do a lot with these, google perl regex if you want to learn more.

**On MacOS you may have to install rename before you can do this: `$ brew install rename`** 


