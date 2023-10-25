# WorldFlora Online (WFO) Fuzzy Join

## Overview

A repository for R code that uses a fuzzy join operation to find scientific plant name matches in abstracts
of scientific articles.

Fuzzy join is an alternative and typically faster method of matching records than WFO.match that allows for
different methods of calculating the fuzzy distance via stringdist. 

Here we implement two related techniques for finding name matches: 
1) Fuzzy joins with small data sets and only a subset of scientific names
2) Fuzzy joins with large data sets and the complete taxonomic backbone consisting of ~1.5 observations
   using parallel processing.

If you are unfamiliar with WorldFlora and its associated package, the best place to start is the [WFO CRAN]
(https://cran.r-project.org/web/packages/WorldFlora/WorldFlora.pdf)
