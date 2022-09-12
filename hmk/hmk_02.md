hmk_02
================
Elaine Nunan

## Question 1: Loading tidyverse

``` r
library(tidyverse)
```

The tidyverse is loaded

## Question 2: Assigning values to “a” and “b”

``` r
a <- 90
b <- 4
a <= b
```

    [1] FALSE

a is not less than or equal to b

## Question 3: Using ls() function

``` r
ls()
```

    [1] "a" "b"

“a” and “b” are now listed in the global environment

## Question 4: Using rm(list = ls()) to clean up the environment

``` {rm(list=ls())}
```

If you don’t pass the “list” argument for the rm() function, it will
default to the “…” argument, which is less specific.
