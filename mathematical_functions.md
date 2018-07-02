# Math Functions

R can be used to perform some easy and effective math functions which allows the user to directly call a function rather than doing manual mathematical operations.

_Examples:_

```R
v <- c(-1,0,1,2,3,4,5)
abs(-2)
2

abs(v)
0 1 2 3 4 5

sum(v)
14

mean(v)
2

round(23.1231)
23

round(23.1231234,2)
23.12
```

A table of a couple more mathematical functions:


| Function				| Description 							  |
|----------------------	|-----------------------------------------|
| abs(x)				| absolute value 						  |
| sqrt(x)				| square root 							  |
| ceiling(x)			|	ceiling(3.475) is 4 				  |
| floor(x)				|floor(3.475) is 3 						  |
| trunc(x)				|trunc(5.99) is 5 						  |
| round(x, digits=n)	|round(3.475, digits=2) is 3.48 		  |
| signif(x, digits=n)	|signif(3.475, digits=2) is 3.5 		  |
| cos(x), sin(x), tan(x)|	also acos(x), cosh(x), acosh(x), etc. |
| log(x)				| natural logarithm 					  |
| log10(x)				|common logarithm 						  |
| exp(x)				|e^x 									  |