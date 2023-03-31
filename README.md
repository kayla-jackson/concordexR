
<!-- README.md is generated from README.Rmd. Please edit that file -->

# concordexR

<!-- badges: start -->

[![Codecov test
coverage](https://codecov.io/gh/kayla-jackson/concordexR/branch/master/graph/badge.svg)](https://app.codecov.io/gh/kayla-jackson/concordexR?branch=master)
<!-- badges: end -->

The goal of concordexR is to replace UMAP as a clustering diagnostic.

## Installation

This repository is not maintained. It has been moved to 
[https://github.com/pachterlab/concordexR](https://github.com/pachterlab/concordexR).

You can install the development version of concordexR from 
[GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("kayla-jackson/concordexR")
```

## Example

This is a basic example using concordex:

``` r
library(concordexR)
library(BiocNeighbors)
```

``` r
g <- findKNN(iris[, seq_len(4)], k = 10)
#> Warning in (function (to_check, X, clust_centers, clust_info, dtype, nn, :
#> detected tied distances to neighbors, see ?'BiocNeighbors-ties'
res <- calculateConcordex(g$index, labels = iris$Species, k = 10, return.map = TRUE)
```

``` r
plotConcordexSim(res)
```

<img src="man/figures/README-unnamed-chunk-3-1.png" width="70%" />

``` r
heatConcordex(res)
```

<img src="man/figures/README-unnamed-chunk-4-1.png" width="70%" />
