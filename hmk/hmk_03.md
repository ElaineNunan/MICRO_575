Homework 3
================
Elaine Nunan

## Reading the CSV file

``` r
library(tidyverse)

read_csv(file = "fake.csv")
```

    # A tibble: 10 × 2
          ID lengths
       <dbl>   <dbl>
     1     1       3
     2     2       6
     3     3       2
     4     4       8
     5     5       7
     6     6       1
     7     7       9
     8     8      10
     9     9       5
    10    10       4

The tidyverse message has been disabled, and the file “fake” is now in
the environment.

# Investigating the properties of data frames

Using the glimpse and sequence function to look at the data frame from
the fake.csv file.

``` r
fake <- read_csv(file = "fake.csv")
```

    Rows: 10 Columns: 2
    ── Column specification ────────────────────────────────────────────────────────
    Delimiter: ","
    dbl (2): ID, lengths

    ℹ Use `spec()` to retrieve the full column specification for this data.
    ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
glimpse(fake)
```

    Rows: 10
    Columns: 2
    $ ID      <dbl> 1, 2, 3, 4, 5, 6, 7, 8, 9, 10
    $ lengths <dbl> 3, 6, 2, 8, 7, 1, 9, 10, 5, 4

``` r
class(fake)
```

    [1] "spec_tbl_df" "tbl_df"      "tbl"         "data.frame" 

``` r
class(fake$lengths)
```

    [1] "numeric"

Of the two functions I used (glimpse and class), glimpse seems to be the
more useful function for looking at the entire data frame than class, as
glimpse shows all the values in the data frame. The class function tells
you that “fake” is a data frame, which isn’t very helpful or you need to
specify which column in the data frame what you want information about.

# Manipulating data frames

``` r
fake$something <- 2 * fake$lengths

glimpse(fake)
```

    Rows: 10
    Columns: 3
    $ ID        <dbl> 1, 2, 3, 4, 5, 6, 7, 8, 9, 10
    $ lengths   <dbl> 3, 6, 2, 8, 7, 1, 9, 10, 5, 4
    $ something <dbl> 6, 12, 4, 16, 14, 2, 18, 20, 10, 8

I created a column called “something” in the “fake” data frame by
multiplying the “lengths” column by 2.

# Working on columns

Performing the mean function on the lengths column of the fake.csv file

``` r
mean(fake$lengths)
```

    [1] 5.5

The mean of the lengths column is 5.5

# Accessing elements of data frames

-   [Challenge 3 from SC Data Structures
    lesson](https://swcarpentry.github.io/r-novice-gapminder/04-data-structures-part1/index.html#challenge-3):
    Show what each of the following returns, and explain what each line
    of code is doing:

    ``` r
    cats <- data.frame( coat = c("calico", "black", "tabby", "calico"),
                    weight = c(2.1, 5.0, 3.2, 4.4),
                    likes.string = c(TRUE, FALSE, TRUE, TRUE))
    cats[1]
    ```

            coat
        1 calico
        2  black
        3  tabby
        4 calico

    The above function is returning the 1st list that is in the data
    frame which is the colum of coat type.

    ``` r
    cats[[1]]
    ```

        [1] "calico" "black"  "tabby"  "calico"

    The above function is returning the data in the 1st column as a
    vector

    ``` r
    cats$coat
    ```

        [1] "calico" "black"  "tabby"  "calico"

    The above function also returns the data in the 1st column. With
    this function you need to know the name of the column.

    ``` r
    cats[1,1]
    ```

        [1] "calico"

    The above function returns the 1st value of the 1st column.

    ``` r
    cats[ ,1]
    ```

        [1] "calico" "black"  "tabby"  "calico"

    The above function all of the values of the 1st column.

    ``` r
    cats[1, ]
    ```

            coat weight likes.string
        1 calico    2.1         TRUE

The above function returned the 1st values of all the columns
