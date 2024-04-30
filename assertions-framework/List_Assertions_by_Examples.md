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
    version: 3.8.18
  nbformat: 4
  nbformat_minor: 4
---

<div class="cell markdown">

In this notebook, I've covered most used List assertion functions. Below
are these functions:

1.  `assert_list_variable_equals_variable(student_variable_name, expected_variable_name, delete_afterwards=True)`
2.  `assert_list_variable_equals_json(student_variable_name, json_file_name)`
3.  `assert_list_variable_equals_pickle(student_variable_name, pickle_file_name)`

</div>

<div class="cell code">

``` python
exec(open("utils.py").read())
```

</div>

<div class="cell markdown">

### Student Data Activities

</div>

<div class="cell code">

``` python
# Import the data from the text file into a list
student_list = []
with open("student.txt", "r") as file:
    for line in file:
        student = line.strip().split(',')
        student_list.append(student)

# Print the first 5 students
student_list[:5]
```

</div>

<div class="cell markdown">

#### 1. Put the students from the index 98 to 214 into the list `best_students`

Create a list `select_student` from the original list(`student_list`),
starting at index 98 up to, but not including, index 214.

> Make sure to not change the order of the students.

</div>

<div class="cell code">

``` python
select_student = ...
```

</div>

<div class="cell markdown">

Solutions:

</div>

<div class="cell code">

``` python
select_student = student_list[98:214]
select_student
```

</div>

<div class="cell code">

``` python
# save json file
import json
with open('activity_solutions_files/solution_01.json', 'w') as f:
    json.dump(select_student, f)
```

</div>

<div class="cell markdown">

Assertion:

</div>

<div class="cell code">

``` python
# new assertions
assert_list_variable_equals_json("select_student", "solution_01.json")
```

</div>

<div class="cell markdown">

##### 2. Find the `name, age, grade, subject` of the last student from our `select_students` list.

From the previous activity, we have the list `select_student` which
contains the students from the index 98 to 214. Now we need to find the
`name, age, grade, subject` of the last student from our
`select_student` list. Store the values in the variables
`name, age, grade, and subject` respectively.

</div>

<div class="cell code">

``` python
name = ...
age = ...
grade = ...
subject = ...
```

</div>

<div class="cell markdown">

Solutions:

</div>

<div class="cell code">

``` python
name = select_student[-1][0]
age = select_student[-1][2]
grade = select_student[-1][3]
subject = select_student[-1][4]

print(f"name: {name} age: {age} grade: {grade} & subject: {subject}")
```

</div>

<div class="cell markdown">

Assertion:

</div>

<div class="cell code">

``` python
# new assertions
expected_name = "Audrey"
expected_age = "17"
expected_grade = "E"
expected_subject = "History"
assert_variable_equals_variable("name", "expected_name")
assert_variable_equals_variable("age", "expected_age")
assert_variable_equals_variable("grade", "expected_grade")
assert_variable_equals_variable("subject", "expected_subject")
```

</div>

<div class="cell markdown">

## List Iteration with Conditional Statements

</div>

<div class="cell markdown">

##### 3. Get the ages of each student and store it in the list `students_age`

> Convert the ages into `int` as currently they are type `str` (string).

Loop through the list `student_list`, access the age, cast it to int,
and append it to the new list variable `students_age`.

</div>

<div class="cell code">

``` python
students_age = ...
```

</div>

<div class="cell markdown">

Solutions:

</div>

<div class="cell code">

``` python
students_age = []
for student in student_list:
    student_age = int(student[2])
    students_age.append(student_age)

students_age
```

</div>

<div class="cell code">

``` python
len(students_age)
```

</div>

<div class="cell code">

``` python
# save json file
import json
with open('activity_solutions_files/solution_03.json', 'w') as f:
    json.dump(students_age, f)
```

</div>

<div class="cell markdown">

Assertion:

</div>

<div class="cell code">

``` python
# new assertions
assert_list_variable_equals_json("students_age", "solution_03.json")
```

</div>

<div class="cell markdown">

##### 4. How many students have `History` as their favorite subject, how many have `English` and how many have `Math`.

