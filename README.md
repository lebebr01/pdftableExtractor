
# pdftableExtractor

<!-- badges: start -->
<!-- badges: end -->

The `pdftableExtractor` package provides functions for extracting tables
from PDF files. Using the
[pdftools](https://github.com/ropensci/pdftools) package developed by
[rOpenSci](https://ropensci.org/), tables can be easily extracted from
pdf files in R environment without the need for additional setup.

## Installation

The development version of `pdftableExtractor` can be downloaded using
devtools:

``` r
install.packages("devtools")
devtools::install_github('Mubarak-M/pdftableExtractor')
```

## Usage

`pdftableExtractor` provides functions to extract tables from single and
double column PDF files. It has additional functionality which allows
users to extract tables from specific page(s) in pdf files. The
`exctractor_tables` function extract tables from single column pdf file
and the `pages_tables` helper function does the same for specified
page(s) in the pdf file. The `exctractor_tables2` and
`pages_tables`functions extract tables from uploaded pdf file and
specified pages respectively, but with double column pdf files.

## Usage guide for single column document

### `extractor_tables`

This is a basic example which shows you how to extract tables from
single column pdf documents using `extractor_tables` function:

``` r
library(pdftableExtractor)
file <- system.file("extdata", "1coldata.pdf", package = "pdftableExtractor")
table <- extractor_tables(file, path = TRUE)
```

### `pages_tables`

This is a basic example which shows you how to extract tables from a
specific page(s) of a single column pdf documents using `pages_tables`
function:

``` r
library(pdftableExtractor)
file <- system.file("extdata", "1coldata.pdf", package = "pdftableExtractor")
tab <- pages_tables(file, path = TRUE)
```

#### Rectangular data

Extracting a rectangular data that is ready for analysis in R can reduce
data processing time. The `rec` argument is capable of extracting clean
data.frame from pdf files. For this argument to work, users must be sure
that the table meets the requirement of a rectangular data. That is, all
rows and all columns are of equal length.

``` r
library(pdftableExtractor)
file <- system.file("extdata", "1coldata.pdf", package = "pdftableExtractor")
tab <- pages_tables(file, path = TRUE, rec = TRUE)
```

## Usage guide for double column document

### `extractor_tables2`

This is a basic example which shows you how to extract tables from
double column pdf documents using `extractor_tables2` function:

``` r
library(pdftableExtractor)
file <- system.file("extdata", "1coldata.pdf", package = "pdftableExtractor")
tab <- extractor_tables2(file, path = TRUE)
```

### `pages_tables2`

This is a basic example which shows you how to extract tables from a
specific page(s) of a double column pdf documents using `pages_tables2`
function:

``` r
library(pdftableExtractor)
file <- system.file("extdata", "1coldata.pdf", package = "pdftableExtractor")
tab <- pages_tables2(file, path = TRUE)
```

#### Rectangular data

Extracting a rectangular data that is ready for analysis in R can reduce
data processing time. The `rec` argument is capable of extracting clean
data.frame from pdf files. For this argument to work, users must be sure
that the table meets the requirement of a rectangular data. That is, all
rows and all columns are of equal length.

``` r
library(pdftableExtractor)
file <- system.file("extdata", "1coldata.pdf", package = "pdftableExtractor")
tab <- pages_tables2(file, path = TRUE, rec = TRUE)
```

#> You’ll still need to render `README.Rmd` regularly, to keep
`README.md` up-to-date. #>`devtools::build_readme()` is handy for this.
You could also use GitHub Actions to #> re-render `README.Rmd` every
time you push. An example workflow can be found here: #>
<https://github.com/r-lib/actions/tree/v1/examples>.
