# Lighthouse Labs | SQL Intro

Ressources
- https://www.codecademy.com/article/sql-commands
- https://www.geeksforgeeks.org/postgresql-psql-commands/
- https://www.postgresql.org/docs/current/datatype.html
- https://www.w3schools.com/sql/sql_update.asp

* [] Introduction
    - Introduction Store 3 WAYS (ask for app idea/example?)
        - array/object (local)
        - json (local)
        - database (external)
    - Pros/Cons Local vs External
* [] Database
    - Explanation (Drawing Client-Server)
    - 2 Types (SQL vs noSQL):
* [] PostgreSQL (Word database)
    - Command Terminal: \dt, \l, 
    - Crud: Select, Create, Insert, Alter, Delete, Drop

    *BREAK* 

    - Add Ons: Where, Limit, Offset, Join (Outer, Inner, Left, Right)



# Class Notes

```js
./ --> inside current folder
../ --> outisde current folder

cd [folderName] --> inside folder
cd ..  -> outside folder
```

# Pros (Local)
- Instant Access
- No connection needed to access it
- Access from anywhere
- Security since its local
- Seperation of Concerns


# Cons (Local)
- Running out of Space on computer
- Really Hard to share data with others
- Hard to access elsewhere
- Javascript is not specialized in data storage

# Databases

* 2 Types
* SQL vs NoSQL
* Relational vs Non-Relational
* Tables vs Objects

SQL: 

Movies
|id|movieName    |movieGenre|yearReleased|
|--|-------------|----------|------------|
|0 |Step Brothers|Comedy    |  2005      |
|1 |Scarface     |Action    |  1990      |

- mySQL
- PostgreSQL *****
- Cassandra
- MariaDB

NoSQL:

```js
const Movies = [
    {
        id: 0, 
        movieName: "Step Brothers", 
        movieGenre: "Comedy", 
        yearReleased: 2005
    },
    {
        id: 1, 
        movieName: "Scarface", 
        movieGenre: "Action", 
        yearReleased: 1990
    },
]
```

- MongoDB
- Couchbase
- Apache

# Command Terminal 

/l --> allows you to see all the databases 
/dt -> allows you to see all the tables in your database
/d [table name] -> allows you to get more details on a a specific table "table name"

CRUD Commands

Create
Read/Retrieve
Update 
Delete


- Select
```js
SELECT [column_name] FROM [table_name]
SELECT email FROM users
SELECT * FROM users 
```

- Create
```js
CREATE TABLE table_name (
  column_1 datatype, 
  column_2 datatype, 
  column_3 datatype
);

CREATE TABLE movies (
    id SERIAL PRIMARY key, 
    movieName TEXT, 
    movieGenre TEXT, 
    directorId INTEGER
);

CREATE TABLE director (
    id SERIAL PRIMARY key, 
    directorName TEXT
);
```

- Insert
```js
INSERT INTO table_name (column_1, column_2, column_3) 
VALUES (value_1, 'value_2', value_3);

INSERT INTO movies (id, movieName, movieGenre, directorId) 
VALUES (2, 'Notebook', 'Romance', 1),
(3, 'Pursuit of Happiness', 'Coming Of Age', 2);

INSERT INTO director (id, directorName) 
VALUES (0, 'Bobby'),
(1, 'Mr.Potato'),
(2, 'Spongebob');

INSERT INTO movies (id, movieName, movieGenre, directorId) 
VALUES (4, 'Blades Of Glory', 'Comedy', 10),
(5, 'Titanic', 'Action', 20);

INSERT INTO director (id, directorName) 
VALUES (5, 'Sakhia');
```

- Alter
```js
ALTER TABLE table_name 
ADD column_name datatype;

ALTER TABLE movies
ADD director TEXT;
```

- Update
```js
UPDATE [table_name]
SET [column_name] = [column_value]
WHERE [id] = value;

UPDATE movies
SET director = 'Alfred Schmidt';
```


- Delete
```js
DELETE FROM table_name
WHERE some_column = some_value;

DELETE FROM movies
// WHERE some_column = some_value;
```

- Drop
```js
DROP TABLE table_name;

DROP TABLE movies;
```

- Inner
```js
SELECT column_name(s)
FROM table_1
JOIN table_2
  ON table_1.column_name = table_2.column_name;

SELECT *
FROM movies
JOIN director
  ON movies.directorid = director.id;
```

- Left 

```js
SELECT column_name(s)
FROM table_1
LEFT JOIN table_2
  ON table_1.column_name = table_2.column_name;

SELECT *
FROM movies
LEFT JOIN director
  ON movies.directorid = director.id;
```

- Right

```js
SELECT column_name(s)
FROM table_1
RIGHT JOIN table_2
  ON table_1.column_name = table_2.column_name;

SELECT *
FROM movies
RIGHT JOIN director
  ON movies.directorid = director.id;
```

Add Ons
- Where
```js
SELECT * FROM movies
WHERE movieName = 'Scarface';
```

- Limit 
```js
SELECT * FROM movies
LIMIT 3;
```