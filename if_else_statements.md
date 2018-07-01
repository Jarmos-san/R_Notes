# If-Else Loop

`if` Statement
----

The `if-else` loop can be used to program logical statements into R. In other words, the `if-else` loop is meant for executing a code inside a loop _if_ some condition is `TRUE`. The syntax for a `if-else` loop is as follows;

```R
if (condition){
    # Execute some code
}
```

_Example:_

```R
hot <- FALSE
temp <- 60

if (temp > 80){
    hot <- TRUE
}

hot
FALSE

# Reset temp
temp <- 100
if (temp > 80){
    hot <- TRUE
}

hot
TRUE
```

_**NOTE:**_ It's important to format the `if-else` statements for better readability. The ending curly bracket `}` should align properly with the the `if` statement.

`else` Statement:
-----
The `else` statements are used when another piece of code needs to be executed right after the `if` statement.
_Syntax:_

```R
if (condition) {
  # Code to execute if true
} else {
  # Code to execute if above was not true
}
```

_Example:_

```R
temp <- 30
if (temp > 90){
    print("Hot outside!")
} else{
    print("Its not too hot today!")
}
"Its not too hot today!"
```

`else if` Statement:
----
The `else if` statement can be used to make multiple conditional checks between the `if` and `else` statements.

_Example:_

```R
temp <- 30
if (temp > 80){
    print("Hot outside!")
} else if(temp<80 & temp>50){
    print('Nice outside!')
} else if(temp <50 & temp > 32){
    print("Its cooler outside!")
} else{
    print("Its really cold outside!")
}
"Its really cold outside!"
```

_Example_ of a `if`, `else` and `if else` program:

```R
ham <- 10
cheese <- 10

report <- 'blank'
if(ham >= 10 & cheese >= 10){
    report <- "Strong sales of both items"
}else if(ham == 0 & cheese == 0){
    report <- "Nothing sold!"
}else{
    report <- 'We had some sales'
}
print(report)
"Strong sales of both items"
```