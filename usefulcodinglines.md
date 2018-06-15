---
layout: page
title: Useful Coding Lines
subtitle: A resources for useful lines when coding
---

### Want to change to a directory without having to type the entire directory path? Use the click and drag method:

<img src="../img/quickdirectory.gif" style="width:100%;" alt="Quick Directory Access" />

### Want to remove files created before a certain date? Here's an example:

`find /home/br.ford/br.ford_remote/slim/results/ -ctime +14 -print -exec rm {} \;`

This finds all files in the `.../results/` directory that are older than 14 days and removes them

You can also be more specific. For example, if you want to remove only txt files older than two days:

`find /home/br.ford/br.ford_remote/slim/results/*.txt -ctime +2 -print -exec mv {} finished_results \;`

### Want to list just subdirectories in the current directory?

`ls -d */`

### Want to replace a character in a txt file? Use sed:

`sed -i '' 's/["]//g' test.txt`

The -i argument says to use in-place editing (edit and return file without making another copy), the empty quotes identifies extension of backup file (none, unless you want a backup file), the statement in the quotes specifies: to substitute (s/) quotations ([“]) with nothing (//) globally (g’) in test.txt

### Want to change permissions to a directory and all subdirectories, but are not sure which `chmod` arguments to use to do so recursively? Use mac GUI:

<img src="../img/changepermissions.gif" style="width:100%;" alt="Change Permissions" />



