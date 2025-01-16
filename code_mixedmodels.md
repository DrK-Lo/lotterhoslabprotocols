# Linear Mixed Effect Models

Here are some of Lotterhos' notes on learning how to mix model

We have a private [google drive with many of the resources](https://drive.google.com/drive/folders/1L70xzfNel7eTYSbX0ZnmmvmBOL0iC4bO?usp=sharing)

### Learn about `lme`

[Mixed Effects Models and Extensions in Ecology with R - Zuur](https://drive.google.com/file/d/1wmcZeZPiNoUtrrImV72fRI73MbVaD2gZ/view?usp=sharing)
  * If you have taken intro Biostats, review lectures on general linear models, simple linear and multiple regression, 
ANCOVA, and their assumptions, and likelihood before starting in with this book. Then review and learn new ways to test for assumptions in Chapter 2. 
You should also review matrix algebra.
	* This is an older book published in 2008, but much of which is still relevant.
	* Testing assumptions - Chapter 2
	* Learn about dealing with heterogeneity of variance in Chapter 4
	*  Mixed effects models and additive mixed effects models in Chapters 5,6,and7.
		* This book uses the `nlme` packages and the `lme` function, which has different syntax than lme4. However, the introduction to mixed modeling in Chapter 5 is an excellent place to start learning. Note that `lme` gives P-values for model effects, but we recommend using `lme4` with `lmertest` to generate these, or the package `brms` to take a Bayesian approach. 
		* Chapter 5 exlplains the difference between the random intercept model, the random intercept and slope model, and the random affection model.
		* Section 5.7 talks about model selection and should be read, but `lmertest` offers better options for this
		* Chapter 6 - dealing with autocorrelation in regularly spaced time series intervals.
	* Generalized GLM and GAMs (Chap 8-11)
		* Chap 8 is a good introduction to different distributions that you can assume your data follow, and distributions to use if your response variable does not include 0 (zero-truncated)
		* Chapter 9 has a good section on overdispersion
		* Chap 10 dedicated to proportional and presence/absence data
		* Chap 11 zero-truncated and inflated models
	* Chapter 12-13 GEEs (generalized estimating equations) for repeated measures and longitudinal data
		* In Chapters 12 and 13, we concentrated on mod- els that allow for correlation and random effects in Poisson and binomial GLMs and GAMs. These models are called generalised estimation equations (GEE), gener- alised linear mixed modelling (GLMM), and generalised additive mixed modelling (GAMM). 


### Learn `lme4` 

* [lme4 paper](https://cran.r-project.org/web/packages/lme4/vignettes/lmer.pdf)
	* good explanations of the form of the models and syntax
	* this paper has several sections on the mathematical details of the implementation, which can be skimmed, but be sure to pay attention again starting at 5.2
	* for the sections "... and model comparison" and "Computing P-values" here on page 34+, be sure to read `lmertest`for a better alternative
	
* [Mixed model theory](https://cran.r-project.org/web/packages/lme4/vignettes/Theory.pdf)
	* This can be skimmed

* [PLS vs GLS for linear mixed models](https://cran.r-project.org/web/packages/lme4/vignettes/PLSvGLS.pdf)
	* This can be skimmed

[Performance tips](https://cran.r-project.org/web/packages/lme4/vignettes/lmerperf.html)
	* This can be skimmed

[tutorial with nested random effects](http://www.bodowinter.com/tutorial/bw_LME_tutorial.pdf)


### Learn about approximating degrees of freedom, getting P-values, and model selection from lme4 with `lmertest`

If `lme4` and REML offers good convergence for your model, then you may want to consider testing the significance of fixed 
and random effects with the `lmertest` package.

[lmertest paper](https://www.jstatsoft.org/article/view/v082i13)

[vignette](http://www2.compute.dtu.dk/courses/02930/SummerschoolMaterialWeb/Readingmaterial/MixedModels-TuesdayandFriday/Packageandtutorialmaterial/lmerTestTutorial.pdf)


### Good online tutorials

* [LM Tutorial 1](http://www.bodowinter.com/tutorial/bw_LME_tutorial1.pdf) 
This is a good intro to basic linear models output and assumptions.

* [LME Tutorial](http://www.bodowinter.com/tutorial/bw_LME_tutorial.pdf) Good intro to mixed effect models. 
Uses likelihood ratio tests to compare models. Has a good section on random slopes vs. random intercepts. 
Has some citations "Moreover, researchers in ecology (Schielzeth & Forstmeier, 2009),
psycholinguistics (Barr, Levy, Scheepers, & Tilly, 2013) and other fields have
shown via simulations that mixed models without random slopes are anticonservative or, in other words, 
they have a relatively high Type I error rate (they
tend to find a lot of significant results which are actually due to chance)."

### Learn about Bayesian Regression Models `brms`

The `brms` package offers the most versatility for modeling data, and can accommodate a whole family of different distributions. It even allows you to define your own functions and estimate parameters on those, and has a framework for hypothesis comparison of different effects with Bayes Factors. We've found this package is able to more accurately estimate parameters on methylation data than other packages.

For example in Alan's 2017 oyster exposure experiment: methylation data is binomially distributed (e.g., read counts for methylated or unmethylated) and in our case, we wanted to make sure to account for the random effect of tank in the experiment (see results). For some  loci, we found with preliminary analyses that some approaches to generalized linear modeling failed to converge (when parameters were estimated via restricted maximum likelihood as implemented in lme4, or when the posterior distributions of the parameters were estimated via MCMC with Gibbs sampling as implemented in MCMCglmm). We traced this issue of convergence to loci in which all individuals within a treatment combination had 100\% or 0\% methylation, and with diverse levels of methylation in other treatments, making them biologically interesting and desirable to model correctly. As pointed out by Burkner, the approaches used by MCMCglmm can be slow to converge in high-dimensional models with correlated parameters and may depend on conjugate priors. We therefore took a robust approach to analyzing methylation data with Bayesian Regression Models (BRMs) in which the sampling on the posterior distributions on the parameters was accomplished with the No-U-Turn-Sampler (NUTS). This algorithm converges much more quickly for high-dimensional models regardless of whether the priors are conjugate or not.

## How to write about mixed models

* We had a [lab professional development discussion on this](https://docs.google.com/document/d/1jQZkbZbZuWnElYmLUntg5qgh1NG2-yAbsT3zzvmbkZ0/edit#heading=h.btb80w3ha1pf)

* **What to write in a paper?** Check out Zuur and [LME Tutorial](http://www.bodowinter.com/tutorial/bw_LME_tutorial.pdf) for examples.
 
## Frequently asked questions

* **How do you know you want to model an explanatory variable as fixed or random?** If the levels of your explanatory variable represent a subset of an entire population of levels of that variable, then this should be modeled as random. 
	* For more information see [lme4 paper](https://cran.r-project.org/web/packages/lme4/vignettes/lmer.pdf) page 6.

* **Do your random effects or subjects appear to vary in the slopes AND intercepts relationships?** Use data visualization to explore the linear relationship across levels of the random explanatory variable(s). An example is shown in [lme4 paper](https://cran.r-project.org/web/packages/lme4/vignettes/lmer.pdf) page 4. If so, this suggests a model with random slopes and intercepts.

* **What are the dimensions of linear models (e.g. p, q, n, etc.)?** See [lme4 paper](https://cran.r-project.org/web/packages/lme4/vignettes/lmer.pdf) page 8

* **What does $X^TX$ do?** This is a common approach seen in statistics. (WILL ADD MORE)

* **What is REML?** See section 5.6 of Zuur for a great explanation.


