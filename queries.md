![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# Answers

## Iteration 2

**1. Add the `solid` and `chartjs` libraries as new rows to the `jslibraries` table.**

<!-- Your Query Goes Here -->

<br>

**2. Get all the fields of the library that was released earliest (first).**

<!-- Your Query Goes Here -->

select \* from jslibraries
order by release_date asc
<br>

**3. Get all the fields of the library that was released most recently (last).**

<!-- Your Query Goes Here -->

select \* from jslibraries
order by release_date desc

<br>

**4. All the libraries released before 2015.**

<!-- Your Query Goes Here -->

select \* from jslibraries
where release_date < '2015-01-01';

<br>

**5. Get the `name` and the `release_date` of the libraries without a licence.**

<!-- Your Query Goes Here -->

select name, release_date from jslibraries
where licence != 'MIT License'

<br>

**6. Get the `name` and the `stars` from all CSS Framework libraries.**

<!-- Your Query Goes Here -->

select name, stars from jslibraries
where type = 'CSS Framework'

<br>

**7. Get the `name` of the libraries where the main technology is Typescript.**

<!-- Your Query Goes Here -->

select name from jslibraries
where main_technology = 'typescript'

<br>

**8. Get the `name` and the `type` of all the libraries with more than 1000 contributors.**

<!-- Your Query Goes Here -->

select name, type from jslibraries
where contributors < 1000

<br>

**9. Get the total number of `stars` of all the libraries.**

<!-- Your Query Goes Here -->

select SUM(stars) from jslibraries

<br>

**10. Get the average number of `contributors` for all the libraries.**

<!-- Your Query Goes Here -->

select avg(contributors) from jslibraries

<br>

**11. Update the `licence` field of the libriaries without a licence to store `'unknown'` instead of `NULL`.**

<!-- Your Query Goes Here -->

update jslibraries
set licence = 'unknown'
where licence IS NULL

<br>

**12. Update the `used_by` field of the libraries that don't have this information to store `'unknown'` instead of `NULL`.**

<!-- Your Query Goes Here -->

update jslibraries
set used_by = 'unknown'
where used_by IS NULL

<br>

**13. Update all the records to capitalize the string provided in the `main_technology` field.**

<!-- Your Query Goes Here -->

update jslibraries
SET main_technology = UPPER(main_technology);

<br>

**14. Delete all the records where `licence` is `'unknown'`.**

<!-- Your Query Goes Here -->

delete from jslibraries
where licence = 'unknown'

<br>

**15. Delete all the records with 10000 or less `stars`.**

<!-- Your Query Goes Here -->

delete from jslibraries
where stars < 10001

<br>

**16. Delete all the records with less than 100 `releases`.**

<!-- Your Query Goes Here -->

delete from jslibraries
where releases < 100

<br>
