# Data 200: Data Systems for Data Analytics


# Homework 5: Single Table Operations with SQL Part 1


<font color='red'>**Due Date and Time:** Oct 31 beginning of class. </font>
---
Enter your name in the markdown cell below.

# Name:

# Tasks

- **Make sure you have installed SQL Magic before you begin** via `! pip install ipython-sql`.
- Review pages 313-335 in the Bressoud & White Introduction to Data Systems.
- Complete the **Selecting Columns** and **Filtering Rows** chapters of the **Intermediate SQL Queries** course on DataCamp.

# Exercises

This homework will make use of the `book.db` database, which should already be located in the same folder as this notebook in your clone repo.  I suggest that you review pages 315-317 in the course textbook to familiarize yourself with the tables in `book.db`.

**Make sure the `book.db` database is in the same directory as this notebook**, so the chunk below can execute.

Then, run the code cell below to load the SQL Magic module and connect to the `book.db` database. Don't forget to install the `ipython-sql` package if you have not already.


```python
%load_ext sql
%sql sqlite:///book.db
```

<div class="exercise"><b>Exercise 1:</b></div> 

Select the `year`, `code`, `pop`, and `cell` fields from the `indicators` table, limiting the results to 5 records.

The output from my solution is:<br>
<code>
year	code   pop	cell
1960	ABW	0.05	0.0
1960	AFG	9.0	 0.0
1960	AGO	5.45	0.0
1960	ALB	1.61	0.0
1960	AND	0.01	0.0
</code>


```sql
%%sql
/* Enter your SQL query below */


```

<div class="exercise"><b>Exercise 2:</b></div> 

Use an SQL query to select the `year`, `code`, `pop`, `gdp`, and `life` fields from the `indicators` table, ordered by life expectancy from high to low.  Limit the number of records to six.

The output from my solution is:<br>
<code>
year	code	pop	gdp	   life
2012	SMR	0.03	1.8	   85.4
2017	HKG	7.39	341.65	84.7
2015	HKG	7.29	309.38	84.3
2016	HKG	7.34	320.86	84.2
2017	JPN	126.79  4859.95   84.1
2014	HKG	7.23	291.46	84.0
</code>


```sql
%%sql
/* Enter your SQL query below */


```

<div class="exercise"><b>Exercise 3:</b></div> 

Use an SQL query to determine in which year was the maximum number of cell phones in any country (in the `indicators` table).

**Note:** Your query should reveal that the maximum number of cell phones in any country was in **2017**.


```sql
%%sql
/* Enter your SQL query below */


```

<div class="exercise"><b>Exercise 4:</b></div> 

Write a query to find all the distinct years that appear in the `indicators` table. Limit the results to 5 rows.

The output from my solution is:<br>
<code>
year
1960
1961
1962
1963
1964
</code>


```sql
%%sql
/* Enter your SQL query below */


```

<div class="exercise"><b>Exercise 5:</b></div> 

With regards to the `indicators` table, write a query that selects all the fields, but only returns rows for which there is no missing data for the `gdp` field.  Limit your results to five rows.

The output from my solution is:<br>
<code>
year	code	pop	gdp	life	cell	imports exports
1960	AFG	9.0	 0.54	32.3	0.0	None	   49.9
1960	AUS	10.28  18.58	70.8	0.0	2524.06  2022.9
1960	AUT	7.05	6.59	68.6	0.0	1408.8   1118.9
1960	BDI	2.8 	0.2	 41.3	0.0	None	   None
1960	BEL	9.15	11.66   69.7	0.0	None	   None
</code>


```sql
%%sql
/* Enter your SQL query below */


```

<div class="exercise"><b>Exercise 6:</b></div> 

Write a query to find all rows of the `indicators` table where the life expectancy is between 50 and 65 (inclusively), ordered from largest to smallest life expectancy. Include the `year`, `code`, `pop`, and `life` fields for such rows.  Limit your results to five rows.

The output from my solution is:<br>
<code>
year	code   pop	life
1960	ARG	20.48  65.0
1961	HRV	4.17   65.0
1961	JAM	1.65   65.0
1965	BRN	0.1    65.0
1965	PRT	9.0	65.0
</code>


```sql
%%sql
/* Enter your SQL query below */


```

<div class="exercise"><b>Exercise 7:</b></div> 

Write a query to find all rows of the `indicators` table where exports are greater than imports, ordered by exports from smallest to largest.  Include the `year`, `code`, `imports`, and `exports` fields for such rows.  Limit your results to five rows.

