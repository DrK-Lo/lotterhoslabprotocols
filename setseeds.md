# Setting seeds for reproducibility

If you are running a large number of replicate simulations, it's important to make them reproducible. 
A good practice is to think about what parameters you are going to model and make a giant table.
Here is an example for a simulation with three replicates of two different sets of parameters:

|Seed | Rep | Param 1 | Param 2 |
|-----|------|---------|-------------|
|98234 | 1 | 0.5 | 1.2|
|98235 | 2 | 0.5 | 1.2|
|98236 | 3 | 0.5 | 1.2|
|98237 | 1 | 0.9 | 1.5|
|98238 | 2 | 0.9 | 1.5|
|98239 | 3 | 0.9 | 1.5|

As you loop through this table, you can use the Seed as the `mySeed` for your simulations. However, 
there are bad and good ways to take the seed from this table and incorporate it into your simulations.

### Bad Practice:

```
set.seed(mySeed)
a<-rnorm(100)
set.seed(mySeed)
b<-rnorm(100)
set.seed(mySeed)
c<-rnorm(100)
```

Try this in R. _What values do you get for a, b, and c?_

### Good practice:
```
set.seed(mySeed)
sim_seeds <- round(runif(100)*10000000) #may need more than 100 if there are more than 100 places in your sim where you set seeds
set.seed(sim_seeds[1])
a<-rnorm(100)
set.seed(sim_seeds[2])
b<-rnorm(100)
set.seed(sim_seeds[3])
c<-rnorm(100)
```
