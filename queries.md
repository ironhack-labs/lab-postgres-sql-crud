![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# Answers

## Iteration 2

**1. Add the `solid` and `chartjs` libraries as new rows to the `jslibraries` table.**

<!-- Your Query Goes Here -->
```sql
 INSERT INTO jslibraries(name, owner, description, stars, url, releases, licence, used_by, contributors, main_technology, type, release_date)
VALUES
  ('solid', 'solidjs', 'A declarative, efficient, and flexible JavaScript library for building user interfaces.', 10700, 'solidjs.com', 194, 'MIT License', 624, 73, 'typescript', 'UI Library', '2011-08-13'),
  ('chartjs', 'chartjs', 'Simple HTML5 Charts using the canvas tag.', 54700, 'chartjs.org', 85, 'MIT License', 414000, 377, 'javascript', 'Charts Library', '2011-11-02');



name   |  owner  |                                       description                                       | stars |     url     | releases |   licence   | used_by | contributors | main_technology |      type      | release_date 
---------+---------+-----------------------------------------------------------------------------------------+-------+-------------+----------+-------------+---------+--------------+-----------------+----------------+--------------
 solid   | solidjs | A declarative, efficient, and flexible JavaScript library for building user interfaces. | 10700 | solidjs.com |      194 | MIT License |     624 |           73 | typescript      | UI Library     | 2011-08-13
 chartjs | chartjs | Simple HTML5 Charts using the canvas tag.                                               | 54700 | chartjs.org |       85 | MIT License |  414000 |          377 | javascript      | Charts Library | 2011-11-02
(2 rows)

```


<br>

**2. Get all the fields of the library that was released earliest (first).**

<!-- Your Query Goes Here -->

```sql

SELECT * FROM jslibraries ORDER BY release_date ASC LIMIT 1;



name  |  owner  |                                       description                                       | stars |     url     | releases |   licence   | used_by | contributors | main_technology |    type    | release_date 
-------+---------+-----------------------------------------------------------------------------------------+-------+-------------+----------+-------------+---------+--------------+-----------------+------------+--------------
 solid | solidjs | A declarative, efficient, and flexible JavaScript library for building user interfaces. | 10700 | solidjs.com |      194 | MIT License |     624 |           73 | typescript      | UI Library | 2011-08-13
(1 row)
```

<br>

**3. Get all the fields of the library that was released most recently (last).**

<!-- Your Query Goes Here -->
```sql
SELECT * FROM jslibraries ORDER BY release_date DESC LIMIT 1;


 name    |   owner   |                                description                                | stars |      url      | releases |   licence   | used_by | contributors | main_technology |        type        | release_date 
-----------+-----------+---------------------------------------------------------------------------+-------+---------------+----------+-------------+---------+--------------+-----------------+--------------------+--------------
 chakra-ui | chakra-ui | ⚡️ Simple, Modular & Accessible UI Components for your React Applications. | 20300 | chakra-ui.com |     2073 | MIT License |   23100 |          429 | typescript      | Components Library | 2018-08-12
(1 row)
```


<br>

**4. All the libraries released before 2015.**

<!-- Your Query Goes Here -->
```sql
SELECT * FROM jslibraries WHERE release_date < '2015-01-01';


name    |     owner      |                                        description                                        | stars  |                    url                     | releases |   licence   | used_by | contributors | main_technology |        type        | release_date 
------------+----------------+-------------------------------------------------------------------------------------------+--------+--------------------------------------------+----------+-------------+---------+--------------+-----------------+--------------------+--------------
 react      | facebook       | A declarative, efficient, and flexible JavaScript library for building user interfaces.   | 174000 | reactjs.org                                |      138 | MIT License | 7400000 |         1501 | javascript      | SPA library        | 2014-08-23
 ant-design | ant-design     | VAn enterprise-class UI design language and React UI library.                             |  34600 | ant.design                                 |      474 | MIT License |  233000 |         1469 | typescript      | Components Library | 2012-12-16
 victory    | FormidableLabs | A collection of composable React components for building interactive data visualizations. |   9100 | http://formidable.com/open-source/victory/ |      214 |             |    9700 |          148 | javascript      | Charts Library     | 2014-08-08
 pug        | pugjs          | Pug – robust, elegant, feature rich template engine for Node.js.                          |  20300 | pugjs.org                                  |      244 | MIT License |  348000 |          253 | javascript      | Template engine    | 2012-02-07
 hbs        | pillarjs       | Express view engine wrapper for Handlebars.                                               |   1500 | pugjs.org                                  |       44 | MIT License |         |           25 | javascript      | Template engine    | 2013-08-25
 moment     | moment         | Parse, validate, manipulate, and display dates in javascript.                             |  45900 | momentjs.com                               |       84 |             | 2500000 |          590 | javascript      | Date library       | 2012-10-08
 solid      | solidjs        | A declarative, efficient, and flexible JavaScript library for building user interfaces.   |  10700 | solidjs.com                                |      194 | MIT License |     624 |           73 | typescript      | UI Library         | 2011-08-13
 chartjs    | chartjs        | Simple HTML5 Charts using the canvas tag.                                                 |  54700 | chartjs.org                                |       85 | MIT License |  414000 |          377 | javascript      | Charts Library     | 2011-11-02
(8 rows)
```


<br>

**5. Get the `name` and the `release_date` of the libraries without a licence.**

<!-- Your Query Goes Here -->
```sql
SELECT name, release_date FROM jslibraries WHERE licence IS NULL;

 name   | release_date 
---------+--------------
 victory | 2014-08-08
 moment  | 2012-10-08
(2 rows)
```

<br>

**6. Get the `name` and the `stars` from all CSS Framework libraries.**

<!-- Your Query Goes Here -->
```sql
SELECT name, stars FROM jslibraries WHERE type = 'CSS Framework';

 name | stars 
------+-------
(0 rows)

```
<br>

**7. Get the `name` of the libraries where the main technology is Typescript.**

<!-- Your Query Goes Here -->

```sql

SELECT name FROM jslibraries WHERE main_technology = 'typescript';

       name        
-------------------
 styled-components
 ant-design
 chakra-ui
 solid
(4 rows)
```

<br>

**8. Get the `name` and the `type` of all the libraries with more than 1000 contributors.**

<!-- Your Query Goes Here -->
```sql
SELECT name, type FROM jslibraries WHERE contributors > 1000;

   name    |        type        
------------+--------------------
 react      | SPA library
 ant-design | Components Library
 bootstrap  | CSS Framework
(3 rows)

```

<br>

**9. Get the total number of `stars` of all the libraries.**

<!-- Your Query Goes Here -->
```sql
SELECT SUM(stars) FROM jslibraries;

 sum   
--------
 783300
(1 row)
```

<br>

**10. Get the average number of `contributors` for all the libraries.**

<!-- Your Query Goes Here -->
```sql
SELECT AVG(contributors) FROM jslibraries;

         avg          
----------------------
 542.5384615384615385
(1 row)


```

<br>

**11. Update the `licence` field of the libriaries without a licence to store `'unknown'` instead of `NULL`.**

<!-- Your Query Goes Here -->
```sql

UPDATE jslibraries SET licence = 'unknown' WHERE licence IS NULL;
UPDATE 2

jslab=# SELECT name, licence FROM jslibraries WHERE licence = 'unknown';
  name   | licence 
---------+---------
 victory | unknown
 moment  | unknown
(2 rows)

```

<br>

**12. Update the `used_by` field of the libraries that don't have this information to store `'unknown'` instead of `NULL`.**

<!-- Your Query Goes Here -->
```sql
UPDATE jslibraries SET used_by = 0 WHERE used_by IS NULL;
UPDATE 2


name   |     owner      |                                        description                                        | stars |                    url                     | releases | licence | used_by | contributors | main_technology |      type      | release_date 
---------+----------------+-------------------------------------------------------------------------------------------+-------+--------------------------------------------+----------+---------+---------+--------------+-----------------+----------------+--------------
 victory | FormidableLabs | A collection of composable React components for building interactive data visualizations. |  9100 | http://formidable.com/open-source/victory/ |      214 | unknown |    9700 |          148 | javascript      | Charts Library | 2014-08-08
 moment  | moment         | Parse, validate, manipulate, and display dates in javascript.                             | 45900 | momentjs.com                               |       84 | unknown | 2500000 |          590 | javascript      | Date library   | 2012-10-08
(2 rows)


```

<br>

**13. Update all the records to capitalize the string provided in the `main_technology` field.**

<!-- Your Query Goes Here -->
```sql
UPDATE jslibraries SET main_technology = INITCAP(main_technology);
UPDATE 13

<!-- Para confirmar se deu certo -->
SELECT DISTINCT main_technology FROM jslibraries;

 main_technology 
-----------------
 Typescript
 Javascript
(2 rows)

```

<br>

**14. Delete all the records where `licence` is `'unknown'`.**

<!-- Your Query Goes Here -->
```sql

DELETE FROM jslibraries WHERE licence = 'unknown';
DELETE 2

SELECT * FROM jslibraries WHERE licence = 'unknown';
 name | owner | description | stars | url | releases | licence | used_by | contributors | main_technology | type | release_date 
------+-------+-------------+-------+-----+----------+---------+---------+--------------+-----------------+------+--------------
(0 rows)


```

<br>

**15. Delete all the records with 10000 or less `stars`.**

<!-- Your Query Goes Here -->
```sql
DELETE FROM jslibraries WHERE stars <= 10000;
DELETE 1

SELECT * FROM jslibraries WHERE stars <= 10000;
 name | owner | description | stars | url | releases | licence | used_by | contributors | main_technology | type | release_date 
------+-------+-------------+-------+-----+----------+---------+---------+--------------+-----------------+------+--------------
(0 rows)


```

<br>

**16. Delete all the records with less than 100 `releases`.**

<!-- Your Query Goes Here -->
```sql
DELETE FROM jslibraries WHERE releases < 100;
DELETE 3

SELECT * FROM jslibraries WHERE releases < 100;
 name | owner | description | stars | url | releases | licence | used_by | contributors | main_technology | type | release_date 
------+-------+-------------+-------+-----+----------+---------+---------+--------------+-----------------+------+--------------
(0 rows)


```

<br>