The output from my solution is:<br>
<code>
year	code imports exports
1962	FRO	 0.1	  0.7
1960	TGO	 0.4	  1.0
1961	TGO	 0.6	  2.5
1960	BRN	 1.3	  3.3
1961	BFA	 0.3	  3.7
</code>


```sql
%%sql
/* Enter your SQL query below */


```

<div class="exercise"><b>Exercise 8:</b></div> 

Write a query to find all distinct country codes that appear in the `indicators` table, ordered in reverse alphabetically order.  Limit your results to five rows.

The output from my solution is:<br>
<code>
code
ZWE
ZMB
ZAF
YEM
XKX
</code>


```sql
%%sql
/* Enter your SQL query below */


```

<div class="exercise"><b>Exercise 9:</b></div> 

Write a query to find all the countries that *end* with `'Islands'` as a suffix in the `countries` table.  Project only the `country` and `region` fields. 

The output from my solution is:<br>
<code>
country	                 region
Channel Islands	         Europe & Central Asia
Cayman Islands	          Latin America & Caribbean
Faroe Islands	           Europe & Central Asia
Marshall Islands	        East Asia & Pacific
Northern Mariana Islands    East Asia & Pacific
Solomon Islands	         East Asia & Pacific
Turks and Caicos Islands    Latin America & Caribbean
British Virgin Islands	  Latin America & Caribbean
</code>


```sql
%%sql
/* Enter your SQL query below */


```

<div class="exercise"><b>Exercise 10:</b></div> 

With regards to the `countries` table, write a query to find all the regions that contain the word `'East'` (anywhere in the `region` field).  Project only the `country` and `region` fields and sort by `country`.  Limit your results to five records.

The output from my solution is:<br>
<code>
country	       region
Algeria	       Middle East & North Africa
American Samoa	       East Asia & Pacific
Australia	            East Asia & Pacific
Bahrain	       Middle East & North Africa
Brunei Darussalam        East Asia & Pacific
</code>


```sql
%%sql
/* Enter your SQL query below */


```

<div class="exercise"><b>Exercise 11:</b></div> 

With regards to the `indicators` table, project the `year`, `code`, `gdp`, `imports`, and `exports` fields, and create a new (Boolean) column named `new` that that indicates whether `exports` are larger than `imports`.  Sort by `exports` in descending order and limit the results to 10 rows.

The output from my solution is:<br>
<code>
year	code	gdp	   imports	  exports	new
2014	CHN	10438.5	1963110.0	2343220.0	1
2015	CHN	11015.5	1601760.0	2280540.0	1
2017	CHN	12143.5	1832130.0	2280090.0	1
2013	CHN	9570.41	1949300.0	2210660.0	1
2016	CHN	11138.0	1589460.0	2136590.0	1
2012	CHN	8532.23	1817340.0	2050090.0	1
2011	CHN	7551.5 	1741430.0	1899280.0	1
2014	USA	17521.8	2347680.0	1620480.0	0
2010	CHN	6087.16	1393910.0	1578440.0	1
2013	USA	16784.8	2268370.0	1578430.0	0
</code>


```sql
%%sql
/* Enter your SQL query below */


```

<div class="exercise"><b>Exercise 12:</b></div> 

With regards to the `topnames` table, select all rows where the top name is John.  Project all columns and sort by year in descending order. Limit the results to five rows.

The output from my solution is:<br>
<code>
year	sex	 name	count
1923	Male	John	57470
1922	Male	John	57277
1921	Male	John	58217
1920	Male	John	56913
1919	Male	John	53528
</code>


```sql
%%sql
/* Enter your SQL query below */


```

<div class="exercise"><b>Exercise 13:</b></div> 

With regards to the `topnames` table, select all rows corresponding to males who's name is not John nor Michael.  Project all columns and sort by year in descending order. Limit the results to five rows.

The output from my solution is:<br>
<code>
year	sex	 name	count
2018	Male	Liam	19837
2017	Male	Liam	18798
2016	Male	Noah	19117
2015	Male	Noah	19635
2014	Male	Noah	19305
</code>


```sql
%%sql
/* Enter your SQL query below */


```

<div class="exercise"><b>Exercise 14:</b></div> 

With regards to the `indicators` table, select all rows for which the GDP is missing and the population is greater than 140 million.  Project `year`, `code`, `gdp`, and `pop` for such rows and sort by year in ascending order.  No need to limit results.


The output from my solution is:<br>
<code>
year	code   gdp     pop
1982	RUS	None	140.82
1983	RUS	None	141.67
1984	RUS	None	142.74
1985	RUS	None	143.86
1986	RUS	None	144.89
1987	RUS	None	145.91
</code>


```sql
%%sql
/* Enter your SQL query below */


```
