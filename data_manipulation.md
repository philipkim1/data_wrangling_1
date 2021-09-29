Data Manipulation
================

## Import some data

I want to import `FAS_litters.csv`.

``` r
litters_df = read.csv("data/FAS_litters.csv")
litters_df = janitor::clean_names(litters_df)

pups_df = read.csv("data/FAS_pups.csv")
```