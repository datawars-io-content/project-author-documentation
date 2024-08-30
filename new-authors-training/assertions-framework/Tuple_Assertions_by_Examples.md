In this notebook, you'll learn how to use most used Tuple assertion functions.
Below are these functions:

1.  `assert_tuple_variable_equals_variable(student_variable_name, expected_variable_name, delete_afterwards=True)`: Checks if student tuple variable is equals to expected tuple variable.
2.  `assert_tuple_variable_equals_pickle(student_variable_name, pickle_file_name)`: Checks if student tuple variable is equals to expected pickle file.


Load the `utils.py` file to use the assertion functions.

``` python
exec(open("utils.py").read())
```

### Activities

**Below are two tuples having students records of two cohorts for
Computer Science course this semester, each cohort has 30 students**

Each tuple is as `(student_name, overall_grade)`.

``` python
student_data_a = (
    ("John", 85), ("Emily", 92), ("Michael", 78), ("Sophia", 95),
    ("Jacob", 88), ("Emma", 90), ("Joshua", 81), ("Olivia", 87),
    ("Daniel", 93), ("Ava", 89), ("Matthew", 77), ("Isabella", 94),
    ("Ethan", 83), ("Mia", 91), ("Alexander", 86), ("Charlotte", 84),
    ("William", 82), ("Amelia", 96), ("James", 79), ("Liam", 97),
    ("Abigail", 80), ("Benjamin", 85), ("Harper", 88), ("Henry", 92),
    ("Ella", 89), ("Samuel", 83), ("Sofia", 90), ("David", 94),
    ("Victoria", 87), ("Joseph", 91)
)
```


``` python
student_data_b = (
    ("Lily", 88), ("Christopher", 94), ("Grace", 79), ("Andrew", 91),
    ("Samantha", 85), ("Jack", 90), ("Avery", 82), ("Daniel", 96),
    ("Madison", 89), ("Ryan", 77), ("Evelyn", 93), ("Nicholas", 84),
    ("Chloe", 92), ("Joshua", 81), ("Zoe", 95), ("Luke", 86),
    ("Hannah", 83), ("Gabriel", 90), ("Aria", 87), ("Caleb", 78),
    ("Lillian", 94), ("Isaac", 84), ("Audrey", 91), ("Owen", 89),
    ("Brooklyn", 82), ("Nathan", 95), ("Elizabeth", 88), ("Elijah", 93),
    ("Scarlett", 86), ("David", 90)
)
```


+++Activity 1
##### 1. Concatenate the records of both collections into one tuple

Combine the records of both cohorts into one tuple named `combined`.

``` python
# Try your code here
combined = ...
```

+++Solution
Solution:

``` python
combined = student_data_a + student_data_b
```


+++Assertions

As the expected tuple is quite large, we can save it in a pickle file and then use `assert_tuple_variable_equals_pickle()` function to assert the solution with the student tuple.

This is how you can save the tuple in a pickle file.

``` python
# save pickle file
with open('activity_solutions_files/solution_02.pkl', 'wb') as f:
    pickle.dump(combined, f)
```

Assertions:

``` python
assert_tuple_variable_equals_pickle('combined', 'solution_02.pkl')
```
+++


+++Activity 2
##### 2. Find the student with the highest grade

First, find the highest grade and then find the student with that grade
then store the details in a tuple named `top_student`.

``` python
# Try your code here
top_student = ...
```

+++Solution
Solution:

``` python
top_student = sorted_combine[-1]
```

+++Assertions

As the expected tuple only contains one student, we can easily compare it with the student tuple, we can use `assert_tuple_variable_equals_variable()` function to assert the solution with the student tuple.

Assertions:

``` python
expected_top_student = ('Zoa', 95)
assert_tuple_variable_equals_variable('top_student', 'expected_top_student')
```
+++