---
expanded: true
order: A
---

In this notebook, you'll learn how to use most used Functions checking assertion
functions. Below are the functions that I've covered in this notebook.

1.  `assert_student_function_name_equals(student_function_name, fn_args=None, fn_kwargs=None, expected_value=DataWarsConstants.EMPTY)`: Checks that the student's function named `student_function_name` returns the expected value.
2.  `assert_student_function_test_cases(student_function_name, test_cases)`: Checks that the student's function named `student_function_name` returns the expected value for each test case in the list `test_cases`.

Load the `utils.py` file to use the assertion functions.

``` python
exec(open("utils.py").read())
```

### Activities

Now, with activities examples, you'll learn how to use the assertion functions.

+++Activity 1
##### 1. Create a function `add()`.

Create a functions `add()` that takes two arguments and returns the sum
of the two arguments.

``` python
def add(a, b):
    pass
```

+++Solution
Solution:

``` python
def add(a, b):
    return a + b
```

+++Assertions

Out expected function should return the sum of the two arguments. So, we use `assert_student_function_name_equals()` function to assert the solution with the student function.

Assertions:

``` python
assert_function_name_equals('add', (2, 6), expected_value=8)
```
+++

+++Activity 2
##### 2. Implement a Function to Define a Movie Dictionary

Define a function `define_movies` that takes a dictionary, `id`, `name`, `year`, and `rank` as arguments and returns the dictionary with the movie details. Function also takes empty dictionary as first argument which will be used to store the movie details.

``` python
movies = {}

def define_movies(dictionary, id, name, year, rank):
    # Your code goes here
    return dictionary
```


+++Solution
Solution:

``` python
def define_movies(dictionary, id, name, year, rank):
    dictionary[id] = {
        'name': name,
        'year': year,
        'rank': rank
    }
    return dictionary
```


``` python
define_movies(movies, 0, 'Carmencita', 1894, 5.6)
```

+++Assertions

Here we have two expected outputs, so we save them in two different dictionaries and then use `assert_student_function_test_cases()` function to assert the solution with the student function.
Assertions:

``` python
# For the function `define_movies()`
expedted_movies_1 = {}
expedted_movies_2 = {}

assert_student_function_test_cases(
    "define_movies",
    [
    student_function_test_case((expedted_movies_1, 0, 'Carmencita', 1894, 5.6), expected_value={0: {'name': 'Carmencita', 'year': 1894, 'rank': 5.6}}),
    student_function_test_case((expedted_movies_2, 0, 'Carmencita', 1894, 5.6), expected_value={0: {'name': 'Carmencita', 'year': 1894, 'rank': 5.6}}),
     
    #  Add one more in expected_movies_1
    student_function_test_case((expedted_movies_1, 1, 'Carmencita', 1894, 5.6), expected_value={0: {'name': 'Carmencita', 'year': 1894, 'rank': 5.6}, 1: {'name': 'Carmencita', 'year': 1894, 'rank': 5.6}}),
    ]
)
```
+++


+++Activity 3
##### 3. Define a function `define_roles`

Define a function `define_roles` that takes a dictionary, `actor_id`, and `role` as arguments and returns the dictionary with the actor's roles. Function also takes empty dictionary as first argument which will be used to store the actor's roles.

``` python
roles = {}

def define_roles(dictionary, actor_id, role):
    # Your code goes here
    return dictionary
```

+++Solution
Solution:

``` python
def define_roles(dictionary, actor_id, role):
    if actor_id in dictionary:
        dictionary[actor_id]['role'].append(role)
    else:
        dictionary[actor_id] = {
            'role': [role]
        }
    return dictionary
```

``` python
define_roles(roles, 4, 'Actor')
define_roles(roles, 4, 'Singer')
define_roles(roles, 3, 'Actor')
```

+++Assertions

Here we have two expected outputs, so we save them in two different dictionaries and then use `assert_student_function_test_cases()` function to assert the solution with the student function.

Assertions:

``` python
# For the function `define_roles()`
expedted_roles_1 = {}
expedted_roles_2 = {}

assert_student_function_test_cases(
    "define_roles",
    [
    student_function_test_case((expedted_roles_1, 4, 'Actor'), expected_value={4: {'role': ['Actor']}}),
    student_function_test_case((expedted_roles_2, 4, 'Actor'), expected_value={4: {'role': ['Actor']}}),
     
    #  Add one more in expeted_roles_1
    student_function_test_case((expedted_roles_1, 4, 'Singer'), expected_value={4: {'role': ['Actor', 'Singer']}}),
    ]
)
```
+++
