01\_write-installed-packages.R
================
BRIANMERK
Thu Oct 04 14:32:35 2018

``` r
## deja vu from earlier!

library(tidyverse)
```

    ## Warning: package 'tidyverse' was built under R version 3.3.3

    ## -- Attaching packages ----------------------------------------------- tidyverse 1.2.1 --

    ## v ggplot2 2.2.1     v purrr   0.2.4
    ## v tibble  1.3.4     v dplyr   0.7.4
    ## v tidyr   0.7.2     v stringr 1.2.0
    ## v readr   1.1.1     v forcats 0.2.0

    ## Warning: package 'tibble' was built under R version 3.3.3

    ## Warning: package 'tidyr' was built under R version 3.3.3

    ## Warning: package 'readr' was built under R version 3.3.3

    ## Warning: package 'purrr' was built under R version 3.3.3

    ## Warning: package 'dplyr' was built under R version 3.3.3

    ## -- Conflicts -------------------------------------------------- tidyverse_conflicts() --
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
library(here)
```

    ## Warning: package 'here' was built under R version 3.3.3

    ## here() starts at H:/R/RStudioWorkshop/explore-libraries

``` r
## create a data frame of your installed packages
## hint: installed.packages() is the function you need
dat <- installed.packages() %>%
  as_tibble %>%
  select(Package,LibPath,Version,Priority,Built)

nrow(dat)
```

    ## [1] 143

``` r
## optional: select just some of the variables, such as
##   * Package
##   * LibPath
##   * Version
##   * Priority
##   * Built

## write this data frame to data/installed-packages.csv
## hint: readr::write_csv() or write.table()
## idea: try using here::here() to create the file path
dat %>%
  write_csv(here::here("data","installed-packages.csv"))

## YES overwrite the file that is there now (or delete it first)
## that came from me (Jenny)
## it an example of what yours should look like and where it should go
```
