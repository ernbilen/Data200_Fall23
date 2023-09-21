# Data 200: Data Systems for Data Analytics


# Homework 3: Access Operations in Pandas


<font color='red'>**Due Date and Time:** Sep 28 beginning of class </font>
---
Enter your name in the markdown cell below.

# Name:


```python
import numpy as np
import pandas as pd
```




<style>
blockquote { background: #AEDE94; }
h1 { 
    padding-top: 25px;
    padding-bottom: 25px;
    text-align: left; 
    padding-left: 10px;
    background-color: #DDDDDD; 
    color: black;
}
h2 { 
    padding-top: 10px;
    padding-bottom: 10px;
    text-align: left; 
    padding-left: 5px;
    background-color: #EEEEEE; 
    color: black;
}

div.exercise {
	background-color: #ffcccc;
	border-color: #E9967A; 	
	border-left: 5px solid #800080; 
	padding: 0.5em;
}

div.exercise-r {
	background-color: #fce8e8;
	border-color: #E9967A; 	
	border-left: 5px solid #800080; 
	padding: 0.5em;
}


span.sub-q {
	font-weight: bold;
}
div.theme {
	background-color: #DDDDDD;
	border-color: #E9967A; 	
	border-left: 5px solid #800080; 
	padding: 0.5em;
	font-size: 18pt;
}
div.gc { 
	background-color: #AEDE94;
	border-color: #E9967A; 	 
	border-left: 5px solid #800080; 
	padding: 0.5em;
	font-size: 12pt;
}
p.q1 { 
    padding-top: 5px;
    padding-bottom: 5px;
    text-align: left; 
    padding-left: 5px;
    background-color: #EEEEEE; 
    color: black;
}
header {
   padding-top: 35px;
    padding-bottom: 35px;
    text-align: left; 
    padding-left: 10px;
    background-color: #DDDDDD; 
    color: black;
}
</style>





# Tasks

- Read pages 145-204 in the textbook.
- Complete the **Transforming DataFrames** chapter of the **Data Manipulation with Pandas** course on DataCamp
- Commit + push your completed Jupyter notebook + .md output.

# Exercises

Run the code cell below that defines a dictionary of lists from a vet clinic.


```python
data = {
  'animal': ['cat','cat','snake','dog', 'dog','cat','snake','cat','dog','dog'],
  'age': [2.5, 3, 0.5, 7, 5, 2, 4.5, 4, 7, 3],
  'visits': [1, 3, 2, 3, 2, 3, 1, 1, 2, 1],
  'priority': ['yes','yes','no','yes','no',
  'no','no','yes','no', 'no']}
```

<div class="exercise"><b>Exercise 1</b></div> 

- Create a `pd.Index` called `row_names` that can be used to specify the row names of a dataframe, and set <code>name=`pet_names`</code>
- Create a dataframe called `vetInfo` from the dictionary `data` and assign the row labels to be `row_names`
- Print the dataframe.
    
The output from my solution is as follows: <br>

<code>
         animal  age  visits priority
names                                
Maisey      cat  2.5       1      yes
Finny       cat  3.0       3      yes
Slithery  snake  0.5       2       no
Fluffy      dog  7.0       3      yes
Rex         dog  5.0       2       no
Tucker      cat  2.0       3       no
Snakey    snake  4.5       1       no
Mason       cat  4.0       1      yes
Lou Lou     dog  7.0       2       no
Snoopy      dog  3.0       1       no</code>


```python
pet_names = ['Maisey', 'Finny', 'Slithery', 'Fluffy', 'Rex', 'Tucker', 'Snakey', 
             'Mason', 'Lou Lou', 'Snoopy']
## Your code here

```

<div class="exercise"><b>Exercise 2</b></div> 

Write Python code to select and print the following:

a) The data in rows with indices 2, 3, and 4<br>
b) The data in columns `animal` and `age`<br>

The output from my solution is:<br>

<code>
         animal  age  visits priority
names                                
Slithery  snake  0.5       2       no
Fluffy      dog  7.0       3      yes
Rex         dog  5.0       2       no
</code><code>
         animal  age
names               
Maisey      cat  2.5
Finny       cat  3.0
Slithery  snake  0.5
Fluffy      dog  7.0
Rex         dog  5.0
Tucker      cat  2.0
Snakey    snake  4.5
Mason       cat  4.0
Lou Lou     dog  7.0
Snoopy      dog  3.0</code>


```python

```

<div class="exercise"><b>Exercise 3</b></div> 

Use `iloc` to select the following:<br>

a) The rows with indices 2, 3, and 4<br>
b) The rows with indices 0, 1, and 2 for columns with indices 0, 2, and 3<br>

The output from my solution is:<br>

<code>
         animal  age  visits priority
names                                
Slithery  snake  0.5       2       no
Fluffy      dog  7.0       3      yes
Rex         dog  5.0       2       no
</code><code>
       animal  visits priority
names                         
Maisey    cat       1      yes
Finny     cat       3      yes</code>


```python

```

<div class="exercise"><b>Exercise 4</b></div> 

