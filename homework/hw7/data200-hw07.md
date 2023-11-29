# Data 200: Data Systems for Data Analytics


# Homework 7: Regex and API

**Dickinson College**<br/>
Prof. Eren Bilen<br/>
<font color='red'>**Due Date:** Dec 5 beginning of class </font>
---
Enter your name in the markdown cell below.

# Name:

# Tasks

- Review the notes posted on Github on regular expressions and API.
- Review pages 103-128 in Bressoud & White textbook on regular expressions.
- Review the TMDB API documentation on https://developers.themoviedb.org/3/getting-started/introduction
- Commit and push your completed `.ipynb` and `.md` files


```python
import re
```

# Exercises: Regex

Let's practice using regular expressions.

<div class="exercise"><b>Exercise 1:</b></div> 

Write regex to return all numbers in the text below

```Speed of light in vacuum is 299792458 m/s. Standard atmosphere 101325 Pa.```

Below is the output from my solution:<br>
<code>
['299792458', '101325']
</code>


```python

```

<div class="exercise"><b>Exercise 2:</b></div> 

Write regex to return the numbers in the text below

```Circumference to diameter ratio is 3.141592. Gas constant 8.3144621 J/mol*K.```

Below is the output from my solution:<br>
<code>
['3.141592', '8.3144621']
</code>


```python

```

<div class="exercise"><b>Exercise 3:</b></div> 

Write regex to return the numbers in the text below, including its unit of measurement.

```Earth to Sun distance is 149600000 km. Earth to Mars distance is 54600000 km.``

Below is the output from my solution:<br>
<code>
['149600000 km', '54600000 km']
</code>


```python

```

<div class="exercise"><b>Exercise 4:</b></div> 

Write regex to return all years in the text below

```1 The Shawshank Redemption (1994)
2 The Godfather (1972)
3 The Godfather: Part II (1974) 
4 Pulp Fiction (1994) 
5 The Good, the Bad and the Ugly (1966) 
6 The Dark Knight (2008) 
7 12 Angry Men (1957) 
8 Schindler's List (1993)
9 The Lord of the Rings: The Return of the King (2003) 
10 Fight Club (1999)```

Below is the output from my solution:<br>
<code>
['1994',
 '1972',
 '1974',
 '1994',
 '1966',
 '2008',
 '1957',
 '1993',
 '2003',
 '1999']
</code>


```python
text = "1 The Shawshank Redemption (1994)\
2 The Godfather (1972)\
3 The Godfather: Part II (1974) \
4 Pulp Fiction (1994) \
5 The Good, the Bad and the Ugly (1966) \
6 The Dark Knight (2008) \
7 12 Angry Men (1957) \
8 Schindler's List (1993)\
9 The Lord of the Rings: The Return of the King (2003) \
10 Fight Club (1999)"
```


```python

```

<div class="exercise"><b>Exercise 5:</b></div> 

It is generally not recommended to parse html with regex, (BeautifulSoup package is designed just for parsing html and does it much more efficiently) but let's practice anyway in case you find yourself in a situation where regex is needed.

Write regex to return the title in the html text below:


```python
text = "\\n<!DOCTYPE html>\\n<html>\\n<head>\\n<title>This is a title</title>\\n</head>\\n<body>\\n<p1>Hello world!</p1>\\n<p2>Hello world again</p2>\\n</body>\\n</html>\\n"
```

Below is the output from my solution:<br>
<code>
'This is a title'
</code>


```python

```

<div class="exercise"><b>Exercise 6:</b></div> 

Write regex to return the content body of the website contained in the same html `text` above from Exercise 5. *Hint: Use () in your regex syntax to access inside of the html tags. Hint2: There are many ways of approaching this problem. My solution uses nested regex code.

Below is the output from my solution:<br>
<code>
['Hello world!', 'Hello world again']
</code>


```python

```

# Exercises: API

Please go to https://developers.themoviedb.org/3/getting-started/introduction and create a free account. Using your free account, get an API key. With your unique API key, you will be able to send requests to TMDB for data retrieval. Review the API documentation on "/discover/movie" at https://developers.themoviedb.org/3/discover/movie-discover


```python
import requests
import pandas as pd
```

<div class="exercise"><b>Exercise 7:</b></div> 

Return the 10 highest rated movies (according to `vote_average`) in 2021 that have received more than 5000 votes (according to `vote_count`). Return `title`, `vote_average`, and `vote_count` *Hint: insert the filter requests to your API query*.


Below is the output from my solution. *Note that your results might be slightly different, since there may have been new votes casted since this notebook was created.* <br>
<code>
                          title  vote_average  vote_count
0  Zack Snyder's Justice League           8.2        8356
1                        Nobody           8.1        5244
2                       Cruella           8.1        7699
3       Spider-Man: No Way Home           8.0       15948
4      Raya and the Last Dragon           8.0        5717
5              The Tomorrow War           7.9        5984
6                          Luca           7.9        6877
7                          Dune           7.8        8014
8             Godzilla vs. Kong           7.7        8380
9                       Encanto           7.7        7614
</code>


```python

```

<div class="exercise"><b>Exercise 8:</b></div> 

Return the 10 highest rated movies (according to `vote_average`) that were released between 1980 and 2023 and have received more than 5000 votes (according to `vote_count`). Return `title`, `vote_average`, `vote_count`, and `year` *Hint: Use a combination of filtering via API request and filtering via Pandas.*.


Below is the output from my solution. *Again, your results might be slightly different.*<br>
<code>
                      title  vote_average  vote_count  year
0  The Shawshank Redemption           8.7       22733  1994
1          Schindler's List           8.6       13478  1993
2              Pulp Fiction           8.5       24112  1994
3         Life Is Beautiful           8.5       11477  1997
4                  Parasite           8.5       14772  2019
5              Forrest Gump           8.5       23659  1994
6                GoodFellas           8.5       10698  1990
7            The Green Mile           8.5       14667  1999
8             Spirited Away           8.5       13592  2001
9                Your Name.           8.5        9255  2016
</code>


```python

```

<div class="exercise"><b>Writing in Discipline (WiD) Assignment:</b></div> 

The SQL Murder Mystery is a fun story based game experience where you use SQL code and a careful inspection of a relational database structure to solve a murder mystery: https://mystery.knightlab.com

Please go ahead and give the game a try. Feel free to use the walkthrough if you get stuck on any part of it.

Your assignment is to write your own "story" where your story includes an event where its details could be traced in a relational database, much like the SQL Murder Mystery's story. Please feel free to be creative! After you turn in your WiD assignment, I will give you my feedback, and you will resubmit an updated version which then will be included in your WiD portfolio. Note that you have to complete this assignment even if you are not a Data Analytics Major. Please make sure your story is 500 words minimum. Feel free to use a relational database schema you construct "by hand" or a description of a sentient webscraper and all that sort. Good luck, and I look forward to reading your stories.

Note that the cell below is already Markdown, so you can write your story as Markdown below. In addition to writing it below, please also upload it to your WID repository (both versions before and after editing) which you can access at https://forms.office.com/Pages/ResponsePage.aspx?id=VbAyYrl2E0ybiLVirn22-8NaUHs-9y9AnrNpzWbacKxUNTdFQlRHM1RPVFVFUERRWDZSQ0xJUjA1WC4u

Note that the WID repo does not take in .md output, so you need to convert your .md to something like .pdf. The following website is my favorite online markdown editor that lets you export out pdf: https://dillinger.io


