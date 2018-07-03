# Using the `tidyr` Package

The `tidyr` package is a complementary package that helps in creating tidy data sets. Tidy data is when there is a need to have a data set where every row is an observation and every column is a variable, this way the data is organized in such a way where every cell is a value for a specific variable of a specific observation. Having the data in this format helps in building an understanding of the data and allows to analyze or visualize it quickly and efficiently. Some of the useful `tidyr` functions are:

- `gather()` function collapses multiple columns into key-pair values. 

- `spread()` is the complement of `gather()`, which is why its called spread()

- `separate()` turns a single character column into multiple columns, given either regular expression or a vector of character positions.

- `unite()` is a convenience function to paste together multiple columns into one.

More functions of the `tidyr` package are available through this [Data Wrangling Cheatsheet](http://www.rstudio.com/wp-content/uploads/2015/02/data-wrangling-cheatsheet.pdf)