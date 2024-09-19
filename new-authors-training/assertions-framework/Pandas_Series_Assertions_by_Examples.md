In this you'll learn how to use most used Pandas Series assertion
functions. Below are the functions that are covered.

  1.  `assert_pd_series_variable_equals_variable(student_variable_name, expected_outcome_variable_name)`: Checks that the student's Series in `student_variable_name` matches the variable in `expected_outcome_variable_name`.
  2.  `assert_pd_series_variable_equals_csv(student_variable_name, solution_csv_name, read_csv_kwargs=None)`: Checks that the student's Series in `student_variable_name` matches the Series contained in the solution CSV file named `solution_csv_name`.
  3. `assert_pd_series_variable_equals_pickle(student_variable_name, pickle_name, read_pickle_kwargs=None, series_testing_kwargs=None)`: Checks that the student's Series in `student_variable_name` matches the Series contained in the solution pickle file named `pickle_name`. This used when we have pivoted data or multi-column data.


Load the `utils.py` file to use the assertion functions. 

``` python
exec(open('utils.py').read())
```

``` python
import pandas as pd
```

### Activities

Now, with activities examples, you'll learn how to use the assertion functions.


+++Activity 1
##### 1. Create a student series

Use below data to create a series named `student_data`.

``` python
data = ['Albert', 'John', 'Peter', 'James', 'Robert']
```

```python
student_data = ...
```

+++Solution
Solution:

``` python
data = ['Albert', 'John', 'Peter', 'James', 'Robert']
student_data = pd.Series(data)
```

+++Assertions

As the expected output is small series, so we use `assert_pd_series_variable_equals_variable()` function to assert the solution with the student series.

Assertions:

``` python
expected_output = pd.Series(['Albert', 'John', 'Peter', 'James', 'Robert'])
assert_pd_series_variable_equals_variable('student_data', 'expected_output')
```

Here, we passed first student variable then expected variable.
+++


+++Activity 2
##### 2. Create a prime number series

Create a series named `prime_numbers_series` which contains the first 10,000 prime numbers.

``` python
prime_numbers_series = ...
```

+++Solution
Solution:

``` python
prime_numbers = []
num = 2
while len(prime_numbers) < 10000:
    for i in range(2, num):
        if num % i == 0:
            break
    else:
        prime_numbers.append(num)
    num += 1

prime_numbers_series = pd.Series(prime_numbers)
```

+++Assertions

In previous example, the expected series is small, so we've used `assert_pd_series_variable_equals_variable()` function to assert the solution with the student series but in this example, the expected series is large, so we'll save the expected series to a csv file and then use `assert_pd_series_variable_equals_csv()` function to assert the solution with the csv file.

``` python
prime_numbers_series.to_csv('activity_solutions_files/activity_1.csv', index=False)
```

Assertions:

``` python
assert_pd_series_variable_equals_csv('field_goal_perc', 'activity_1.csv')
```
+++


+++Activity 3
##### 3. Create a student series with index and multi-column data

Create a series named `student_data` with below data and index.

``` python
data = {'Name': ['Albert', 'John', 'Peter', 'James', 'Robert'],
        'Age': [25, 30, 35, 40, 45],
        'City': ['New York', 'Los Angeles', 'Chicago', 'Houston', 'Phoenix']}
index = ['A', 'B', 'C', 'D', 'E']
```

``` python
student_data = ...
```

+++Solution
Solution:

``` python
data = {'Name': ['Albert', 'John', 'Peter', 'James', 'Robert'],
        'Age': [25, 30, 35, 40, 45],
        'City': ['New York', 'Los Angeles', 'Chicago', 'Houston', 'Phoenix']}
index = ['A', 'B', 'C', 'D', 'E']

student_data = pd.Series(data, index=index)
```

+++Assertions

Here, we'll use pickle file to save the expected series and then use `assert_pd_series_variable_equals_pickle()` function to assert the solution with the pickle file.

``` python
student_data.to_pickle('activity_solutions_files/activity_3.pkl')
```

Assertions:

``` python
assert_pd_series_variable_equals_pickle('student_data', 'activity_3.pkl')
```
