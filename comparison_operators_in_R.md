Comparison Operators in R
------

- **Comparison Operators** in R is used to make comparison between variables returning a logical value.

	Example:
	```R
    5 > 6
    FALSE
    5 < 6
    TRUE
    5 <= 6
    TRUE
    5 >= 5
    TRUE
    2 == 3 	#'==" is for checking equality
    	   	#'=' is for assignment
    FALSE
    2 != 3
    TRUE
    ```
- Spacing between numbers and the comparison operator is important since `<-` is used to make an assignment to a variable.

	Example:
    ```R
    v <- 2	#2 is assigned to the variable v
    
    v <-1 	#-1 is assigned to V
    v
    1
    
    v < -1	#Compares between variable v and the numeric -1
    FALSE
    ```
    
- Using **Comparison Operators** between vectors returns a vector of **Logical Values**

	Example:
    ```R
    v <- c(1,2,3,4,5)
    v < 2 #Operator checks each element in vector v for elements less than 2
    FALSE TRUE FALSE FALSE FALSE
    v == 2
    FALSE FALSE TRUE FALSE FALSE FALSE
    ```
    
- Comparison between vectors

	Example:
    ```R
    v1 <- c(10,22,34,73)
    v2 <- c(12,22,34, 89)
    v1 == v2
    FALSE TRUE TRUE FALSE
    ```