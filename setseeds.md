# Setting seeds for reproducibility

Any time you call a random varible or random sample (e.g. `rnorm` or `sample` in R), your code will not be reproductible unless you set a seed. sets the starting number used to generate a sequence of random numbers – it ensures that you get the same result if you start with that same seed each time you run the same process. 

The function `set.seed` can make your code reproducible, but you have to call it on the line before you ask R to do anything random.

Try:
```
set.seed(98234)
rnorm(100)
set.seed(98234)
rnorm(100)
```

And compare it to:
```
set.seed(98234)
rnorm(100)
rnorm(100)
```


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
sim_seeds <- round(runif(100)*10000000) 
  # may need more than 100 if there are more than 
  # 100 places in your sim where you set seeds
set.seed(sim_seeds[1])
a<-rnorm(100)
set.seed(sim_seeds[2])
b<-rnorm(100)
set.seed(sim_seeds[3])
c<-rnorm(100)
```
