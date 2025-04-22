![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# Answers

## Iteration 2

**1. Add the `solid` and `chartjs` libraries as new rows to the `jslibraries` table.**

INSERT INTO jslibraries(name, owner, description, stars, url, releases, licence, used_by, contributors, main_technology, type,release_date) VALUES ('solid', 'solidjs', 'A declarative, efficient, and flexible JavaScript library for building user interfaces.', 10700, 'solidjs.com', 194, 'MIT License', 624, 73, 'typescript', 'UI Library', '2011-08-13'),
('chartjs', 'chartjs', 'Simple HTML5 Charts using the canvas tag.', 54700, 'chartjs.org', 85, 'MIT License', 414000, 377, 'javascript', 'Charts Library', '2011-11-02');

<br>

**2. Get all the fields of the library that was released earliest (first).**

SELECT \* FROM jslibraries ORDER BY release_date ASC LIMIT 1;

<br>

**3. Get all the fields of the library that was released most recently (last).**

SELECT \* FROM jslibraries ORDER BY release_date DESC LIMIT 1;

<br>

**4. All the libraries released before 2015.**

SELECT \* FROM jslibraries WHERE release_date < '2015-01-01';

<br>

**5. Get the `name` and the `release_date` of the libraries without a licence.**

SELECT name, release_date FROM jslibraries WHERE licence is NULL;

<br>

**6. Get the `name` and the `stars` from all CSS Framework libraries.**

SELECT name, stars FROM jslibraries WHERE type = 'CSS Framework';

<br>

**7. Get the `name` of the libraries where the main technology is Typescript.**

SELECT name FROM jslibraries WHERE main_technology = 'typescript';

<br>

**8. Get the `name` and the `type` of all the libraries with more than 1000 contributors.**

SELECT name, type FROM jslibraries WHERE contributors > 1000;

<br>

**9. Get the total number of `stars` of all the libraries.**

SELECT SUM(stars) AS total_stars FROM jslibraries;

<br>

**10. Get the average number of `contributors` for all the libraries.**

SELECT AVG(contributors) AS average_contributors FROM jslibraries;

<br>

**11. Update the `licence` field of the libriaries without a licence to store `'unknown'` instead of `NULL`.**

UPDATE jslibraries SET licence = 'unknown' WHERE licence IS NULL;

<br>

**12. Update the `used_by` field of the libraries that don't have it specified to store `0` ( i.e., number zero), instead of `NULL`.**

UPDATE jslibraries SET used_by = 0 WHERE used_by IS NULL;

<br>

**13. Update all the records to capitalize the string provided in the `main_technology` field.**

UPDATE jslibraries SET main_technology = UPPER(main_technology);

<br>

**14. Delete all the records where `licence` is `'unknown'`.**

DELETE FROM jslibraries WHERE licence = 'unknown';

<br>

**15. Delete all the records with 10000 or less `stars`.**

DELETE FROM jslibraries WHERE stars <= 10000;

<br>

**16. Delete all the records with less than 100 `releases`.**

DELETE FROM jslibraries WHERE releases < 100;

<br>
