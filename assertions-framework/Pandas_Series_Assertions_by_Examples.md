In this you'll learn how to use most used Pandas Series assertion
functions. Below are the functions that are covered.

  1.  `assert_pd_series_variable_equals_variable()`
  2.  `assert_pd_series_variable_equals_csv()`


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

