# WorldFlora Online (WFO) Fuzzy Join Example
This project focuses on utilizing fuzzy string matching techniques to join biological scientific names using 
the World Flora Online (WFO) dataset. The code showcases several methods to perform fuzzy joins for matching 
and retrieving data across datasets. The aim is to facilitate data integration and comparison by handling 
slight discrepancies or variations in the recorded scientific names.

## Overview

R code that uses a fuzzy join operation to find scientific plant name matches in abstracts
of scientific articles. The scientific names are those contained in the WorldFlora Online Plant List, a 
comprehensive and authoritative list of vascular plants.

## Installation 
To use this code, ensure you have the required R packages installed. The essential packages include:

dplyr

tidytext

tm

fuzzyjoin

WorldFlora

data.table

stringr

parallel

doParallel

foreach

iterators

The packages can be installed in R using the install.packages("package_name") command.

## Usage
### Loading Data
Load the `scientific_name` and `example_data` CSV files.
The WFO.download() function retrieves the World Flora Online data, which needs to be run once.
Data frames are subset for troubleshooting purposes and all scientific names are converted to lowercase.

### Cleaning Abstracts
Text preprocessing is completed before completing the matching operations. Preprocessing aids the matching 
process by reducing the size of the data set, resulting in fewer operations, and removing text that is not
likely to contain words of interest. Specifically, we use the [tm](https://cran.r-project.org/web/packages/tm/index.html) package
to remove punctuation and numbers, and convert all text to lowercase. We then remove stop words (e.g., "is",
"are", "the"). Lastly, the abstracts are tokenized into n-grams (e.g., word chunks) of a length specified by
the user (e.g., 4-word chunks) using the unnest_tokens function from the tidytext package.

### Fuzzy Join Options
Three different approaches for fuzzy joins are demonstrated:

Option 1: Fuzzy join using [WFO.match.fuzzyjoin](https://cran.r-project.org/web/packages/WorldFlora/WorldFlora.pdf) without parallel processing

Tokenized n-grams are processed for fuzzy joins with the WFO dataset.


Option 2: Fuzzy join using [WFO.match.fuzzyjoin](https://cran.r-project.org/web/packages/WorldFlora/WorldFlora.pdf) with parallel processing

Utilizes parallel processing to perform fuzzy joins with the WFO dataset.


Option 2.1: Fuzzy join using [WFO.match.fuzzyjoin](https://cran.r-project.org/web/packages/WorldFlora/WorldFlora.pdf) with parallel processing and chunked data frames

Splits the data frame into chunks for parallel processing to enhance performance.


Option 3: Fuzzy join using [fuzzyjoin](https://cran.r-project.org/web/packages/fuzzyjoin/index.html)

Performs fuzzy join based on approximate string matching using the stringdist_left_join function.


Each section provides code snippets and detailed explanations on how the fuzzy joins are executed and the rationale behind each method.

## Contributing
Contributions to this project are welcome. If you'd like to contribute, please follow these steps:

Fork the repository.

Create a new branch for your feature.

Make your changes and submit a pull request.
