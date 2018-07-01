# While Loops

A `while` loop are used to make the program run continuosly while some condition/a block of code is met(or made `TRUE`). Also it's important to keep in mind that the `while` loop will keep executing itself if at a certain point the condition isn't `TRUE`. The `while` loops follows the syntax as mentioned below;

```R
while(condition){
	#code here
    #while condition is TRUE
}
```

_Example:_

```R
x <- 0
while(x < 10){
    cat('x is currently: ',x)
    print(' x is still less than 10, adding 1 to x')
    # add one to x
    x <- x+1
    if(x==10){
        print("x is equal to 10! Terminating loop")
    }
}

x is currently:  0[1] " x is still less than 10, adding 1 to x"
x is currently:  1[1] " x is still less than 10, adding 1 to x"
x is currently:  2[1] " x is still less than 10, adding 1 to x"
x is currently:  3[1] " x is still less than 10, adding 1 to x"
x is currently:  4[1] " x is still less than 10, adding 1 to x"
x is currently:  5[1] " x is still less than 10, adding 1 to x"
x is currently:  6[1] " x is still less than 10, adding 1 to x"
x is currently:  7[1] " x is still less than 10, adding 1 to x"
x is currently:  8[1] " x is still less than 10, adding 1 to x"
x is currently:  9[1] " x is still less than 10, adding 1 to x"
"x is equal to 10! Terminating loop"
```

Break Function
----
The `break` function can be used inside a `while` loop to break out of the loop.

_Example:_

```R
x <- 0

while(x < 10){
    
    cat('x is currently: ',x)
    print(' x is still less than 10, adding 1 to x')
    
    # add one to x
    x <- x+1
    if(x==10){
        print("x is equal to 10!")
        break
        print("I will also print, woohoo!")
    }
}

x is currently:  0[1] " x is still less than 10, adding 1 to x"
x is currently:  1[1] " x is still less than 10, adding 1 to x"
x is currently:  2[1] " x is still less than 10, adding 1 to x"
x is currently:  3[1] " x is still less than 10, adding 1 to x"
x is currently:  4[1] " x is still less than 10, adding 1 to x"
x is currently:  5[1] " x is still less than 10, adding 1 to x"
x is currently:  6[1] " x is still less than 10, adding 1 to x"
x is currently:  7[1] " x is still less than 10, adding 1 to x"
x is currently:  8[1] " x is still less than 10, adding 1 to x"
x is currently:  9[1] " x is still less than 10, adding 1 to x"
"x is equal to 10!"
```

The `break` function stopped the loop right on the tracks before the executing the `print("I will also print, woohoo!")`
