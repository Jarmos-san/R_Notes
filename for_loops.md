# For Loops

Content
----
- [Overview](https://github.com/Jarmos-san/R_Notes/blob/master/for_loops.md#overview) 
- [Looping Over a Vector](https://github.com/Jarmos-san/R_Notes/blob/master/for_loops.md#looping-over-a-vector)
- [Looping Over a List](https://github.com/Jarmos-san/R_Notes/blob/master/for_loops.md#looping-over-a-list)
- [Looping Over a Matrix](https://github.com/Jarmos-san/R_Notes/blob/master/for_loops.md#looping-over-a-matrix)
- [Nested `For` Loops](https://github.com/Jarmos-san/R_Notes/blob/master/for_loops.md#nested-for-loops)

Overview
----
A `for` loop is used to iterate over an object like a vector or list, executing a piece of code with each loops. 
_Syntax:_

```R
for (temporary_variable in object){
    # Execute some code at every loop
}
```

Looping Over a Vector
----
`for` loops are effective at iterating through an iterable to create a temporary variable with the use of the `in` keyword. Like;

```R
vec <- c(1,2,3,4,5)
(temp_var in vec){
    print(temp_var)
}
1
2
3
4
5
```

The `length()` function can also be used to loop a certain number of times and then indexing to grab the values. Like;

```R
for (i in 1:length(vec)){
    print(vec[i])
}
1
2
3
4
5
```

Looping Over a List:
----
A `list` behaves somewhat similar to a `vector`

```R
li <- list(1,2,3,4,5)
for (temp_var in li){
    print(temp_var)
}
1
2
3
4
5

for (i in 1:length(li)){
    print(li[[i]]) # double brackets used to grab the index
}
1
2
3
4
5
```

Looping Over a Matrix:
----
A `matrix` can be iterated as well like;

```R
mat <- matrix(1:25,nrow=5)
mat
1	6	11	16	21
2	7	12	17	22
3	8	13	18	23
4	9	14	19	24
5	10	15	20	25

for (num in mat){
    print(num)
}
1
2
3
4
5
6
7
....
23
24
25
```

Nested For Loops:
----
`for` loops can be implemented inside another `for` loop, one downside of doing so is that the execution time increases.

```R
for (row in 1:nrow(mat)){
    for (col in 1:ncol(mat)){
        print(paste('The element at row:',row,'and col:',col,'is',mat[row,col]))
    }
}
[1] "The element at row: 1 and col: 1 is 1"
[1] "The element at row: 1 and col: 2 is 6"
[1] "The element at row: 1 and col: 3 is 11"
[1] "The element at row: 1 and col: 4 is 16"
[1] "The element at row: 1 and col: 5 is 21"
[1] "The element at row: 2 and col: 1 is 2"
....
[1] "The element at row: 5 and col: 3 is 15"
[1] "The element at row: 5 and col: 4 is 20"
[1] "The element at row: 5 and col: 5 is 25"
```
