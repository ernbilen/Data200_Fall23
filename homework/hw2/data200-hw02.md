# Data 200: Data Systems for Data Analytics


# Homework 2: Introduction to NumPy

<font color='red'>**Due Date:** Sep 19 beginning of class </font>
---
Welcome!🎪 As a reminder, you will turn in your assignment by making changes on this Jupyter Notebook file which is already saved on your Github repository after you accepted my invitation for the assignment. You will work on this file locally. (You can either manually download the files from the online repo, or "clone" it via "Code">"Open with Github Desktop" which downloads a local copy for you, and makes "committing" easier.) Once you finish and you are ready to submit, go to Github and "commit" + "push" to turn in your assignment. Make sure to submit two things: Your completed assignment **as a Markdown file** and the source **.ipynb file**.

I will grade your assignment by opening your "hw2.ipynb" file in Jupyter (in a directory containing all required data files), clicking "Kernel > Restart & Run All", reading the output, and reading your "hw2.md" file. Any code that fails to run due to errors receives a 0, so make sure to "Restart & Run All" your file and verify that all code runs without any issues before you submit.

Please enter your name by double clicking on the cell below.


# Name:


```python
import numpy as np
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





# Prelim Tasks

- Read pages 3-15 in the textbook, Bressoud and White.
- Complete the **numPy** chapter of the **Introduction to Python** course on DataCamp. I have sent you an invitation last week. Make sure to use your Dickinson email address to register.
- Read notes posted on Github.

# Exercises

Run the code cell below.


```python
values = [23, 19, 34, 50]
```

<div class="exercise"><b>Exercise 1</b></div> 

Convert the Python list `values` to a NumPy array called `np_values` and then print the array.


```python

```

<div class="exercise"><b>Exercise 2</b></div> 

Using the `np.arange(.)` function: <br><br>
a) Create an array `x` with integers ranging from 12 to 36.<br>
b) Create an array `x2` with even integers ranging from 10 to 20.<br>
c) Create an array `x3` with integers from 8 to -4 in a backwards fashion.<br>

Be sure to print the arrays to obtain the following expected output:<br><br>`[12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35]`<br>`[10 12 14 16 18]
`<br>`[ 8  7  6  5  4  3  2  1  0 -1 -2 -3]`


```python

```

Run the code cell below, which defines an array `mpg` of miles-per-gallon (mpg) of a fleet of vehicles.


```python
mpg = np.array([19, 23, 20, 21, 20, 23, 21, 21, 23, 19, 24, 23, 28, 19, 18, 21, 23, 17, 20, 20, 20, 21, 24, 18, 15])
```

<div class="exercise"><b>Exercise 3</b></div> 

Develop Python code to accomplish the following (you may want to review Boolean Indexing):<br><br>
a) Print the elements in `mpg` from index 3 to 10<br>
b) Print the elements in `mpg` from index 15 forward<br>
c) Create and print an array `goodMpg` that contains all the elements in `mpg` that are >= 23<br>
d) Create and print an array `okMpg` that contains all the elements in `mpg` that are strictly between 18 and 23<br>
e) Using *vectorization*, convert the `mpg` values to kilometers-per-liter (kpl) and assign it to the array `kpl`--be sure to print the new array. Note: 1 mpg = 0.425 kpl.<br>

The expected output for this exercise is as follows:<br>
    
<code>[21 20 23 21 21 23 19]
[21 23 17 20 20 20 21 24 18 15]
[23 23 23 24 23 28 23 24]
[19 20 21 20 21 21 19 19 21 20 20 20 21]
[  8.075   9.775   8.5     8.925   8.5     9.775   8.925   8.925   9.775
   8.075  10.2     9.775  11.9     8.075   7.65    8.925   9.775   7.225
   8.5     8.5     8.5     8.925  10.2     7.65    6.375]</code>


```python

```

<div class="exercise"><b>Exercise 4</b></div> 
Develop Python code to do the following:<br>

a) Create and print a 3x3 matrix A (2D NumPy array) with values ranging from 2 to 10 (using `arange(.)` and `reshape(.)`). <br>
b) Negate all the numbers of A that are strictly between 3 and 7 and then print the updated matrix.<br>

The expected output for this exercise is as follows:<br>
        
<code>[[ 2  3  4]
 [ 5  6  7]
 [ 8  9 10]]</code>

<code>
[[ 2  3 -4]
 [-5 -6  7]
 [ 8  9 10]]</code>



```python

```

<div class="exercise"><b>Exercise 5</b></div> Develop Python code to do the following:<br><br>
a) Print the first row of A (from the previous exercise--the updated matrix from part (b)<br>
b) Print the third column of A (from the previous exercise)--make sure the output is a 3x1 column!<br>
c) Print the sum of the values of the second column of A<br>
d) Print the average of all the values of A<br>
e) Print the median of the values of the first column of A<br>

The expected output for this exercise is as follows:<br>
        
<code>[ 2  3 -4]</code>

<code>
[[-4]
 [ 7]
 [10]]</code>

`6`

`2.66666666667`

`2.0`


```python

```

<div class="exercise"><b>Exercise 6</b></div>Use *broadcasting* to add the row [-2 1 2] to each of the rows of A<br>

The expected output for this exercise is as follows:<br>
        
<code>[[ 0  4 -2]
 [-7 -5  9]
 [ 6 10 12]]</code>


```python

```

<div class="exercise"><b>Exercise 7</b></div>Create and print a 4x3x2 (3-dimensional) array B consisting of the numbers 0 through 23

The expected output for this exercise is as follows::<br>
        
<code>[[[ 0  1]
  [ 2  3]
  [ 4  5]]</code>

 <code>[[ 6  7]
  [ 8  9]
  [10 11]]</code>

 <code>[[12 13]
  [14 15]
  [16 17]]</code>

 <code>[[18 19]
  [20 21]
  [22 23]]]</code>


```python

```
