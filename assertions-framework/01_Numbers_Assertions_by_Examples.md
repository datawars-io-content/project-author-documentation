---
label: Numbers Assertions
expanded: true
order: A
---

In this notebook, you'll learn how to use most used Numbers assertion functions. Below
are these functions:

1.  `assert_variable_almost_equals(student_variable_name, expected_value, tolerance_in_decimals=2)`: Checks that the student's variable in `student_variable_name` matches the expected value within the given tolerance.
2.  `assert_variable_almost_equals_variable(student_variable_name, expected_variable_name, tolerance_in_decimals=2, delete_afterwards=True)`: Checks that the student's variable in `student_variable_name` matches the expected variable in `expected_variable_name` within the given tolerance.


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
#### 1. Calculate the average marks of the students in `English` subject.

Loop through the list `student_list`, access the marks of the students who have `English` as their favorite subject, and calculate the average marks of those students. Store the average marks in the variable `average_marks_english`.

``` python
average_marks_english = ...
```

+++Solution
Solutions:

``` python
total_marks = 0
count = 0

for student in student_list:
    if student[4] == 'English':
        total_marks += int(student[1])
        count += 1

average_marks_english = total_marks / count
print(average_marks_english)
```

+++Assertions

As the expected output is a float, so we use `assert_variable_almost_equals()` function to assert the solution with the student variable.

Assertion:

``` python
assert_variable_almost_equals("average_marks_english", 52.0)
```
+++


+++Activity 2
#### 2. Calculate the average marks of the students in `Math` subject.

Loop through the list `student_list`, access the marks of the students who have `Math` as their favorite subject, and calculate the average marks of those students. Store the average marks in the variable `average_marks_math`.

``` python
average_marks_math = ...
```

+++Solution
Solutions:

``` python
total_marks = 0
count = 0

for student in student_list:
    if student[4] == 'Math':
        total_marks += int(student[1])
        count += 1

average_marks_math = total_marks / count
print(average_marks_math)
```

+++Assertions

As the expected output is a float, so we use `assert_variable_almost_equals_variable()` function to assert the solution with the student variable.

Assertion:

``` python
expected_average_marks_math = 72.5
assert_variable_almost_equals_variable("average_marks_math", "expected_average_marks_math")
```
+++
