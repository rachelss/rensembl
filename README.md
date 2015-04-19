---
output:
  md_document:
    variant: markdown_github
---

<!-- README.md is generated from README.Rmd. Please edit that file -->


```
## Error in knitr::opts_chunk$set(collapse = TRUE, comment = "#>", ): argument is missing, with no default
```
# rensembl
[![Travis-CI Build
Status](https://travis-ci.org/dwinter/rensembl.png?branch=master)](https://travis-ci.org/dwinter/rensembl)


The very early stage of an R package wrapping [the Ensembl REST
api](http://rest.ensembl.org/). 

This package is very much a work in progress, and the behaviour may well change
in the future. Even so, there is some stuff to play with already. You can
install the package via `devtools`

```r
devtools::install_github("dwinter/rensembl")
```


##Examples

Our development plan is to work on low-level functions that return simple R
objects (lists or character vectors), then build some higher-level functions
hat impliment common tasks or return richer R objects

Though we have only low level functions at present, some of them are quite helpful:

### Get information about a gene by its symbol


```r
brca2_info <- lookup_symbol("BRCA2")
```

```
## Error in eval(expr, envir, enclos): could not find function "lookup_symbol"
```

```r
brca2_info
```

```
## Error in eval(expr, envir, enclos): object 'brca2_info' not found
```
### Find variants within a gene


```r
snps <- overlap(gene_id=brca2_info$id, feature="variation")
```

```
## Error in eval(expr, envir, enclos): could not find function "overlap"
```

```r
snps[[1]]
```

```
## Error in eval(expr, envir, enclos): object 'snps' not found
```

We can extract some information for each case too:


```r
table(sapply(snps, "[[", "consequence_type"))
```

```
## Error in lapply(X = X, FUN = FUN, ...): object 'snps' not found
```



