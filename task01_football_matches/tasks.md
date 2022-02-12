# Football Matches - Tasks

Each of the questions/tasks below can be answered using a `SELECT` query. When you find a solution copy it into the code block under the question before pushing your solution to GitHub.

1) Find all the matches from 2017.

```sql
<!-- Copy solution here -->
SELECT * FROM matches WHERE season = 2017;

```

2) Find all the matches featuring Barcelona.

```sql
<!-- Copy solution here -->
SELECT * FROM matches WHERE hometeam = 'Barcelona' OR awayteam = 'Barcelona';

```

3) What are the names of the Scottish divisions included?

```sql
<!-- Copy solution here -->
SELECT * FROM divisions WHERE country = 'Scotland';
 id | code |         name          | country  
----+------+-----------------------+----------
 16 | SC0  | Scottish Premiership  | Scotland
 17 | SC1  | Scottish Championship | Scotland
 18 | SC2  | Scottish League One   | Scotland
(3 rows)
```

4) Find the division code for the Bundesliga. Use that code to find out how many matches Freiburg have played in the Bundesliga since the data started being collected.

```sql
<!-- Copy solution here -->
SELECT code FROM divisions WHERE name = 'Bundesliga';
 code 
------
 D1
(1 row)
SELECT COUNT(*) FROM matches WHERE division_code = 'D1' AND 'Freiburg' IN (hometeam, awayteam) IS TRUE;
 count 
----------------------
  374
(1 row)


```

5) Find the unique names of the teams which include the word "City" in their name (as entered in the database)

```sql
<!-- Copy solution here -->
SELECT DISTINCT hometeam FROM matches WHERE hometeam LIKE '%City%';
 hometeam
------
 Bath City
 Man City
 Edinburgh City
 Bristol City
(4 rows)

```

6) How many different teams have played in matches recorded in a French division?

```sql
<!-- Copy solution here -->
SELECT * FROM divisions WHERE country = 'France';
 id | code |         name          | country  
----+------+-----------------------+----------
 9  | F1   | Ligue 1               | France
 10 | F2   | Ligue 2               | France
(2 rows)
SELECT COUNT(DISTINCT awayteam) FROM matches WHERE division_code IN ('F1', 'F2') IS TRUE;
 count 
----------------------
  61
(1 row)
```

7) Have Huddersfield played Swansea in the period covered?

```sql
<!-- Copy solution here -->
SELECT * FROM matches WHERE ('Huddersfield' IN (hometeam, awayteam)) AND ('Swansea' IN (hometeam, awayteam))  IS TRUE;

```

8) How many draws were there in the Eredivisie between 2010 and 2015?

```sql
<!-- Copy solution here -->
SELECT COUNT(*) FROM matches 
WHERE division_code = (SELECT code FROM divisions WHERE name = 'Eredivisie') 
AND ftr = 'D' AND (season BETWEEN 2010 AND 2015);
 count 
----------------------
  431
(1 row)

```

9) Select the matches played in the Premier League in order of total goals scored from highest to lowest. Where there is a tie the match with more home goals should come first.

```sql
<!-- Copy solution here -->


```

10) In which division and which season were the most goals scored?

```sql
<!-- Copy solution here -->


```

### Useful Resources

- [Filtering results](https://www.w3schools.com/sql/sql_where.asp)
- [Ordering results](https://www.w3schools.com/sql/sql_orderby.asp)
- [Grouping results](https://www.w3schools.com/sql/sql_groupby.asp)