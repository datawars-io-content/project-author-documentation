---
label: List Assertions
expanded: true
order: C
---

In this notebook, you'll learn how to use most used List assertion functions. Below
are these functions:

1.  `assert_list_variable_equals_variable(student_variable_name, expected_variable_name, delete_afterwards=True)`: Checks that the student's list in `student_variable_name` matches the list in `expected_variable_name`.
2.  `assert_list_variable_equals_json(student_variable_name, json_file_name)`: Checks that the student's list in `student_variable_name` matches the list contained in the solution JSON file named `json_file_name`.
3.  `assert_list_variable_equals_pickle(student_variable_name, pickle_file_name)`: Checks that the student's list in `student_variable_name` matches the list contained in the solution pickle file named `pickle_file_name`.

Load the `utils.py` file to use the assertion functions.

``` python
exec(open("utils.py").read())
```

### Student Data for Activities

In the activities, we'll use the below student data. Format of the data is `name, marks, age, grade, subject`. 

> There are total 500 students in the list, but we are showing only a few here.

``` python
# Import the data from the text file into a list
student_list = [['Gabriel', '53', '18', 'D', 'English'],
                ['Nora', '79', '18', 'F', 'Math'],
                ['Luna', '2', '18', 'A', 'English'],
                ['Anthony', '76', '18', 'A', 'Math'],
                ['Logan', '56', '17', 'D', 'History'],
                ['Luna', '25', '18', 'E', 'Geography'],
                ['Daniel', '29', '18', 'C', 'History'],
                ['Sarah', '92', '17', 'B', 'History'],
                ['Victoria', '91', '17', 'D', 'History'],
                ['Zoe', '47', '18', 'E', 'Geography']
                ...
                ]
```


### Activities

+++Activity 1
#### 1. Put the students from the index 98 to 104 into the list `best_students`

Create a list `select_student` from the original list(`student_list`),
starting at index 98 up to, but not including, index 104.

> Make sure to not change the order of the students.

Expected output:

``` python
[['Luna', '25', '18', 'E', 'Geography'],
 ['Daniel', '29', '18', 'C', 'History'],
 ['Sarah', '92', '17', 'B', 'History'],
 ['Victoria', '91', '17', 'D', 'History'],
 ['Zoe', '47', '18', 'E', 'Geography'],
 ...
]
```

``` python
select_student = ...
```

+++Solution
Solutions:

``` python
select_student = student_list[98:104]
select_student
```

+++Assertions

As we can see the expected output is a list of list which is small(only 6 students), so we use `assert_list_variable_equals_variable()` function to assert the solution with the student list.

Assertion:

``` python
expected_output = [['Luna', '25', '18', 'E', 'Geography'],
 ['Daniel', '29', '18', 'C', 'History'],
 ['Sarah', '92', '17', 'B', 'History'],
 ['Victoria', '91', '17', 'D', 'History'],
 ['Zoe', '47', '18', 'E', 'Geography'],
 ['Ava', '18', 'A', 'Art']]

assert_list_variable_equals_variable('select_student', 'expected_output')
```
+++



+++Activity 2
##### 2. Get the ages of each student and store it in the list `students_age`

> Convert the ages into `int` as currently they are type `str` (string).

Loop through the list `student_list`, access the age, cast it to int,
and append it to the new list variable `students_age`.


``` python
students_age = ...
```

+++Solution
Solutions:

``` python
students_age = []
for student in student_list:
    student_age = int(student[2])
    students_age.append(student_age)

students_age
```


+++Assertions

As the expected output is a list of integers containing total of 500 students and it is a large list, so we use `assert_list_variable_equals_json()` function to assert the solution with the student list.

This is how we can save the expected output in a json file:

``` python
# save json file
import json
with open('activity_solutions_files/solution_03.json', 'w') as f:
    json.dump(students_age, f)
```

Assertion:

``` python
# new assertions
assert_list_variable_equals_json("students_age", "solution_03.json")
```
+++



+++Activity 3
##### 4. Separate all `A` graders and all `B` graders from the list `student_list`.

Create two lists `a_graders` and `b_graders` with the name, age, grade,
and favorite subject of the students. Put students with `A` grades to
the list `a_graders` and students with `B` graders to the list
`b_graders`

Expected output for `a_graders`:

``` python
[['Luna', '18', 'A', 'English'],
 ['Anthony', '18', 'A', 'Math'],
 ['Bella', '17', 'A', 'History'],
 ['Lucy', '17', 'A', 'History'],
 ['Brooklyn', '18', 'A', 'History'],
 ['Ava', '18', 'A', 'Art'],
 ['Riley', '17', 'A', 'Math'],
 ...
]
```

``` python
a_graders = ...
b_graders = ...
```

+++Solution
Solutions:

``` python
a_graders = []
b_graders = []

for student in student_list:
    if student[3]=='A':
        student_name = student[0]
        student_age = student[2]
        student_grade = student[3]
        student_subject = student[4]
        a_graders.append([student_name,student_age,student_grade,student_subject])
    if student[3]=='B':
        student_name = student[0]
        student_age = student[2]
        student_grade = student[3]
        student_subject = student[4]
        b_graders.append([student_name,student_age,student_grade, student_subject])

print(f"len a {len(a_graders)}, len b: {len(b_graders)}")
```


+++Assertions

We use `assert_list_variable_equals_json()` function to assert the solution with the student list as the expected output is a list of list which is is quite large.

Here, we have two expected outputs, so we save them in two different json files and then use `assert_list_variable_equals_json()` function to assert the solution with the student list.

``` python
# save json file
import json
with open('activity_solutions_files/solution_04_a.json', 'w') as f:
    json.dump(a_graders, f)

with open('activity_solutions_files/solution_04_b.json', 'w') as f:
    json.dump(b_graders, f)
```

Assertions:

``` python
# new assertions
assert_list_variable_equals_json("a_graders", "solution_04_a.json")
assert_list_variable_equals_json("b_graders", "solution_04_b.json")
```
+++



+++Activity 4
##### 4. Convert the `student_list` into list of tuples.

Given the list `student_list` is a list of lists. Convert it into a list
of tuples and store it in the variable `student_list_tuple`.

Expected output:

``` python
[('Luna', '18', 'A', 'English'),
 ('Anthony', '18', 'A', 'Math'),
 ('Bella', '17', 'A', 'History'),
 ('Lucy', '17', 'A', 'History'),
 ('Brooklyn', '18', 'A', 'History'),
 ('Ava', '18', 'A', 'Art'),
 ('Riley', '17', 'A', 'Math'),
 ...
]
```

> This is just a simple conversion from list of lists to list of tuples.
> Expected output is different from above example list of tuples.

``` python
# Try your code here
student_list_tuple = ...
```

+++Solution
Solution:

``` python
student_list_tuple = []

for student in student_list:
    student_list_tuple.append(tuple(student))
    
student_list_tuple[:5]
```


+++Assertions

As the expected output is a list of tuples which is small, so we use `assert_list_variable_equals_pickle()` function to assert the solution with the student list as JSON can't save tuples.

This is how we can save the expected output in a pickle file:

``` python
# save in a pickle file
import pickle

with open('activity_solutions_files/solution_06.pkl', 'wb') as f:
    pickle.dump(student_list_tuple, f)
```

Assertions:

``` python
# new assertions
assert_list_variable_equals_pickle("student_list_tuple", "solution_06.pkl")
```
+++
