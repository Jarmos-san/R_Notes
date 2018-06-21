R - Programing Overview
---
- "R is an open-source, high level programming language for data analysis"
	- being **OPEN-SOURCE** means everyone can contribute to R in the form of libraries(**_packages_**)
		1. First R-version was realeased in 2000
		2. First started out of the S-language on 1988
		3. Huge add-on libraries, collection of function for a given topic
		4. Multiple solutions for a given topic
		
	- being a high-level programming language means `R` already has objective classes defined as `functions`
		1. Functions are pre-defined eliminating the needfor the user to code from scratch.
		2. Pre-packaged functions can executed with supplied data and specific arguments
		
	- **DATA ANALYSIS** is for for making statistiical inferences, data manipulation and visualisation among many other features.
		1. Data Entry
		2. Data pre-processing
		3. Ststistical analysis(e.g. modelling, machine learning, prediction)
		4. Data simulations
		5. Data visualization
		6. Web scraping
		7. Data visualization for website integration(using Shiny)
		
Using Some Basic Functions
---
- Used mainly to explain a certain question or address a problem on StackOverflow and elsewhere.
	
    `runif` = Random Number Generator of a uniform distribution

	Example:-
```R
	> runif(9, 3, 3)
	3 3 3 3 3 3 3 3 3
	> runif(9, 3, 22)
	20.949677 16.180729 11.319621 17.589032 15.296086  8.977608 20.669086  5.782250  7.529091
	> runif(10, 0, 22)
	7.717004  3.475022  8.140339  7.414284 13.775444  7.651788  4.624573  1.369649 21.285684  7.126922
```
	`rnorm` = Random Number Generator of a normal distribution

	Takes in three arguments in the format `(n, min, max)` where `n` is the number of observations, `min` & `max` for the minimum and maximum observation.

**_IMPORTANT:_**
		1. The order of the argument matters.
        2. Some of the arguments are mandatory, while some of them aren't.

- `set.seed(65)` is used to make the random sample reproducible, the argument of the function `seed()` which is always a `numeric` implies `R`for using it's `nth` random number variation.

- `help()` or ?_func_ can be useful to get info about;
	- Available arguments
	- Order of arguments
	- Default settings of arguments

Common Mistakes to Take Care Of
----
- Packages must be downloaded either through RStudio's package manager or using `install.package()` function. _**REQUIRED ONLY ONCE**_
- Package should be activated once again either through RStudio or using `library()` function. _**REQUIRED FOR EACH SESSION**_
-  The R programming language is _**CASE SENSITIVE**_
-  The _**CONCATENATION FUNCTION**_ `c()` allows the whole vector rather than the variable to be input into a function.
	Example:-
    `plot.ts(c(3,4,5,6,7,8))`is the correct form as the function `plot.ts()` accepts 	only a vector as it's argument.
    `plot.ts(3,4,5,6,7,8)`would give an error message as this `Error in match.arg(plot.type) : 'arg' must be NULL or a character vector`
