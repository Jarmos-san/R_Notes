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
		
Basic Functions
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

- `set.seed(65)` is used to make the random sample reproducible, the argument of the function `seed()` which is always a `numeric` implies `R`for using it's `nth` random number variation.

- `help()` or ?_func_ can be useful to get info about;
	- Available arguments
	- Order of arguments
	- Default settings of arguments

- `seq()` - generates regular sequences of a vector characters.
	- Arguments: `from`, `length`, `by`

- paste() - string concatenation
	- Arguments: `sep`

- `rep()` - replicates elements of vectors & lists
	- Arguments: `x`, `times`, `each`

- Index positions;
	- `which()` - returns the index position(s) of a given value from object "x"
	- `[]` - returns the value of the specified index from object "x"

- `head()` - prints first six rows

- `tail()` - prints last six rows

- `summary()` - prints basic statistics on each of the variable

- `plot()` - prints a xy-plot

- `hist()` - prints a histogram

**_IMPORTANT:_**
1. The order of the argument matters.
2. Some of the arguments are mandatory, while some of them aren't.

- **_Dataframe manipulation_**
	- `$` - gives access to a specific column within a dataset
	```R
	data <- dataframe$column
	```
 	- `attach()` - attaches datasets to the environment
 	```R
 	attach(dataset)
 	```
 	-  `detach()` - detaches a datasets from the environment
 	```R
    detach(dataset)
    ```
	 -  `[]` - extracts data from a dataset a vale level
	```R
    dataset[2]
    ```
    
Objects
-----
- _**OBJECT**_ can be considered as a collection of data that can be used as one;
	- whole dataset
	- result of a calculation
 	- a part of a dataset with specific traits

- Different ==**OBJECT**== properties/classes can determine what can be done with the data. 
	- Examples of an **Object Class** would be a `data.frame` or a `vector`

- Objects can be assigned to a `variable` using either the `<-` or `->`. The `=` operator and the `assign()` function is also interchangeably.

Using Brackets
-----

- R uses three types of brackets *Round Brackets* `()`, *Square Brackets* `[]`, *Curly Brackets*`{}`. 
 - *Round Brackets*`()`
   - Used in the standard form to signify data used together
   - Used to bind values together
   - Mainly used by pre-defined functions  
 - *Square Brackets*`[]`
   - Used during filtering data
   - Used for indication index positions within an object
 - *Curly Brackets*`{}`
   - Used user-defined functions 

Functions and Loops
---
- In the R programming language, _**functions**_ are`OBJECTS` which can be programmed to make calculations.

- Structure of a R function looks like this;
	```
	name <- function (argument) {statements} 
	the arguments specify the components to be used in the function 
	```

   Example of a function can be written as follows;
   ```R
   myFunc <- function(x) {x + X}
   myFunc(10)
   20
   ```

- _**Loops**_ on the other hand allow a certain operation to be performed a ### of times.

	Example;
    ```R
    for (i in 1:7) {print (i)}
    1
    2
    3
    4
    5
    6
    7
    ```
Arithmetic Operators
----

- R can be used as a calculator for performing basic arithmetic operations like;

	```R
	4 + 4 + 5
	13
	```
    
- While the spacing between characters doesn't matter R follows flow of operation execution like;

	```R
	(5-3)^3 #operations within the parenthesis will be excuted first
	8
	```
    
- R accepts ` +, -, /, * and ^` for addition, subtraction, division, multiplication and exponent respectively.


Common Mistakes to Take Care Of
----
- Packages must be downloaded either through RStudio's package manager or using `install.package()` function. _**REQUIRED ONLY ONCE**_
- Package should be activated once again either through RStudio or using `library()` function. _**REQUIRED FOR EACH SESSION**_
-  The R programming language is _**CASE SENSITIVE**_
-  The _**CONCATENATION FUNCTION**_ `c()` allows the whole vector rather than the variable to be input into a function.
	Example:-
    `plot.ts(c(3,4,5,6,7,8))`is the correct form as the function `plot.ts()` accepts 	only a vector as it's argument.
    `plot.ts(3,4,5,6,7,8)`would give an error message as this `Error in match.arg(plot.type) : 'arg' must be NULL or a character vector`
