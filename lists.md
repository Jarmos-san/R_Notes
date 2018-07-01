# Lists

Content
----
- [Overview](https://github.com/Jarmos-san/R_Notes/blob/master/lists.md#overview)
- [Named Indexing](https://github.com/Jarmos-san/R_Notes/blob/master/lists.md#named-indexing)
- [Selecting Objects from List](https://github.com/Jarmos-san/R_Notes/blob/master/lists.md#selecting-objects-from-list)
- [Combining Lists](https://github.com/Jarmos-san/R_Notes/blob/master/lists.md#combining-lists)

Overview
-----

_**Lists**_ are data structures in the R-language that can store a 	   variety of data types - _vectors_, _matrices_, _dataframes_ and 		even other _lists_

_Example:_

```R
#create a vector
v <- c(1:5)

#create a matrix
mat <- matrix(1:10, nrow = 2)

#create data frame
df <- women

#combine all data types in one list
li <- list(v, mat, df)

li
[[1]]				#this are indexes
[1] 1 2 3 4 5

[[2]]				#index as well
     [,1] [,2] [,3] [,4] [,5]
[1,]    1    3    5    7    9
[2,]    2    4    6    8   10

[[3]]				#index here as well
    height weight
 1      58    115
 2      59    117
 3      60    120
 4      61    123
 5      62    126
 6      63    129
 7      64    132
 8      65    135
 9      66    139
 10     67    142
 11     68    146
 12     69    150
 13     70    154
 14     71    159
 15     72    164
   ```

Named Indexing
----
	
_Example_:
  
```R
li <- list(sample_vec = v, sample_mat = mat, sample_df = df)
  
li
$`sample_vec`
[1] 1 2 3 4 5

$sample_mat
     [,1] [,2] [,3] [,4] [,5]
[1,]    1    3    5    7    9
[2,]    2    4    6    8   10

$sample_df
   height weight
1      58    115
2      59    117
3      60    120
4      61    123
5      62    126
6      63    129
7      64    132
8      65    135
9      66    139
10     67    142
11     68    146
12     69    150
13     70    154
14     71    159
15     72    164
```

Selecting Objects from List
-----
The `[]` notation is used to show objects in a list while `[[ ]]` notation can be used to grab specific objects from within the list.

_Example:_

```R
# Single brackets
li[1]				# By index
$sample_vec =
1 2 3 4 5

# By name
li['sample_vec']
$sample_vec =
1 2 3 4 5

# Use double brackets to actually grab the items
li[['sample_vec']]
1 2 3 4 5

# Can also use $ notation
li$sample_vec
1 2 3 4 5

#once selected it can be indexed on top of that
li[['sample_mat']][1,]
1 3 5 7 9

li[['sample_df']]['height']
  height
1	 58
2	 59
3	 60
4	 61
5	 62
6	 63
7	 64
8	 65
9	 66
10	67
11	68
12	69
13	70
14	71
15	72
```

Combining Lists
----
lists can hold other lists within them as well using the `c()` function.

_Example:_

```R
list(c(li, li))
```
