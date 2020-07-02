+++
title = "SQL Notes"
menutitle = "SQL Notes"
description = "Notes for Basic SQL stuff"
weight = 1
+++

# SQL Basics

What is a database exactly?
To put it simply, it’s a computer program which stores various data. There are quite a few database vendors, e.g., Oracle, MySQL, PostgreSQL, SQL Server, and many others.

There are various types of databases. In this course, we’re going to focus on relational databases - they’re a very frequent choice in the contemporary IT world.

## ***Relational Databases***:

Every relational database stores information in **tables**. You can have many tables in one database and each of your tables will hold data which refers to similar objects. Each tables has a **name**. So you can find out what kind of information is stored there.

For example, the database of your university would include a table named `student`, with all data regarding students, another table `subject` with information on the subjects at your university, etc.

Tables in databases look _exactly_ the way you would imagine a normal table - they have **columns** and **rows**.

Columns in every table have their **names** and they identify the kind of information is stored in them.

Each row stores information about one object. In the `student` table below, you can see that the column names reflect the kind of data contained in them, so in the column `name` there are names of students, in the columns `graduation_year` there is the year of their graduation, etc.

Each **row** corresponds to exactly _one_ student.

[ Insert table here ] 

## ***Notation***:

Lets use the notation:

`pet (id, name, owner_id)`

The above means that we have a table named `pet` which has the following columns: `id`, `name`, and `owner_id`. This information will be enough for you to work with the tables in our exercise.

## ***SQL***:

So, how do we get in touch with our database? We use the so-called **Structured Query Language**. Of course, no one uses the full name, we just call it SQL for short.

All relational databases understand SQL, but each of them has a slightly different _dialect_, so to speak.

Thanks to SQL, you’ll be able to make queries in each database environment.

### Queries

Just as the name suggests, queries are questions that we ask to find out some information about the data stored in the database.

Databases can do amazing things - they don’t only return the data you ask for, they can actually do advanced calculations on the tables. You’ll see for yourself!

### Coding

```

SELECT *
FROM user;

```

`SELECT` tells your databases that you want to select data. `FROM user` tells the database to select data from the table `user`.

Finally, the asterisk `(*)` tells the database you want to see **all columns** in this table.

Remember that it’s good practice to always end your SQL command with a semicolon `(;)`. A semicolon is like a period at the end of the sentence. It tells the database that you’re done with your command.

### Filtering Data

#### Conditional Operators

- `OR`

- `AND`

- `BETWEEN`
    - Always check how `BETWEEN` works

- `NOT`

We can also include even more conditions by using **parentheses**, according to our needs.

- `LIKE`
    - Allows for the use of the percentage sign `%`

- `NOT NULL`
    - There can be `NULL` values, I.e. fields with unknown, missing values.
    - To check whether a column has a value, we use a special instruction `IS NOT NULL`.

If you’re looking for null values…

- `IS NULL`

Remember, `NULL` is a special value. It means that some piece of information is **missing** or **unknown**.

_Also, `NULL = NULL` is NEVER true in SQL!_

#### Mathematical Operators

You can:

- Add (`+`)

- Subtract (`-`)

- Multiply (`*`)

- Divide (`/`)

### Multiple Tables

In big databases we always use **multiple tables**. This also means that we often want to get data from more than one table at a time.

#### Joining results from multiple tables

Say we have two tables:

```

Director (id, name, birth_year);

Movie (id, title, production_year, director_id)

```

If we want data from both tables, we can simply do:

```

SELECT *
FROM movie, director;

```

How would the data be presented? There’s 8 movies, and 5 directors. Will it be 5? 8? Or will it get added together to be 13?

Thing is, none of those numbers are correct, we actually get **40 rows**. The numbers multiply, _8 * 5 = 40_. This is because SQL takes every single movie and joins it with every possible director.

In other words, SQL doesn’t know what to do with the results from the two tables, so it gave you every possible connection. 

How can we change it? Take a look:

```

/* Select everything from the database(s) */
SELECT *

/* Data from certain one or more databases */
FROM movie, director

/* Filter our responses, in this case, we merge related data so it doesn’t get bloated */
WHERE movie.director_id = director.id;

```

