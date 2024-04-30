---
jupyter:
  kernelspec:
    display_name: base
    language: python
    name: python3
  language_info:
    codemirror_mode:
      name: ipython
      version: 3
    file_extension: .py
    mimetype: text/x-python
    name: python
    nbconvert_exporter: python
    pygments_lexer: ipython3
    version: 3.10.4
  nbformat: 4
  nbformat_minor: 2
  orig_nbformat: 4
---

<div class="cell markdown">

In this notebook, I've covered most used Functions checking assertion
functions. Below are the functions that I've covered in this notebook.

1.  `assert_student_function_name_equals()`
2.  `assert_student_function_test_cases()`

</div>

<div class="cell code">

``` python
exec(open("utils.py").read())
```

</div>

<div class="cell markdown">

### Activities

</div>

<div class="cell markdown">

##### Activity 1. Create a function `add()`.

Create a functions `add()` that takes two arguments and returns the sum
of the two arguments.

</div>

<div class="cell code">

``` python
def add(a, b):
    pass
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

``` python
def add(a, b):
    return a + b
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
assert_function_name_equals('add', (2, 6), expected_value=8)
```

</div>

<div class="cell markdown">

##### Activity 2. Implement a Function to Define a Movie Dictionary

</div>

<div class="cell code">

``` python
movies = {}
```

</div>

<div class="cell code">

``` python
def define_movies(dictionary, id, name, year, rank):
    # Your code goes here
    return dictionary
```

</div>

<div class="cell code">

``` python
# Insert Values in movies dictionary using above created function
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

``` python
def define_movies(dictionary, id, name, year, rank):
    dictionary[id] = {
        'name': name,
        'year': year,
        'rank': rank
    }
    return dictionary
```

</div>

<div class="cell code">

``` python
define_movies(movies, 0, 'Carmencita', 1894, 5.6)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
# new assertions
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

</div>

<div class="cell markdown">

##### Activity 3. Define a function `define_roles`

</div>

<div class="cell code">

``` python
roles = {}

def define_roles(dictionary, actor_id, role):
    # Your code goes here
    return dictionary
```

</div>

<div class="cell code">

``` python
# Insert the data into `roles` dictionary
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

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

</div>

<div class="cell code">

``` python
define_roles(roles, 4, 'Actor')
define_roles(roles, 4, 'Singer')
define_roles(roles, 3, 'Actor')
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

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

</div>

<div class="cell markdown">

##### Activity 4. Define a function `define_movies_generes`

</div>

<div class="cell code">

``` python
movies_genres = {}

def define_movies_genres(dictionary, movie_id, genre):
    # Your code goes here
    return dictionary
```

</div>

<div class="cell code">

``` python
# Insert the data into `movies_genres` dictionary using function `define_movies_genres()`
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

``` python
def define_movies_genres(dictionary, movie_id, genre):
    if movie_id in dictionary:
        dictionary[movie_id]['genre'].append(genre)
    else:
        dictionary[movie_id] = {
            'genre': [genre]
        }
    return dictionary
```

</div>

<div class="cell code">

``` python
define_movies_genres(movies_genres, 1, 'Short')
define_movies_genres(movies_genres, 2, 'Short')
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
# new assertions

# For the function `define_movies_genres()`
expedted_movies_genres_1 = {}
expedted_movies_genres_2 = {}

assert_student_function_test_cases(
    "define_movies_genres",
    [
    student_function_test_case((expedted_movies_genres_1, 1, 'Short'), expected_value={1: {'genre': ['Short']}}),
    student_function_test_case((expedted_movies_genres_2, 1, 'Short'), expected_value={1: {'genre': ['Short']}}),
     
    #  Add one more in expeted_movies_genres_1
    student_function_test_case((expedted_movies_genres_1, 1, 'Comedy'), expected_value={1: {'genre': ['Short', 'Comedy']}}),
    ]
)
```

</div>

<div class="cell markdown">

### The End!

</div>
