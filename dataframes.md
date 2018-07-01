# Data Frames

Content:
-----
- [Dataframe Built-in Functions]()
- [Indexing and Slicing]()
- [Dataframes Overview]()

Unlike _**vectors**_ and _**matrices**_, _**dataframes**_ are quite powerful as they can store multiple data types within it.
R has some built-in dataframes which like `mtcars`, `women`,  `states.x77` datasets. On a first glance it would be quite obvious how Dataframes has rows and columns just like matrices but they're named. The list of **ALL** the datasets available on R-base can be accessed through the function `data()`. 
The following command is quite interesting to check as well `data(package = .packages(all.available = TRUE))`. This will display all the available datasets that came pre-packed along with the various packages that you might have installed sometime around.

Dataframe Built-in Functions
-----
- Some of the pre-packed datasets can be quite huge and difficult to read thus the `head(dataframe)` and the `tail(dataframe)` function helps to check the first and last 6 rows of the specified dataframe.

- The `str(dataframe)` function can be used to check the structure of the dataframe and the data type it contains like variable names and their data types.

	_Example:_
	
    ```R
    str(women)
	#line1 = structure of the dataset
    #line2 = column1 name and the variables
    #line3 = column2 name and the variables
    'data.frame':	15 obs. of  2 variables:
 	$ height: num  58 59 60 61 62 63 64 65 66 67 ...
 	$ weight: num  115 117 120 123 126 129 132 135 139 142 ...
    ```
    
- The `summary(dataframe)` functions displays the statistical data of the dataset.
	
    _Example:_
    
    ```R
	 summary(women)
	    height    
	Min.   :58.0  
	1st Qu.:61.5  
	Median :65.0  
	Mean   :65.0  
	3rd Qu.:68.5  
	Max.   :72.0  
	    weight     
	Min.   :115.0  
	1st Qu.:124.5  
	Median :135.0  
	Mean   :136.7  
	3rd Qu.:148.0  
	Max.   :164.0  
    ```
    
Indexing and Slicing
-----
- Similar to **Indexing** and **Slicing** in `matrices`, the same can be done with `dataframes` as well in the fowllowing syntax `df[row, colum]`.  

- Dataframes can also be indexed using the `column name`.

	_Example:_
    
    ```R
   #Displays a vector of variable values
   women[1:6, 'height']
   58 59 60 61 62 63	
   
   #Displays all the variables in the column "height" 
   women$height
   58 59 60 61 62 63 64 65 66 67 68 69 70 71 72
    ```
    
- The `subset()` function on the other hand helps display data based on the comparison between certain variables in the syntax `subset(dataframe, subset = "comparison statement"`, the `"comparison statement"` takes in a comparison between variables.

	_Example:_
    
    ```R
   #Displays the variables of women taller than 67
   subset(women, subset = height > 67)
  	 height weight
	11     68    146
	12     69    150
	13     70    154
	14     71    159
	15     72    164
    ```
    
Dataframes Overview
----
- _**Creating Dataframes**_: R can create dataframes as much as it can work on them.

	_Example:_
    
    ```R
    c1 <- 1:10
	c2 <- letters[1:10]	#"letters" is an in-built function to display letters
	df <- data.frame
	df <- data.frame(col1 = c1, col2 = c2)
	df
   	col1 col2
	1     1    a
	2     2    b
	3     3    c
	4     4    d
	5     5    e
	6     6    f
	7     7    g
	8     8    h
	9     9    i
	10   10    j	    
    ```
    
- _**Importing and Exporting Data**_:

	```R
	read.csv(~/path/to/filename.csv)					 #Function to read .csv files
	write.csv(~/path/to/save/destinatio/filename.csv)	#Function to write .csv files
    ```

- _**Getting information about dataframe**_:

	```R
    nrow(df)	  #count rows
    ncol(df)	  #count columns
    colnames()	#check columns names
    rownames()	#check row names
    ```

- _**Dealing with missing values**_:

    ```R
	 head(is.na(women))	  #Check for missing in the dataset
     height weight		   #returns df of bolean values
	[1,]  FALSE  FALSE
	[2,]  FALSE  FALSE
	[3,]  FALSE  FALSE
	[4,]  FALSE  FALSE
	[5,]  FALSE  FALSE
	[6,]  FALSE  FALSE
    
    any(is.na(women))		# Checks whole dataset for missing value
	[1] FALSE				#returns a T if 1+ missing value exists
    
    df[is.na(df)] <- 0	   #used to assign a value to missing values
    ```