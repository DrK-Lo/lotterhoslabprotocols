# Tranferring files md5

We recommend using GLOBUS (add link) to tranfer files.
However, if you use another file tranfer mechanism, use md5sums to make sure your files transferred successfully.

## How to ensure the files you are transferring are transferred successfully

### Step 1: Make a list of md5sums of your files

If md5 sums provided by the sequencing facility in a file: `md5_sum.txt` 
(on mac is md5, on unix md5sum)

If not:
`md5sum (list files) > md5sum.txt`

### Step 2: Transfer files to new location (including the md5sum.txt)

change directory to that location

Then, create an md5sum of the transferred files:

`md5sum (list files in new location) > md5sum_new.txt`

### Step 3: Compare md5sum from before the transfer to md5sum after the transfer

Compare sorted files FILE1 and FILE2 line by line:

`comm -3 md5sum.txt md5sum_new.txt`

With  no  options,  produce  three-column  output.  Column one contains 
lines unique to FILE1, column two contains lines unique to  FILE2,  and  column three contains lines common to both files.
  -1     suppress lines unique to FILE1
  -2     suppress lines unique to FILE2
  -3     suppress lines that appear in both files

If the last command produces no output, the two files are identical.

```
