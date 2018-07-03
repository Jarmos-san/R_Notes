# The Pipe `%>%` Operator

While the `%>%` Pipe operator isn't really required while using the `dplyr` or `tidyr` packages, it can be very useful when trying to perform multiple operations/functions on a data set. The pipe operator will allow you to avoid either a long nested operation or doing a bunch of assignmets.

_Example:_

```R
df <- mtcars

library(dplyr)

# Using Nesting
library(dplyr)
arrange(sample_n(filter(df,mpg>20),size=5),desc(mpg))

 mpg	cyl    disp	hp	 drat	wt	   qsec	 vs   am	gear	carb
 27.3	4	 79	  66	 4.08	1.935	18.9 	1	 1	  4	   1
 26	  4	 120.3   91	 4.43	2.14 	16.7 	0	 1      5	   2
 24.4	4	 146.7   62	 3.69	3.19 	20	   1	 0	  4       2
 22.8	4	 140.8   95	 3.92	3.15 	22.9	 1	 0	  4	     2
 21	  6	 160	 110	3.9	 2.875	17.02	0	 1	  4	   4

# Using Multiple Assignments

library(dplyr)
a <- filter(df,mpg > 20)
b <- sample_n(a,size = 5)
c <- arrange(b,desc(mpg))
c

mpg	cyl	disp	hp	 drat	wt	   qsec	 vs   am  gear carb
30.4	4	 95.1	113	3.77	1.513	16.9	  1	1	5	2
30.4	4	 75.7	52	 4.93	1.615	18.52	 1	1	4	2
24.4	4	 146.7   62	 3.69	3.19	 20	    1	0	4	2
21.5	4	 120.1   97	 3.7	 2.465	20.01	 1	0	3	1
21.4	4	 121	 109	4.11	2.78	 18.6	  1	1	4	2

# Using the Pipe Operator
library(dplyr)
df %>% filter(mpg > 20) %>% sample_n(size = 5) %>% arrange(desc(mpg))

mpg	cyl	disp	hp	drat	wt	  qsec	vs	am  gear carb
30.4	4	 75.7	52	4.93	1.615   18.52	1	1	4	2
26	  4	 120.3   91	4.43	2.14	16.7	 0	1	5	2
24.4	4	 146.7   62	3.69	3.19	20	   1	0	4	2
22.8	4	 108	 93	3.85	2.32	18.61	1	1	4	1
21	  6	 160	 110	3.9	2.62	16.46	0	1	4	4

```