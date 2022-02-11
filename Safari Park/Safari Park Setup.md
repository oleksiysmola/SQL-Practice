# Safari Park - Tasks

Each of the questions/tasks below can be answered using a `SELECT` query. When you find a solution copy it into the code block under the question before pushing your solution to GitHub.

1) Select all animals from a particular pen.

```sql
<!-- Copy solution here -->
SELECT name FROM animal WHERE enclosure_id = 1; 

```

2) Join staff and enclosure tables through the assignments table

```sql
<!-- Copy solution here -->
SELECT enclosure.name, staff.name
FROM enclosure 
INNER JOIN assignments ON assignments.enclosure_id = enclosure.id
INNER JOIN staff ON staff.id = assignments.employee_id;

```

3) The names of the staff working in a given enclosure?

```sql
<!-- Copy solution here -->
SELECT staff.name
FROM enclosure 
INNER JOIN assignments ON assignments.enclosure_id = enclosure.id
INNER JOIN staff ON staff.id = assignments.employee_id
WHERE enclosure.name = 'bearpen';
```

4) The names of staff working in enclosures which are closed for maintenance

```sql
<!-- Copy solution here -->
SELECT enclosure.name, staff.name
FROM enclosure 
INNER JOIN assignments ON assignments.enclosure_id = enclosure.id
INNER JOIN staff ON staff.id = assignments.employee_id
WHERE closed_for_maintenance = TRUE;


```

5) The name of the enclosure where the oldest animal lives. If there are two animals who are the same age choose the first one alphabetically.
```sql
<!-- Copy solution here -->
SELECT enclosure.name, animal.name FROM animal
INNER JOIN enclosure ON enclosure.id = animal.enclosure_id
WHERE animal.age = (SELECT MAX (animal.age) FROM animal)
ORDER BY animal.name ASC;

```

6) How many different teams have played in matches recorded in a French division?

```sql
<!-- Copy solution here -->


```

7) Have Huddersfield played Swansea in the period covered?

```sql
<!-- Copy solution here -->


```

8) How many draws were there in the Eredivisie between 2010 and 2015?

```sql
<!-- Copy solution here -->


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