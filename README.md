# WFO Fuzzy Join
A repository for R code that uses a fuzzy join operation to find scientific name matches.
Fuzzy join is an alternative and typically faster method of matching records than WFO.match that allows for
different methods of calculating the fuzzy distance via stringdist. 

Here we implement a two techniques for finding matches. Specifically, we fuzzy join with and without 
parallel processing.
