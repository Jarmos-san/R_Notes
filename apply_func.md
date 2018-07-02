# The `apply()` Functions

Although there're a number of `apply()` functions available on R and a good alternative would be the `plyr` package. The list of some useful `apply()` functions for starters are:

- `apply()`: Required for applying a function to the rows or columns of a matrix (and higher-dimensional analogues) generally useful to manipulate data frames as it will coerce to a matrix first.

	_Example:_
    
    ```R
    # Two dimensional matrix
	M <- matrix(seq(1,16), 4, 4)

	# apply min to rows
	apply(M, 1, min)
	1 2 3 4

	# apply max to columns
	apply(M, 2, max)
	4  8 12 16

	# 3 dimensional array
	M <- array( seq(32), dim = c(4,4,2))

	# Apply sum across each M[*, , ] - i.e Sum across 2nd and 3rd dimension
	apply(M, 1, sum)
	# Result is one-dimensional
	120 128 136 144

	# Apply sum across each M[*, *, ] - i.e Sum across 3rd dimension
	apply(M, c(1,2), sum)
	# Result is two-dimensional
     	[,1] [,2] [,3] [,4]
	[1,]   18   26   34   42
	[2,]   20   28   36   44
	[3,]   22   30   38   46
	[4,]   24   32   40   48
    ```
    
- `lapply()`: Required when there's a need to apply a function to each element of a list in turn and get a list back.

	_Example:_
   
   ```R
   x <- list(a = 1, b = 1:3, c = 10:100) 
   lapply(x, FUN = length) 
   $a 
   1
   $b 
   3
   $c 
   91

   lapply(x, FUN = sum) 
   $a 
   1
   $b 
   6
   $c 
   5005 
   ```
   
- `sapply()`: Required when there's a need to apply a function to each element of a list in turn, but you want a vector back, rather than a list.
	
    _Example:_
    
    ```R
   x <- list(a = 1, b = 1:3, c = 10:100)
   #Compare with above; a named vector, not a list 
   sapply(x, FUN = length)  
   a  b  c   
   1  3 91

   sapply(x, FUN = sum)   
   a    b    c    
   1    6 5005    
   ```
   
- `vapply()`: Required when there's a need to use `sapply()` but perhaps need to squeeze some more speed out of your code. For `vapply()`, you basically give R an example of what sort of thing your function will return, which can save some time coercing returned values to fit in a single atomic vector.

	_Example:_
	
    ```R
	x <- list(a = 1, b = 1:3, c = 10:100)
	#Note that since the advantage here is mainly speed, this
	# example is only for illustration. We're telling R that
	# everything returned by length() should be an integer of 
	# length 1. 
	vapply(x, FUN = length, FUN.VALUE = 0L) 
	a  b  c  
	1  3 91  
    ```
    
- `mapply()`:Required for applying to several data structures(e.g. vectors, lists) and there's a need to apply a function to the 1st elements of each, and then the 2nd elements of each, etc., coercing the result to a vector/array as in sapply. This is multivariate in the sense that your function must accept multiple arguments.
	
    _Example:_
	
    ```R
	#Sums the 1st elements, the 2nd elements, etc. 
	mapply(sum, 1:5, 1:5, 1:5) 
	3  6  9 12 15
	
    #To do rep(1,4), rep(2,3), etc.
	mapply(rep, 1:4, 4:1)   
	[[1]]
	1 1 1 1

	[[2]]
	2 2 2

	[[3]]
	3 3
	
	[[4]]
	4    
	```
    
- `Map()`: It's a wrapper to `mapply()` with `SIMPLIFY = FALSE`, so it is guaranteed to return a list.

	_Example:_
	```R
	Map(sum, 1:5, 1:5, 1:5)
	[[1]]
    3

    [[2]]
    6

    [[3]]
    9

    [[4]]
    12

    [[5]]
    15    
    ```
    
- `rapply()`: Required when there's a need to apply a function to each element of a nested list structure, recursively. 

	_Example:_

    ```R
    #Append ! to string, otherwise increment
    myFun <- function(x){
        if (is.character(x)){
        return(paste(x,"!",sep=""))
        }
        else{
        return(x + 1)
        }
    }
    #A nested list structure
    l <- list(a = list(a1 = "Boo", b1 = 2, c1 = "Eeek"), 
          b = 3, c = "Yikes", 
          d = list(a2 = 1, b2 = list(a3 = "Hey", b3 = 5)))

        #Result is named vector, coerced to character           
        rapply(l,myFun)
        #Result is a nested list like l, with values altered
        rapply(l, myFun, how = "replace")    
    ```
    
- `tapply()`: Required there's a need to apply a function to subsets of a vector and the subsets are defined by some other vector, usually a factor.

	_Example:_
	
    ```R
    #A vector:
    x <- 1:20

    #A factor (of the same length!) defining groups:
    y <- factor(rep(letters[1:5], each = 4))

    #Add up the values in x within each subgroup defined by y:
    tapply(x, y, sum)  
    a  b  c  d  e  
    10 26 42 58 74
    ```   