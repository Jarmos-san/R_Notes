# Matrices
- Matrices are 2D data structures storing elements of the same data types.

- Creating a matrix
	Example:
    ```R
    matrix(1:10)	#Creates a 2D matrix with 10 rows and 1 columns
    		[,1]
    [1,]		1
    [2,]		2
    [3,]		3
    [4,]		4
    [5,]		5
    [6,]		6
    [7,]		7
    [8,]		8
    [9,]		9
    [10,]	  10
    ```
   - Additional parameters of the `matrix()` function:
   ```R
   #byrow = FALSE lets the matrix fill by column first
   matrix(1:12, byrow = FALSE, nrow = 4)
     	[,1] [,2] [,3]
	[1,]    1    5    9
	[2,]    2    6   10
	[3,]    3    7   11
	[4,]    4    8   12
    
    #byrow = TRUE lets the matrix fill by row first
    matrix(1:12, byrow = TRUE, nrow = 4)
     	[,1] [,2] [,3]
	[1,]    1    2    3
	[2,]    4    5    6
	[3,]    7    8    9
	[4,]   10   11   12
    ```
	
 - Naming matrices
 	```R
    goog <- c(450, 451, 452, 468, 471)
	msft <- c(230, 231, 232, 233, 220)
	stocks <- c(goog, msft)

	stock.matrix <- matrix(stocks, byrow = 5, nrow = 2)

	days <- c('Mon', 'Tue', 'Wed', 'Thur', 'Fri')
	stock.names <- c('GOOG', 'MSFT')

	colnames(stock.matrix) <- days
	rownames(stock.matrix) <- stock.names

	print(stock.matrix)
         Mon Tue Wed Thur Fri
	GOOG 450 451 452  468 471
	MSFT 230 231 232  233 220 
    ```