If you have multiple tables, you should refer to specific columns by giving the name of the table and the column, separated by a (`.`). As a result, the column `director_id` from the table `movie` becomes `director.id` and so on.

Now the results look so much better! Joining multiple tables is such a popular and frequent operation that SQL provides a special word for it: `JOIN`. There are many versions of `JOIN` out there. For the time being, we’ll focus on the basic one.

SQL must also know how to join the tables, so there is another keyword `ON`. After it, we set our condition: join only those rows where the `id` in `director` is the same as `director_id` in `movie`.

The code:

```

SELECT *
FROM movie /*  We only select one table called movie, because we’ll JOIN it onto the director table */
JOIN director ON movie.director_id = director.id;

```

Rather than selecting everything now, lets say we select only a few columns. Here’s the code:

```

/* “Filtering” out our results.  */
SELECT director.name,
	movie.title

/* Selecting only one table so that we can choose another to JOIN with */
FROM movie

/* We are still joining the tables together */
JOIN director
ON movie.director_id = director.id;

```

#### Omitting table names

All together, these are good practices, but you only _need_ to do it when there’s _a chance of confusing them_. 

If there are two different columns with the same name in two different tables, then you have to specify the tables. If the name of the column is unique, though, you may omit the table name.

Like in this code:

```

SELECT name,
	title
FROM movie
JOIN director
ON director.id = movie.director_id;

```

#### Renaming Columns

Look at this code:

```

SELECT
	director.id AS director_id,
	movie.id AS movie_id
FROM movie
JOIN director
	ON director.id = movie.director_id;

```

After the column name, e.g. `director.id`, we use the new keyword `AS` and we put the new name after it (`director_id`). We can repeat this process with every column.

The new name is just an **alias**, which means it’s temporary and doesn’t change the actual column name in the database. It only influences the way the column is shown in the result of the specific query.

This technique is often used when there are a few columns with the same name coming from different tables. Normally, when SQL displays columns in the result, there is no information about the table that a specific column in part of.

#### Filtering the joined tables

Code:

```

SELECT *
FROM movie
JOIN director
ON movie.director_id = director.id
WHERE movie.production_year > 2000;

```

You can see, we just used `WHERE` again. Pretty simple. But, since we’re dealing with multiple tables, we specify it with `movie.production_year`. Although, it is quite unique to the movie table, that we can just omit the table name `movie`.

#### Strings

Example Code:

```

SELECT *
FROM movie
JOIN director
   ON director.id = movie.director_id
WHERE director.name = ’Steven Spielberg’;

```

Filtering with Strings.

#### Quick fun example

Here’s a fun problem you can try doing. Try it out, then look at the answers. Or… well don’t. 

Select the `title` and `production_year` columns from the `movie` table, and the `name` and `birth_year` columns from the `director` table in such a way that a movie is shown together with its director.
Show the column `birth_year` as `born_in`. Select only those movies which were filmed when their director was younger than 40 (i.e. the difference between `production_year` and `birth_year` must be less than 40).

Your final code should look something like this:  ```

SELECT title,
	      production_year,
	      name,
	      birth_year AS born_in
FROM movie
JOIN director
   ON director.id = movie.director_id
WHERE (production_year - birth_year) < 40;

```

#### Another fun example

Select the `id`, `title`, and `production_year` columns from the `movie` table, and the `name` and `birth_year` columns from the `director` table in such a way that a movie is shown together with its director. Show the column `birth_year` as `born_in` and the column `production_year` as `produced_in`. Select only those movies:
- _Whose title contains a letter 'a' and which were filmed after 2000_, or
- _Whose director was born between 1945 and 1995_.

Your final code should look something like this:

```

SELECT title,
	   production_year AS produced_in,
       movie.id,
       name,
       birth_year AS born_in
FROM movie
JOIN director
  ON director.id = movie.director_id
WHERE (title LIKE '%a%' AND production_year > 2000) 
  OR (birth_year BETWEEN 1945 AND 1995);

```