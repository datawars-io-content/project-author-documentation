---
jupyter:
  language_info:
    name: python
  nbformat: 4
  nbformat_minor: 2
---

<div class="cell markdown">

In this notebook, I've covered most used SQL assertion functions. Below
are the functions that I've covered in this notebook.

1.  `assert_sqlite_student_query_equals_expected_query(SQLITE_TRAVEL, SOLUTION_QUERY)`
2.  `assert_mysql_student_query_equals_expected_query('sakila', SOLUTION_QUERY)`
3.  `assert_postgresql_student_query_equals_expected_query('dvdrental', SOLUTION_QUERY)`

</div>

<div class="cell markdown">

### Activities

</div>

<div class="cell markdown">

##### Activity 1. Find the First Country

Write a query to retrieve the first country from the `country` table.
Rename the column to `First Country`. Use `IndepYear` to determine the
first country.

</div>

<div class="cell code">

``` python
STUDENT_QUERY = '''
{{ code_answer | safe }}
'''
SOLUTION_QUERY = '''
# paste the solution from the project author here
'''

# SQLite:
# assert_sqlite_student_query_equals_expected_query(SQLITE_TRAVEL, SOLUTION_QUERY)
# MySQL
# assert_mysql_student_query_equals_expected_query('sakila', SOLUTION_QUERY)
# PostgreSQL
# assert_postgresql_student_query_equals_expected_query('dvdrental', SOLUTION_QUERY)
```

</div>

<div class="cell markdown">

There are 3 SQL engine available, use the appropriate assertion function
to check your query result with the expected result of the
`SOLUTION_QUERY`.

</div>

<div class="cell markdown">

### The End!

</div>
