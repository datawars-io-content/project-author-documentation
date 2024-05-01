---
jupyter:
  kernelspec:
    display_name: Python 3 (ipykernel)
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
    version: 3.10.14
  nbformat: 4
  nbformat_minor: 5
---

<div class="cell markdown">

In this notebook, I've covered most used Tuple assertion functions.
Below are these functions:

1.  `assert_tuple_variable_equals_variable(student_variable_name, expected_variable_name, delete_afterwards=True)`
2.  `assert_tuple_variable_equals_pickle(student_variable_name, pickle_file_name)`

</div>

<div class="cell code">

``` python
exec(open("utils.py").read())
```

</div>

<div class="cell markdown">

### Read the dataset

</div>

<div class="cell code">

``` python
# lets get our dataset of Fibonacci Sequence
import pandas as pd
fibo_seq = tuple(pd.read_csv('./fibonacci_sequence.txt').squeeze('columns').values)

# checking first 10 fruits
fibo_seq[:10]
```

</div>

<div class="cell markdown">

##### Activity 1. Slice the tuple `fibo_seq` from 4th index to 34th index

</div>

<div class="cell code">

``` python
# Try your code here
thirty_step = ...
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

``` python
thirty_step = fibo_seq[4:34]
thirty_step
# len(thirty_step)
```

</div>

<div class="cell code">

``` python
# save pickle file
import pickle
with open('activity_solutions_files/solution_01.pkl', 'wb') as f:
    pickle.dump(thirty_step, f)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
# new assertions
assert_tuple_variable_equals_pickle('thirty_step', 'solution_01.pkl')
```

</div>

<div class="cell markdown">

### Students Records Data

</div>

<div class="cell markdown">

**Below are two tuples having students records of two cohorts for
Computer Science course this semester, each cohort has 30 students**

Each tuple is as `(student_name, overall_grade)`.

</div>

<div class="cell code">

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

</div>

<div class="cell code">

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

</div>

<div class="cell markdown">

##### Activity 2. Concatenate the records of both collections into one tuple

</div>

<div class="cell code">

``` python
# Try your code here
combined = ...
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

``` python
combined = student_data_a + student_data_b
combined[0:5]
```

</div>

<div class="cell code">

``` python
# save pickle file
with open('activity_solutions_files/solution_02.pkl', 'wb') as f:
    pickle.dump(combined, f)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
# new assertions
assert_tuple_variable_equals_pickle('combined', 'solution_02.pkl')
```

</div>

<div class="cell markdown">

##### Activity 3. Sort the `combined` tuple so that we will have names in alphabetic order\*\*

</div>

<div class="cell code">

``` python
# Try your code here
sorted_combine = ...
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

``` python
sorted_combine = tuple(sorted(combined))
sorted_combine
```

</div>

<div class="cell code">

``` python
# save pickle file
with open('activity_solutions_files/solution_3.pkl', 'wb') as f:
    pickle.dump(sorted_combine, f)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
# new assertions
assert_tuple_variable_equals_pickle('sorted_combine', 'solution_3.pkl')
```

</div>

<div class="cell markdown">

##### Activity 4. Find the student with the highest grade

First, find the highest grade and then find the student with that grade
then store the details in a tuple named `top_student`.

</div>

<div class="cell code">

``` python
# Try your code here
top_student = ...
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

``` python
top_student = sorted_combine[-1]
```

</div>

<div class="cell code">

``` python
top_student
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
# new assertions
expected_top_student = ('Zoa', 95)
assert_tuple_variable_equals_variable('top_student', 'expected_top_student')
```

</div>

<div class="cell markdown">

### The End!

</div>
