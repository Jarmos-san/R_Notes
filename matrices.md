# Matrices
- Matrices are 2D data structures storing elements of the same data types.

Creating a matrix
-------
Example:

```R
matrix(1:10)	#Creates a 2D matrix with 10 rows and 1 columns
      [,1]
 [1,]    1
 [2,]    2
 [3,]    3
 [4,]    4
 [5,]    5
 [6,]    6
 [7,]    7
 [8,]    8
 [9,]    9
 [10,]   10
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

Matrix Arithmatic
------

- Simple arithmatic opeartions can be done through R on various matrices.

	```R
	mat <- matrix(1:25, byrow = T, nrow = 5)
	mat
	     [,1] [,2] [,3] [,4] [,5]
	[1,]    1    2    3    4    5
	[2,]    6    7    8    9   10
	[3,]   11   12   13   14   15
	[4,]   16   17   18   19   20
	[5,]   21   22   23   24   25
	```
- Matrix Multiplication

	```R
	mat *2	#Element-wise matrix multiplication
	     [,1] [,2] [,3] [,4] [,5]
	[1,]    2    4    6    8   10
	[2,]   12   14   16   18   20
	[3,]   22   24   26   28   30
	[4,]   32   34   36   38   40
	[5,]   42   44   46   48   50

	mat %*% mat	#True matrix multiplication(Linear Algebra method)
	     [,1] [,2] [,3] [,4] [,5]
	[1,]  215  230  245  260  275
	[2,]  490  530  570  610  650
	[3,]  765  830  895  960 1025
	[4,] 1040 1130 1220 1310 1400
	[5,] 1315 1430 1545 1660 1775
	```
- Matrix Division

	```R
	mat / 2
	     [,1] [,2] [,3] [,4] [,5]
	[1,]  0.5  1.0  1.5  2.0  2.5
	[2,]  3.0  3.5  4.0  4.5  5.0
	[3,]  5.5  6.0  6.5  7.0  7.5
	[4,]  8.0  8.5  9.0  9.5 10.0
	[5,] 10.5 11.0 11.5 12.0 12.5
	```

- Matrix Exponentiation

	```R
	mat ^ 2
	     [,1] [,2] [,3] [,4] [,5]
	[1,]    1    4    9   16   25
	[2,]   36   49   64   81  100
	[3,]  121  144  169  196  225
	[4,]  256  289  324  361  400
	[5,]  441  484  529  576  625
	```

- Comparison Operators on Matrices
	Comparison operations between matrices returns a matrix of `logical` values.
    
	```R
	mat > 10
	      [,1]  [,2]  [,3]  [,4]  [,5]
	[1,] FALSE FALSE FALSE FALSE FALSE
	[2,] FALSE FALSE FALSE FALSE FALSE
	[3,]  TRUE  TRUE  TRUE  TRUE  TRUE
	[4,]  TRUE  TRUE  TRUE  TRUE  TRUE
	[5,]  TRUE  TRUE  TRUE  TRUE  TRUE

	mat[mat > 10]	#This way the values can be filtered out
	 [1] 11 16 21 12 17 22 13 18 23 14 19 24 15 20 25
	```								

- Addition and Subtraction Between Matrices

	```R
	 mat + mat	#Addition
	     [,1] [,2] [,3] [,4] [,5]
	[1,]    2    4    6    8   10
	[2,]   12   14   16   18   20
	[3,]   22   24   26   28   30
	[4,]   32   34   36   38   40
	[5,]   42   44   46   48   50

	 mat - mat	#Subtraction
	     [,1] [,2] [,3] [,4] [,5]
	[1,]    0    0    0    0    0
	[2,]    0    0    0    0    0
	[3,]    0    0    0    0    0
	[4,]    0    0    0    0    0
	[5,]    0    0    0    0    0
	```

Matrix Operations
------

- Basic functions across columns and rows
	
	More functions of matrices are available [here](https://cran.r-project.org/doc/contrib/Short-refcard.pdf)

	```R
	goog <- c(450,451,452,445,468)
	msft <- c(230,231,232,233,220)

	stocks <- c(goog,msft)

	stock.matrix <- matrix()
	stock.matrix <- matrix(stocks,byrow = TRUE,nrow = 2)
	days <- c('Mon','Tue','Wed','Thu','Fri')
	st.names <- c('GOOG','MSFT')

	colnames(stock.matrix) <- days
	row.names(stock.matrix) <- st.names

	print(stock.matrix)
	     Mon Tue Wed Thu Fri
	GOOG 450 451 452 445 468
	MSFT 230 231 232 233 220

	#Adding all elements in a column
	colSums(stock.matrix)
	Mon Tue Wed Thu Fri 
	680 682 684 678 688 

	#Adding all elements in a row
	rowSums(stock.matrix)
	GOOG MSFT 
	2266 1146 

	#Average of all elements in a row
	rowMeans(stock.matrix)
	GOOG  MSFT 
	453.2 229.2 
	```

- Binding Rows and Columns

	```R
	FB <- c(111,112,113,120,145)
	tech.stocks <- rbind(stock.matrix,FB)
	print(tech.stocks)
	     Mon Tue Wed Thu Fri
	GOOG 450 451 452 445 468
	MSFT 230 231 232 233 220
	FB   111 112 113 120 145

	avg <- rowMeans(tech.stocks) 
	print(avg)
	GOOG  MSFT    FB 
	453.2 229.2 120.2 

	tech.stocks <- cbind(tech.stocks,avg)
	print(tech.stocks)
	     Mon Tue Wed Thu Fri   avg
	GOOG 450 451 452 445 468 453.2
	MSFT 230 231 232 233 220 229.2
	FB   111 112 113 120 145 120.2
	```
