---
expanded: true
order: G
---

In this notebook, you'll learn how to use most used SQL assertion functions. Below
are the functions that I've covered in this notebook.

1.  `assert_sqlite_student_query_equals_expected_query(SQLITE_TRAVEL, SOLUTION_QUERY)`: Checks if student SQLite query is equals to expected query.
2.  `assert_mysql_student_query_equals_expected_query('sakila', SOLUTION_QUERY)`: Checks if student MySQL query is equals to expected query.
3.  `assert_postgresql_student_query_equals_expected_query('dvdrental', SOLUTION_QUERY)`: Checks if student PostgreSQL query is equals to expected query.



### Activities

##### 1. Find the First Country

Write a query to retrieve the first country from the `country` table.
Rename the column to `First Country`. Use `IndepYear` to determine the
first country.

``` python
STUDENT_QUERY = '''
{{ code_answer | safe }}
'''
SOLUTION_QUERY = '''
# paste the solution from the project author here
'''

# SQLite:
assert_sqlite_student_query_equals_expected_query(SQLITE_TRAVEL, SOLUTION_QUERY)
# MySQL
assert_mysql_student_query_equals_expected_query('sakila', SOLUTION_QUERY)
# PostgreSQL
assert_postgresql_student_query_equals_expected_query('dvdrental', SOLUTION_QUERY)
```

There are 3 SQL engine available, use the appropriate assertion function
to check your query result with the expected result of the
`SOLUTION_QUERY`.

