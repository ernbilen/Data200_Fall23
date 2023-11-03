# Data 200: Data Systems for Data Analytics


# Homework 6: Inner and Outer Joins in SQL


<font color='red'>**Due Date:** November 9 beginning of class. </font>
---
Enter your name in the markdown cell below.

# Name:

# Tasks

- **Make sure you have installed SQL Magic before beginning.**
- Review pages 356-368 in Bressoud & White textbook.
- Commit and push your completed `.ipynb` and `.md` files

# Exercises

This homework will make use of the`school.db` database, which is available under `/data` folder on course Github page. I suggest that you review pages 225-227 in the Course Notes to familiarize yourself with the tables in this database.  You may also want to open the `school.db` database in SQLite Studio to examine the tables as you work on the queries below, or run

<!---
SELECT name FROM sqlite_master
WHERE type='table'
-->

**Load the `school.db` database which is already in the same directory as this notebook.**

**Then, run the code cells below to load the SQL Magic module and connect to the `school.db` database.**


```python
%load_ext sql
```


```python
%sql sqlite:///school.db
```

<div class="exercise"><b>Exercise 1:</b></div> 

Write a query to obtain the department chairs for Modern Language (`'LANG'`), Philosophy (`'PHIL'`), and Mathematics and Computer Science (`'MATH'`).  Return the department name, the chair's last name, and the chair's first name.

Below is the output from my solution:<br>
<code>
departmentname	              instructorlast	instructorfirst
Modern Language	             Brown	         Danielle
Mathematics & Computer Science  Bradley       	Betty
Philosophy	                  Singhal	       Aarav
</code>


```sql
%%sql

/* Enter your SQL query below */


```

<div class="exercise"><b>Exercise 2:</b></div> 

Write a query to list all of the students who are mathematics (`'MATH'`) majors.  Include the student's last and first name, along with the name of the department.  Order the results by last name, first name.  Limit the results to 6 rows.

Below is the output from my solution:<br>
<code>
studentlast	studentfirst	subjectname
Barnett	    Larry	       Mathematics
Campbell	   Gloria	      Mathematics
Chapman	    Robert	      Mathematics
Colombo	    Giulia	      Mathematics
Davis	      Crystal	     Mathematics
Edwards    	Gary	        Mathematics
</code>


```sql
%%sql

/* Enter your SQL query below */


```

<div class="exercise"><b>Exercise 3:</b></div> 

Write a query to list all of the students who are taking Math 123-03 in the fall (this corresponds to `classid=40326`). Please use a `USING` clause on `studentid` (to give you practice with it).  Order the results by last name, first name.  Limit the results to 6 rows.  

Below is the output from my solution:<br>
<code>
studentlast	studentfirst
Brewer	     Scott
Castillo	   Stephen
Chapman	    Robert
Coleman	    Billy
Dunn	       Diane
Fox	        Luke
</code>


```sql
%%sql

/* Enter your SQL query below */


```

<div class="exercise"><b>Exercise 4:</b></div> 

Write a query to find which instructors (last and first names) are teaching in the spring semester.  Your result should not contain any duplicates.  Order the results by last name, first name.  Limit the results to 10 rows.

Below is the output from my solution:<br>
<code>
instructorlast	instructorfirst
Aguilar	       Stephen
Anderson	      Philip
Arnaud	        Antoine
Austin	        Stephanie
Bailey	        Jayden
Balasubramanium   Hemant
Balasubramanium   Vishal
Banks	         Carolyn
Banks	         David
Barnes   	     Deborah
</code>


```sql
%%sql

/* Enter your SQL query below */


```

<div class="exercise"><b>Exercise 5:</b></div> 

Write a query to list all courses (subject and number) that were *not* taught in either the fall or spring semesters.  **Hint:** Recall that LEFT JOIN can be used to compute *set differences*.  In particular, you will need to use a left join of the `courses` and `classes` tables.  Furthermore, in order to match up the course subject and number, you may want to use `USING (coursesubject, coursenum)`. Order your results by the course subject and limit your results to six rows.

The output from my solution is:<br>
<code>
coursesubject	coursenum
ARTH	         363
ARTH	         452
BIOL	         363
BIOL	         364
BLST	         265
BLST	         361
</code>


```sql
%%sql

/* Enter your SQL query below */


```

<div class="exercise"><b>Exercise 6:</b></div> 

Write a query to find all English courses (subject, number, and title) that were *not* offered in either the fall or spring semesters.  *This is very similar to the previous exercise*.

The output from my solution is:<br>
<code>
coursesubject	coursenum	coursetitle
ENGL	         340	      Contemporary Drama
ENGL	         349	      Studies in European Lit
</code>


```sql
%%sql

/* Enter your SQL query below */


```

<div class="exercise"><b>Exercise 7:</b></div> 

Write a query to list instructors (first and last names) and the *number of students* they taught during the year (both fall and spring semesters).  Only include instructors who were actually teaching.  Please name the new column `total_taught` and order your results from smallest to largest.  Limit the results to 10 rows. **Hint:** You will need to join three different tables and use a GROUP BY to accomplish this task.

The output from my solution is:<br>
<code>
instructorfirst	instructorlast	total_taught
Margaux	        Gillet            1
Lisa	           Fuller	        1
Bobby	          Hall	          1
Harrison	       Gray	          1
Aarav	          Jhadav	        2
Kyle	           Stevens	       4
Rose	           James	         5
Philip	         Anderson	      7
Paul	           Dixon	         7
Michelle	       Young	         8
</code>


```sql
%%sql

/* Enter your SQL query below */


```

<div class="exercise"><b>Exercise 8:</b></div> 

Note that in the last exercise we learned that the instructor Kyle Stevens only taught a total of 4 students during the year (which is strange--let's investigate).  Write a query to list the student IDs of these four students, along with the course subject, course number, and course title.  **Hint 1:** In my solution, I joined together five different tables (using four INNER JOIN statements)!  **Hint 2:** You may want to first see if you can list the course subject, course number, and student ID.  Then join the fifth table to get the course title.  That is, sometimes it's easier to build your query in stages to make it more manageable.

The output from my solution is (we can see that Kyle only taught senior research and directed studies):<br>
<code>
coursesubject	coursenum	coursetitle	   studentid
BIOL	         452	      Senior Research   61724
BIOL	         451	      Senior Research   61724
BIOL	         362	      Directed Study    62419
BIOL	         362	      Directed Study    62925
</code>


```sql
%%sql

/* Enter your SQL query below */


```
