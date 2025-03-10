![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# Answers

## Iteration 2

**1. Add the `solid` and `chartjs` libraries as new rows to the `jslibraries`
table.**

INSERT INTO jslibraries (name, type, main_technology, stars, used_by, licence,
contributors, releases, release_date) VALUES ('solid', 'UI Library',
'typescript', 10700, 624, 'MIT License', 73, 194, '2011-08-13'), ('chartjs',
'Charts Library', 'javascript', 54700, 414000, 'MIT License', 377, 85,
'2011-11-02');

<br>

**2. Get all the fields of the library that was released earliest (first).**

SELECT \* FROM jslibraries ORDER BY releases ASC ;

<br>

**3. Get all the fields of the library that was released most recently (last).**

SELECT \* FROM jslibraries ORDER BY releases DeSC ; <br>

**4. All the libraries released before 2015.**

SELECT \* FROM jslibraries ORDER BY releases < 2015 ;

<br>

**5. Get the `name` and the `release_date` of the libraries without a licence.**

SELECT name, release_date FROM jslibraries WHERE licence IS NULL;

<br>

**6. Get the `name` and the `stars` from all CSS Framework libraries.**

SELECT name, stars FROM jslibraries WHERE type = 'CSS FRAMEWORK';

<br>

**7. Get the `name` of the libraries where the main technology is Typescript.**

SELECT name FROM jslibraries WHERE main_technology = 'typescript';

<br>

**8. Get the `name` and the `type` of all the libraries with more than 1000
contributors.**

SELECT name FROM jslibraries WHERE main_technology = 'typescript'; <br>

**9. Get the total number of `stars` of all the libraries.**

SELECT stars FROM jslibraries

<br>

**10. Get the average number of `contributors` for all the libraries.**

SELECT AVG(contributors) FROM jslibraries

<br>

**11. Update the `licence` field of the libriaries without a licence to store
`'unknown'` instead of `NULL`.**

UPDATE jslibraries SET licence = 'unknown' WHERE licence IS NULL;

<br>

**12. Update the `used_by` field of the libraries that don't have this
information to store `'unknown'` instead of `NULL`.**

UPDATE jslibraries SET used_by = 'unknown' WHERE used_by IS NULL;

<br>

**13. Update all the records to capitalize the string provided in the
`main_technology` field.**

UPDATE jslibraries SET main_technology = UPPER(main_technology);

<br>

**14. Delete all the records where `licence` is `'unknown'`.**

DELETE FROM jslibraries WHERE licence = 'unknown'

<br>

**15. Delete all the records with 10000 or less `stars`.**

DELETE FROM jslibraries WHERE stars <= 1000

<br>

**16. Delete all the records with less than 100 `releases`.**

DELETE FROM jslibraries WHERE releases <= 100 <br>