Iterate through the list `student_list` and check for each of these
subjects, incrementing each time the variable for the corresponding
subject and store the result in the variables `history_lovers`,
`english_lovers` and `maths_lovers` respectively.

</div>

<div class="cell code">

``` python
history_lovers = ...
maths_lovers = ...
english_lovers = ...
```

</div>

<div class="cell markdown">

Solutions:

</div>

<div class="cell code">

``` python
history_lovers_student = []
english_lovers_student = []
maths_lovers_student = []

for student in student_list:
    if "History" in student[4]:
        if student[0] not in history_lovers_student:
            history_lovers_student.append(student[0])
    if "English" in student[4]:
        if student[0] not in english_lovers_student:
            english_lovers_student.append(student[0])
    if "Math" in student[4]:
        if student[0] not in maths_lovers_student:
            maths_lovers_student.append(student[0])

history_lovers = len(history_lovers_student)
english_lovers = len(english_lovers_student)
maths_lovers = len(maths_lovers_student)

print(f"History lovers: {history_lovers}")
print(f"English lovers: {english_lovers}")
print(f"Maths lovers: {maths_lovers}")
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
# new assertions
expected_history_lovers = 52
expected_english_lovers = 49
expected_maths_lovers = 63
assert_variable_equals_variable("history_lovers", "expected_history_lovers")
assert_variable_equals_variable("english_lovers", "expected_english_lovers")
assert_variable_equals_variable("maths_lovers", "expected_maths_lovers")
```

</div>

<div class="cell markdown">

##### 5. Separate all `A` graders and all `B` graders from the list `student_list`.

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

</div>

<div class="cell code">

``` python
a_graders = ...
b_graders = ...
```

</div>

<div class="cell markdown">

Solutions:

</div>

<div class="cell code">

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

</div>

<div class="cell code">

``` python
a_graders
```

</div>

<div class="cell code">

``` python
# save json file
import json
with open('activity_solutions_files/solution_04_a.json', 'w') as f:
    json.dump(a_graders, f)

with open('activity_solutions_files/solution_04_b.json', 'w') as f:
    json.dump(b_graders, f)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
# new assertions
assert_list_variable_equals_json("a_graders", "solution_04_a.json")
assert_list_variable_equals_json("b_graders", "solution_04_b.json")
```

</div>

<div class="cell markdown">

##### 6. Remove the student `['Luna', '18', 'E', 'Geography']` from the list `student_list`.

Remove the student whose name is `Luna`, age is `18`, grade is `E` and
subject is `Geography` from the list `student_list`. If there are
multiple students with the same name, age, grade, and subject, remove
all of them.

</div>

<div class="cell code">

``` python
# Try your code here
```

</div>

<div class="cell markdown">

Solutions:

</div>

<div class="cell code">

``` python
student_to_remove = ['Luna', '18', 'E', 'Geography']

students_to_remove = []

for student in student_list:
    if student[0] == student_to_remove[0] and student[2] == student_to_remove[1] and student[3] == student_to_remove[2] and student[4] == student_to_remove[3]:
        students_to_remove.append(student)

print(students_to_remove)

for student in students_to_remove:
    student_list.remove(student)
```

</div>

<div class="cell code">

``` python
# save json file
with open('activity_solutions_files/solution_05.json', 'w') as f:
    json.dump(student_list, f)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
# new assertions
assert_list_variable_equals_json("student_list", "solution_05.json")
```

</div>

<div class="cell markdown">

##### 6. Convert the `student_list` into list of tuples.

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

</div>

<div class="cell code">

``` python
# Try your code here
student_list_tuple = ...
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

``` python
student_list_tuple = []

for student in student_list:
    student_list_tuple.append(tuple(student))
    
student_list_tuple[:5]
```

</div>

<div class="cell code">

``` python
# save in a pickle file
import pickle

with open('activity_solutions_files/solution_06.pkl', 'wb') as f:
    pickle.dump(student_list_tuple, f)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
# new assertions
assert_list_variable_equals_pickle("student_list_tuple", "solution_06.pkl")
```

</div>

<div class="cell markdown">

### The End!

</div>