Use `loc` to select the following:<br>

a) The rows with labels `Maisey`, `Finny`, and `Snoopy`<br>
b) The rows with labels `Slithery` and `Snakey` for columns `age` and `visits`<br>

The output from my solution is:<br>

<code>
       animal  age  visits priority
names                              
Maisey    cat  2.5       1      yes
Finny     cat  3.0       3      yes
Snoopy    dog  3.0       1       no
</code><code>
          age  visits
names                
Slithery  0.5       2
Snakey    4.5       1</code>


```python

```

<div class="exercise"><b>Exercise 5</b></div> 

Print only the rows where `age` is greater than 3.

The output from my solution is:<br>

<code>
        animal  age  visits priority
names                               
Fluffy     dog  7.0       3      yes
Rex        dog  5.0       2       no
Snakey   snake  4.5       1       no
Mason      cat  4.0       1      yes
Lou Lou    dog  7.0       2       no</code>


```python

```

<div class="exercise"><b>Exercise 6</b></div> 

Print:

a) The rows where `priority` is `yes`.<br>
b) The rows where `priority` is `yes` and the `age` is greater than 3.<br>
c) The rows where `priority` is `yes`, but only for columns `animal` and `visits` (use `loc`).

The output from my solution is:<br>

<code>
       animal  age  visits priority
names                              
Maisey    cat  2.5       1      yes
Finny     cat  3.0       3      yes
Fluffy    dog  7.0       3      yes
Mason     cat  4.0       1      yes
</code><code>
       animal  age  visits priority
names                              
Fluffy    dog  7.0       3      yes
Mason     cat  4.0       1      yes
</code><code>
       animal  visits
names                
Maisey    cat       1
Finny     cat       3
Fluffy    dog       3
Mason     cat       1</code>


```python

```

<div class="exercise"><b>Exercise 7</b></div> 

Add a column `age_visit` which, for each row, is the age of the animal divided by the number of visits for the animal.  Print the updated dataframe.

The output from my solution is:<br>
<code>
         animal  age  visits priority  age_visit
names                                           
Maisey      cat  2.5       1      yes   2.500000
Finny       cat  3.0       3      yes   1.000000
Slithery  snake  0.5       2       no   0.250000
Fluffy      dog  7.0       3      yes   2.333333
Rex         dog  5.0       2       no   2.500000
Tucker      cat  2.0       3       no   0.666667
Snakey    snake  4.5       1       no   4.500000
Mason       cat  4.0       1      yes   4.000000
Lou Lou     dog  7.0       2       no   3.500000
Snoopy      dog  3.0       1       no   3.000000</code>


```python

```

<div class="exercise"><b>Exercise 8</b></div> 

Compute and print the mean age of the animals.

The output from my solution is:<br>
<code>
The average age of the animals is 3.85</code>


```python

```

<div class="exercise"><b>Exercise 9</b></div> 

Use the `isin(.)` function to print the rows corresponding to just dogs and cats.
The output from my solution is:<br>
<code>
        animal  age  visits priority  age_visit
names                                          
Maisey     cat  2.5       1      yes   2.500000
Finny      cat  3.0       3      yes   1.000000
Fluffy     dog  7.0       3      yes   2.333333
Rex        dog  5.0       2       no   2.500000
Tucker     cat  2.0       3       no   0.666667
Mason      cat  4.0       1      yes   4.000000
Lou Lou    dog  7.0       2       no   3.500000
Snoopy     dog  3.0       1       no   3.000000</code>


```python

```

<div class="exercise"><b>Exercise 10</b></div> 

Write Python code to:<br>

a) Import the `MotorTrend.csv` file as a dataframe.<br>
b) Print the shape of the dataframe.<br>
c) Print the first five rows of the dataframe (using the `head()` method).<br>

The output from my solution is:<br>
<code>
The shape of the dataframe is (32, 12)
                Name   mpg  cyl   disp   hp  drat     wt   qsec  vs  am  gear  \
0          Mazda RX4  21.0    6  160.0  110  3.90  2.620  16.46   0   1     4   
1      Mazda RX4 Wag  21.0    6  160.0  110  3.90  2.875  17.02   0   1     4   
2         Datsun 710  22.8    4  108.0   93  3.85  2.320  18.61   1   1     4   
3     Hornet 4 Drive  21.4    6  258.0  110  3.08  3.215  19.44   1   0     3   
4  Hornet Sportabout  18.7    8  360.0  175  3.15  3.440  17.02   0   0     3   
</code><code>
   carb  
0     4  
1     4  
2     1  
3     1  
4     2 </code>



```python

```

<div class="exercise"><b>Exercise 11</b></div> 

Use the `describe()` function to print the summary statistics, but just for columns `mpg` and `hp`.

The output from my solution is:<br>
<code>
             mpg          hp
count  32.000000   32.000000
mean   20.090625  146.687500
std     6.026948   68.562868
min    10.400000   52.000000
25%    15.425000   96.500000
50%    19.200000  123.000000
75%    22.800000  180.000000
max    33.900000  335.000000</code>


```python

```
