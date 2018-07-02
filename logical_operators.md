# Logical Operators

Overview:
----
Logical Operators allows us to combine multiple comparison operators in a statement. The logical operators and their R notation are listed as follows:
	
- `AND` denoted as `&` returns a single `TRUE` if **ALL** returned values are `TRUE`.
- `OR` denoted as `|` returns a single `TRUE` if **ANY** returned values are `TRUE`. 
- `NOT` denoted as `!` returns `TRUE` if logical comparison is `FALSE`. 


`AND`/`&` Operator:
-----
```R
x <- 10
x < 20 & x > 5
TRUE

#parenthesises are used for readability
(x < 20) & (x > 5)
TRUE

(x < 20) & (x > 5) & (x == 10)
TRUE

x == 2 & x > 1		#returns FALSE and TRUE
FALSE				 #both value needs to TRUE
```

`OR`/`|` Operator:
------
```R
x == 2 | x > 1		#returns FALSE TRUE
TRUE				  #any value needs to TRUE

x == 1 | x == 12	
FALSE			     #neither variable is TRUE
```

`NOT`/`!` Operator:
------
The `NOT`/`!` can be understood as returning a reverse of any logical value infront of it. Like

```R
10 == 1
FALSE

!(10 == 1)
TRUE
```
