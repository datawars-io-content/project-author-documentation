In this notebook, you'll learn how to use most used Pandas Dataframe assertion
functions. Below are these functions:

1.  `assert_pd_dataframe_variable_equals_variable(student_variable_name, expected_variable_name, delete_afterwards=True)`: Checks if student dataframe variable is equals to expected dataframe variable.
2.  `assert_pd_dataframe_variable_equals_csv(student_df_variable_name, colum_name, csv_name, read_csv_kwargs=None, series_testing_kwargs=None)`: Checks if student dataframe variable is equals to expected csv file.
3.  `assert_pd_dataframe_variable_column_equals_csv(student_df_variable_name, colum_name, csv_name, read_csv_kwargs=None, series_testing_kwargs=None)`: Checks if student dataframe variable column is equals to expected csv file.
4.  `assert_pd_dataframe_csv_equals_csv(student_csv_name, expected_csv_name, student_base_dir=".", read_csv_kwargs=None, dataframe_testing_kwargs=None)`: Checks if student csv file is equals to expected csv file.
5. `assert_pd_dataframe_variable_equals_pickle(student_variable_name, pickle_name, read_pickle_kwargs=None, dataframe_testing_kwargs=None)`: Checks if student dataframe variable is equals to expected pickle file. This is used when we have pivoted data or multi-column data in the dataframe.


Load the `utils.py` file to use the assertion functions.

``` python
exec(open("utils.py").read())
```

``` python
import pandas as pd

df = pd.read_csv('Best_Books_Ever.csv')
```

### Activities

Now, with activities examples, you'll learn how to use the assertion functions. We'll use the `df` dataframe that contains the data of best books ever.


+++Activity 1
##### 1. Create a dataframe `student_df` with the following data:

``` python
student_dict = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eva'],
    'Age': [18, 17, 19, 18, 17],
    'Grade': ['A', 'B', 'A', 'B', 'A']
}
```

+++Solution

Solution:

``` python
student_dict = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eva'],
    'Age': [18, 17, 19, 18, 17],
    'Grade': ['A', 'B', 'A', 'B', 'A']
}

student_df = pd.DataFrame(student_dict)
```

+++Assertions

As the expected dataframe is small and we can easily compare it with the student dataframe, we can use `assert_pd_dataframe_variable_equals_variable()` function to assert the solution with the student dataframe.

``` python
expected_student_dict = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eva'],
    'Age': [18, 17, 19, 18, 17],
    'Grade': ['A', 'B', 'A', 'B', 'A']
}
expected_student_df = pd.DataFrame(expected_student_dict)
assert_pd_dataframe_variable_equals_variable('student_df', 'expected_student_df', delete_afterwards=True)
```
+++


+++Activity 2
##### 2. Calculating the Price-to-Rating Ratio

Create a new column `Price-to-Rating Ratio` in the DataFrame that
calculates the price-to-rating ratio for each book. This ratio will help
us understand how the price of a book relates to its average rating.

+++Solution
Solution:

``` python
df['price_to_rating'] = df['price'] / df['rating']
```

+++Assertions

In this activity, we asked student to create a new column in the dataframe. So, we can use `assert_pd_dataframe_variable_column_equals_csv()` function to assert the solution with the student dataframe. We used this function to check the column `price_to_rating` with the expected column in the csv file.

This is how you can save the dataframe to a new csv file.

``` python
# save the dataframe to a new csv file
df.to_csv('activity_solutions_files/sol_01.csv', index=True)
```

Assertions:

``` python
assert_pd_dataframe_variable_column_equals_csv('df', 'price_to_rating', 'sol_01.csv')
```
+++


+++Activity 3
##### Activity 3. Remove the "isbn" Column

The "isbn" column is not needed for our analysis. Write a script to
remove this column from the dataframe.


+++Solution
Solution:

``` python
df.drop(columns='isbn', inplace=True)
```

+++Assertions

In this activity, we asked student to remove the column from the dataframe. So, we can use `assert_pd_dataframe_variable_equals_csv()` function to assert the solution with the student dataframe.

``` python
# save the dataframe to a new csv file
df.to_csv('activity_solutions_files/sol_02.csv', index=True)
```

Assertions:

``` python
assert_pd_dataframe_variable_equals_csv('df', 'sol_02.csv')
```
+++


+++Activity 4
##### Activity 4. Save the updated dataframe in new CSV file

Save the updated dataframe `df` in a new CSV file named
`updated_best_book.csv`. Save this file in current directory only.

> Make sure not to reset the index

+++Solution
Solution:

``` python
# save the dataframe to a new csv file
df.to_csv('updated_best_book.csv', index=False)
```

+++Assertions

In this activity, we asked student to save the dataframe in a new csv file. So, we can use `assert_pd_dataframe_csv_equals_csv()` function to assert the solution with the student dataframe.

This is how you can save the dataframe to a new csv file.

``` python
# save the dataframe to a new csv file
df.to_csv('activity_solutions_files/sol_08.csv', index=False)
```

Assertions:

``` python
read_csv_kwargs = {'index_col': 0}
assert_pd_dataframe_csv_equals_csv('updated_best_book.csv', 'sol_08.csv', read_csv_kwargs=read_csv_kwargs)
```
+++


+++Activity 5

##### Activity 5. Save the updated dataframe in a pickle file

Create a pivoted dataframe `pivot_df` from the `df` dataframe.

+++Solution
Solution:

``` python
pivot_df = df.pivot(index='title', columns='author', values='rating')
```

+++Assertions

In this activity, we asked student to create a pivoted dataframe from the original dataframe. So, we can use `assert_pd_dataframe_variable_equals_pickle()` function to assert the solution with the student dataframe because CSV file can't store the pivoted data.

This is how you can save the dataframe to a new pickle file.

``` python
# save the dataframe to a new pickle file
pivot_df.to_pickle('activity_solutions_files/sol_05.pkl')
```

Assertions:

``` python
assert_pd_dataframe_variable_equals_pickle('pivot_df', 'sol_05.pkl')
```
+++
