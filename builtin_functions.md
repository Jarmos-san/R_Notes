# Built-in R Features & Functions

`seq()`: Create Sequences
----
The `seq()` function allows a user to create a sequence of number. The syntax of this function is as follows which can be described as the starting number of a sequence followed the ending number and the steps to skip numbers which are seperated by `,` commas.

_Syntax:_

```R
seq(start, end, step)
```

_Example:_

```R
seq(0, 10, 2)
0  2  4  6  8 10

seq(0, 100, 10)
0  10  20  30  40  50  60  70  80  90 100

seq(0, 24, 2)
0  2  4  6  8 10 12 14 16 18 20 22 24
```

`sort()`: Sort Vectors
-----
When a vector is created using the concatenate function `c()`, it isn't sorted properly. The `sort()` function sorts a vector in descending order(_by default_).

_Example_

```R
v <- c(1,4,6,7,2,13,2)

sort(v)
1 2 2 4 6 7 13

sort(v,decreasing = TRUE)
13 7 6 4 2 2 1
```

`rev()`: Reverse Elements of a Object
-----
`rev()` function is used for reversing the elements of an object.

```R
v2 <- c(1,2,3,4,5)

rev(v2)
5 4 3 2 1
```

`str()`: Show Structure of an Object
----
Mentioned earlier, it displays the structure of the dataset/object.

```R
str(v)
num [1:7] 1 4 6 7 2 13 2		#Shows that the vector has elements of a num value
```

`append()`: Merge Objects Together
----
The `append()` function works both of vectors and list and uses the following syntax;

_Example:_

```R
v1 <- 1:10
v2 <- 10:20
append(v1, v2)
1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20
```

Check/Covert Datatypes
-----
- `is.datatype` method
 
    ```R
    v <- c(1, 2, 3)
    
    is.vector(v)				# TRUE since v is a vector
    TRUE
    
    is.dataframe(v)			 # FALSE since v isn't a dataframe
    FALSE
    
    is.dataframe(mtcars)	    # TRUE since mtcars is a dataframe
    TRUE
    ```
    
- `as.datatype` method, is used to convert a certain datatype to another.

	```R
    v <- c(1, 2, 3)
    
    as.list(v)				   # Converts vector into list
    1
    2
    3
    ```
