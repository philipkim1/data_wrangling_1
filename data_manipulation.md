Data Manipulation
================

## Import some data

I want to import `FAS_litters.csv`.

``` r
litters_df = read.csv("data/FAS_litters.csv")
litters_df = janitor::clean_names(litters_df)

pups_df = read.csv("data/FAS_pups.csv")
```

## `select`

Let’s select some columns.

``` r
select(litters_df, group, litter_number)
select(litters_df, group, gd0_weight, gd18_weight)

select(litters_df, group, gd0_weight:gd_of_birth)
select(litters_df, group, starts_with("pups"))

select(litters_df, -litter_number)

select(litters_df, GROUP = group, litter_number)

rename(litters_df, GROUP = group)

select(litters_df, litter_number, everything())

relocate(litters_df, litter_number)
```

## Learning Assessment

``` r
pups_df = janitor::clean_names(pups_df)
select(pups_df, litter_number, sex, pd_ears)
```

## `filter`

Let’s get rid of rows…

``` r
filter(litters_df, gd_of_birth == 20)
filter(litters_df, group == "Con7")

filter(litters_df, gd0_weight < 23)

filter(litters_df, pups_survive != 4)

filter(litters_df, group %in% c("Con7", "Con8"))

drop_na(litters_df)
```

## `mutate`

Let’s add or change columns!

``` r
mutate(
  litters_df, 
    weight_change = gd18_weight - gd0_weight,
    group = str_to_lower(group))
```

## `arrange`

Let’s rearrange the data.

``` r
arrange(litters_df, gd0_weight)
arrange(litters_df, desc(gd0_weight))
arrange(litters_df, gd_of_birth, gd0_weight)
```
