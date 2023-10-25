# WorldFlora Online (WFO) Fuzzy Join

## Overview

A repository for R code that uses a fuzzy join operation to find scientific plant name matches in abstracts
of scientific articles. The scientific names are those contained in the WorldFlora Online Plant List, a 
comprehensive and authoritative list of vascular plants.

WorldFlora Online offers an R package ["WorldFlora"](https://cran.r-project.org/web/packages/WorldFlora/WorldFlora.pdf) with several functions to match names contained in your own data with those of the plant list. 
One offering is a fuzzy join method (WFO.match.fuzzyjoin) that is a typically faster method of matching 
records than using exact matching and allows for different methods of calculating the fuzzy distance via 
stringdist. 

Here we implement two related techniques for finding name matches using WFO.match.fuzzyjoin: 
1) Fuzzy joins with small data sets and only a subset of scientific names
2) Fuzzy joins with large data sets and the complete taxonomic backbone consisting of ~1.5 observations
   using parallel processing and data frame chunking.

If you are unfamiliar with WorldFlora and its associated package, the best place to start is the [WFO CRAN.](https://cran.r-project.org/web/packages/WorldFlora/WorldFlora.pdf)
