
#Database Indices
We have an `ingredients` database consisting of millions of ingredient records and we want all the rows of ingredients that have Brussels Sprouts in them, but querying them is taking forever. Database indices to the rescue!

##SQL queries used
```
EXPLAIN ANALYSE
SELECT * FROM ingredients WHERE name = 'Brussels sprouts';

EXPLAIN ANALYSE
SELECT COUNT(*) FROM ingredients WHERE name = 'Brussels sprouts';

EXPLAIN ANALYSE
SELECT * FROM ingredients WHERE name = 'Brussels sprouts' AND unit = 'gallon(s)';

EXPLAIN ANALYSE
SELECT * FROM ingredients WHERE unit = 'gallon(s)' AND (name = 'Brussels sprouts' OR name LIKE '%j%');

CREATE INDEX ON ingredients(name);
```

##Without Indexing
![Without Indexing](https://dl.dropboxusercontent.com/u/87789399/Launch%20Academy/Screen%20Shot%202015-11-26%20at%201.58.23%20PM.png)

##With Indexing
![With Indexing](https://dl.dropboxusercontent.com/u/87789399/Launch%20Academy/Screen%20Shot%202015-11-26%20at%202.36.14%20PM.png)
