---
expanded: true
order: E
---

In this notebook, you'll learn how to use most used Sets assertion functions. Below
are these functions:

1.  `assert_set_variable_equals_variable(student_variable_name, expected_variable_name, delete_afterwards=True)`: Checks if student set variable is equals to expected set variable.
2.  `assert_set_variable_equals_json(student_variable_name, json_file_name)`: Checks if student set variable is equals to expected json file.
3.  `assert_set_variable_equals_pickle(student_variable_name, pickle_file_name)`: Checks if student set variable is equals to expected pickle file.


Load the `utils.py` file to use the assertion functions.

``` python
exec(open("utils.py").read())
```


### Activities

Now, with activities examples, you'll learn how to use the assertion functions.

+++Activity 1
##### 1. Course Enrollments and Common Students

You have two sets of students enrolled in two different courses. The sets are as follows:

``` python  
course_a_students = {"Alice", "Bob", "Carol", "David"}
course_b_students = {"Bob", "David", "Eve", "Frank"}
```

Find the common students enrolled in both courses.

``` python
# Try your solution here
```

+++Solution
Solution:

``` python
course_a_students = {"Alice", "Bob", "Carol", "David"}
course_b_students = {"Bob", "David", "Eve", "Frank"}
common_students = course_a_students.intersection(course_b_students)
```

+++Assertions

As the expected set is small and have only few elements, we can easily compare it with the student set, we can use `assert_set_variable_equals_variable()` function to assert the solution with the student set.
Assertions:

``` python
expected_common_students = {"Bob", "David"}
assert_set_variable_equals_variable("common_students", "expected_common_students")
```
+++


### Activities on Badge Data

For other assertions examples, we will use the badge data. The badge data is stored in a JSON file named `badge_details.json`. The JSON file contains the details of three badges: Data Novice, Data Explorer, and Analytics Enthusiast. Each badge has a set of students who have earned that badge.(This dataset is large around 10000+ badge holders)

``` python
import json

# Load badge details from the JSON file
with open("badge_details.json", "r") as json_file:
    badge_details = json.load(json_file)

# Recreate badge sets from the loaded data
data_novice_badge = set(badge_details["Data Novice"])
data_explorer_badge = set(badge_details["Data Explorer"])
analytics_enthusiast_badge = set(badge_details["Analytics Enthusiast"])
```

+++Activity 2
##### 2. Add New Student to Data Novice Badge

Incorporate the new student named Sam into the Data Novice badge group.

+++Solution
Solution:

``` python
data_novice_badge.add("Sam")
```

+++Assertions

As we added only one student to set but the set is quite large(10000+ elements), we can save the set in a pickle file and assert it with the expected pickle file using `assert_set_variable_equals_pickle()` function.

This is how you can save the set in a pickle file.

``` python
# save in pickle
import pickle
with open("activity_solutions_files/solution_03.pickle", "wb") as pickle_file:
    pickle.dump(data_novice_badge, pickle_file)
```

Assertions:

``` python
assert_set_variable_equals_pickle("data_novice_badge", "solution_03.pickle")
```
+++