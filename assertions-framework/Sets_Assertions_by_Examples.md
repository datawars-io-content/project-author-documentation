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
    version: 3.8.18
  nbformat: 4
  nbformat_minor: 2
  orig_nbformat: 4
---

<div class="cell markdown">

In this notebook, I've covered most used Sets assertion functions. Below
are these functions:

1.  `assert_set_variable_equals_variable(student_variable_name, expected_variable_name, delete_afterwards=True)`
2.  `assert_set_variable_equals_json(student_variable_name, json_file_name)`
3.  `assert_set_variable_equals_pickle(student_variable_name, pickle_file_name)`

</div>

<div class="cell code">

``` python
exec(open("utils.py").read())
```

</div>

<div class="cell markdown">

### Warm Up Activities

</div>

<div class="cell markdown">

##### Activity 1. Course Enrollments and Common Students

</div>

<div class="cell code">

``` python
# Try your solution here
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

``` python
course_a_students = {"Alice", "Bob", "Carol", "David"}
course_b_students = {"Bob", "David", "Eve", "Frank"}
common_students = course_a_students.intersection(course_b_students)
```

</div>

<div class="cell code">

``` python
common_students
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
# new assertions
expected_common_students = {"Bob", "David"}
assert_set_variable_equals_variable("common_students", "expected_common_students")
```

</div>

<div class="cell markdown">

##### Activity 2. Unique Keywords in Articles

</div>

<div class="cell code">

``` python
# Try your solution here
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

``` python
article1_keywords = {"data", "analysis", "Python", "statistics"}
article2_keywords = {"machine learning", "Python", "data", "programming"}
unique_keywords = article1_keywords.symmetric_difference(article2_keywords)
```

</div>

<div class="cell code">

``` python
unique_keywords
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
# new assertions
expected_unique_keywords = {"analysis", "machine learning", "programming", "statistics"}
assert_set_variable_equals_variable("unique_keywords", "expected_unique_keywords")
```

</div>

<div class="cell markdown">

### Activities on Badge Data

</div>

<div class="cell code">

``` python
import json

# Load badge details from the JSON file
with open("badge_details.json", "r") as json_file:
    badge_details = json.load(json_file)

# Recreate badge sets from the loaded data
data_novice_badge = set(badge_details["Data Novice"])
data_explorer_badge = set(badge_details["Data Explorer"])
analytics_enthusiast_badge = set(badge_details["Analytics Enthusiast"])

# Display the first 5 details of each badge
print("Data Novice:", list(data_novice_badge)[:5])
print("Data Explorer:", list(data_explorer_badge)[:5])
print("Analytics Enthusiast:", list(analytics_enthusiast_badge)[:5])
```

</div>

<div class="cell markdown">

Above, we display as python lists because sets are not subscriptable.

</div>

<div class="cell markdown">

##### Activity 3. Add New Student to Data Novice Badge

Incorporate the new student named Sam into the Data Novice badge group.

</div>

<div class="cell code">

``` python
# Try your solution here
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

``` python
data_novice_badge.add("Sam")
```

</div>

<div class="cell code">

``` python
# save in pickle
import pickle
with open("activity_solutions_files/solution_03.pickle", "wb") as pickle_file:
    pickle.dump(data_novice_badge, pickle_file)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
# new assertions
assert_set_variable_equals_pickle("data_novice_badge", "solution_03.pickle")
```

</div>

<div class="cell markdown">

##### Activity 4. Find the union of 'Data Explorer' and 'Analytics Enthusiast' badge sets.

</div>

<div class="cell code">

``` python
# Try your solution here
union_de_ae = ...
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

``` python
union_de_ae = data_explorer_badge.union(analytics_enthusiast_badge)
```

</div>

<div class="cell code">

``` python
union_de_ae
```

</div>

<div class="cell code">

``` python
# save in pickle
import pickle
with open("activity_solutions_files/solution_04.pickle", "wb") as pickle_file:
    pickle.dump(union_de_ae, pickle_file)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
# new assertions
assert_set_variable_equals_pickle("union_de_ae", "solution_04.pickle")
```

</div>

<div class="cell markdown">

### The End!

</div>
