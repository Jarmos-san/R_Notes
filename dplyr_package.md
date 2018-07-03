# The `dplyr` Package

`dplyr` is a grammar of data manipulation, providing a consistent set of verbs that helps in solving the most common data manipulation challenges:

- By constraining the available options, it helps to think about the data manipulation challenges instead.

- It provides simple “verbs”, functions that correspond to the most common data manipulation tasks, to help in translating one's thoughts into code.

- It uses efficient backends, so less time is spent in waiting for the computer. 

Following are the commonly used `dplyr` functions:

- mutate() adds new variables that are functions of existing variables

- `select()` picks variables based on their names. Often while working with large datasets with many columns but only a few are actually of any interest. `select()` allows to rapidly zoom in on a useful subset using operations that usually only work on numeric variable positions:

- `filter()` picks cases based on their values. `filter()` allows to select a subset of rows in a data frame. Like all single verbs, the first argument is the tibble (or data frame). The second and subsequent arguments refer to variables within that data frame, selecting rows where the expression is `TRUE`.

- `summarise()` reduces multiple values down to a single summary. 

- `arrange()` changes the ordering of the rows working similarly to `filter()` except that instead of filtering or selecting rows, it reorders them. It takes a data frame, and a set of column names (or more complicated expressions) to order by. If you provide more than one column name, each additional column will be used to break ties in the values of preceding columns

- `mutate()`, besides selecting sets of existing columns, this function is often useful to add new columns that are functions of existing columns.

- `slice()` is used to select rows by position using.

- `rename()` can be used to rename columns.

- `distinct()` A common use of `select()` is to find the values of a set of variables. This is particularly useful in conjunction with the `distinct()` verb which only returns the unique values in a table.

- `sample_n()` and `sample_frac()` can be used to take a random sample of rows: use `sample_n()` for a fixed number and `sample_frac()` for a fixed fraction.

More information and extensive examples available on [A Grammar of Data Manipulation * `dplyr`](https://dplyr.tidyverse.org/) and [Introduction to dplyr](https://cran.r-project.org/web/packages/dplyr/vignettes/dplyr.html)

