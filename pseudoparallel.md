## Pseudo-replicate on the cluster

Defiance has 72 (check) cores per comp node. Generally we like to leave a few available, so can 
parallelize code across up to 68 cores at once.

For genomics, we're often doing tests for many loci. Depending on the test, it may
be faster to run each locus in serial on a core, and spread out different parts of the data
across several cores (as opposed to running each locus in serial across all cores 
in parallel).

To accomplish this, you will need a bash script and an R script. Examples are below.



### Bash script runScripts.sh

Save this script as `runRscripts.sh`

```
#!/bin/bash
set -e
set -u
set -o pipefail


## Use these two lines of code if you have a conda environmnent you'd like to activate
## and list what's in that environment
# source activate msprime-env
# conda list

mypath="/XXX" # set your path

cd $mypath

nrows=280000 # number of loci or rows to be tested. Improve this code by
			# actually calculating it from the relevant dataframe with `wc`
nlocipercore=$((nrows/68))
echo nlocipercore $nlocipercore
start=$(seq 1 $nlocipercore $nrows)
echo $start

for i in $start
do
	echo -e "\n\n"
	end=$((i+nlocipercore-1))
	
	if [ $end -gt $nrows ]
	then
		end=$nrows
	fi
	
	## Use this code if you need to name an outfile here
	## You may also name it inside your R script
	#outfile=${i}"_Invers_out.txt"
	#outpath=${mypath}"/results/"
	#outpathfile=${outpath}${outfile}
	
	### Call R script
    echo "Running R scripts for lines" echo 'start row' $i 'end row' $end
    
    Rscript --vanilla ../src/MyScript.R ${i} $end > ${i}"_R.out" 2> ${i}"_R.error" & echo $!
    
    # the above line, using the $! at the end, will run the script in the background on a single core
    # in the next iteration, it will run the script in the background on another core for a different set of rows
	# do not wait until the last background process is finished
	
done
```

### Corresponding MyScript.R

MyScript.R should be located in the `src/MyScript.R` working directory. If it is located in a different place,
than that needs to be specified in the bash script above.

```
# install libraries

args = commandArgs(trailingOnly=TRUE)

# test if there is at least one argument: if not, return an error
if (length(args)==0) {
  stop("At least one argument must be supplied (input file).n", call.=FALSE)
} 

start_row = args[1]
end_row = args[2]

print(c("start_row", "end_row"))
```

Once you have these two scripts set up and working on a subset of data, 
you can just run the bash script like this

````
chmod +x runRscripts.sh
./runRscripts.sh
```` 
