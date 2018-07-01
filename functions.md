# Functions

Content
----

- [Overview](https://github.com/Jarmos-san/R_Notes/blob/master/functions.md#overview)
- [Default Values of a Function](https://github.com/Jarmos-san/R_Notes/blob/master/functions.md#default-values-of-a-function)
- [Returning Values](https://github.com/Jarmos-san/R_Notes/blob/master/functions.md#returning-values)
- [Scope](https://github.com/Jarmos-san/R_Notes/blob/master/functions.md#scope)

Overview
----
Functions act as the building block of programming on R. Formally, functions are defined as a set of statements that can be run repeatedly and certain parameters can be passed into it as arguments for the function as well. Fundamentally, functions are created for code reusability and making repeatative piece of code to be reused efficiently. The _syntax_ to write a user-defined function is;

```R
func_name <- function(arg1,arg2,...){
	# Code that gets executed when function is called
}
```

_Example:_

```R
hello <- function(){
	print('Hello!)
}

hello()
'Hello!'

# Another example
add_num <- function(num1,num2){
    print(num1+num2)
}

add_num(5,10)
15
```
Default Values of a Function:
-----
Default values of a function can be assigned with an `=` like;

```R
hello_someone <- function(name='Frankie'){
    print(paste('Hello ',name))
}

# uses default
hello_someone()
"Hello  Frankie"

# overwrite default
hello_someone('Sammy')
"Hello  Sammy"
```

Returning Values:
----
The `return` keyword can be used to return results so that it can be assigned to a variable like;

```R
formal <- function(name='Sam',title='Sir'){
    return(paste(title,' ',name))
}

formal()		#function returns default values
'Sir Sam'

formal('Issac Newton')	#function returns value based on parameters passed
'Sir Issac Newton'

var <- formal('Marie Curie','Ms.')
var
'Ms. Marie Curie'
```

Scope:
----
The term _**Scope**_ is usually thought of as the definition of objects and variables in R. A thumb rule usually followed is that a variable is considered `global` when it's defined outside a function, rather than inside it.

```R
# Multiplies input by 5
times5 <- function(num) {
  result <- num * 5			# num and result aren't globals
  return(result)
}

times5(4)
20
```

Another example;

```R
v <- "I'm global v"
stuff <- "I'm global stuff"

fun <- function(stuff){
    print(v) 
    stuff <- 'Reassign stuff inside func'
    print(stuff)
}

print(v) #print v
print(stuff) #print stuff
fun(stuff) # pass stuff to function
# reassignment only happens in scope of function
print(stuff)
"I'm global v"
"I'm global stuff"
"I'm global v"
"Reassign stuff inside func"
"I'm global stuff"
```

_**Explanation:**_
So what is happening above?

The following happens:

`print(v)` will check for the global variable `v`, the outer scope.

`print(stuff)` will also check for the global variable stuff.

`fun(stuff)` will accept an argument `stuff`, print out `v`, and then reassign `stuff` (in the scope of the function) and print out `stuff`. 

Two things happened here:

The reassignment of `stuff` only effects the scope of the `stuff` variable inside the function

The `fun` function first checks to see if `v` is defined at the function scope, if not (which was the case) it will then search the global scope for a variable names `v`, leading to it printing out `"I'm global v"`.

Simpler _example:_

```R
# defining the function
double <- function(a){
  a <- 2 * a
  return(a)
}

var <- 5	   # global scope

double(var)	# scope within function
var
10
5
```
