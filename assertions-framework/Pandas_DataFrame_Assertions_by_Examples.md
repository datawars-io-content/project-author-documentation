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
    version: 3.11.0
  nbformat: 4
  nbformat_minor: 4
---

<div class="cell markdown">

In this notebook, I've covered most used Pandas Dataframe assertion
functions. Below are these functions:

1.  `assert_pd_dataframe_variable_column_equals_csv()`
2.  `assert_pd_dataframe_variable_equals_csv()`
3.  `assert_pd_dataframe_variable_equals_variable()`
4.  `assert_pd_dataframe_csv_equals_csv()`

</div>

<div class="cell code" tags="[]">

``` python
exec(open("utils.py").read())
```

</div>

<div class="cell markdown">

### Import the libraries and load the dataset

</div>

<div class="cell code" tags="[]">

``` python
import pandas as pd

df = pd.read_csv('Best_Books_Ever.csv')
```

</div>

<div class="cell markdown">

### Activities

</div>

<div class="cell markdown">

##### Activity 1. Calculating the Price-to-Rating Ratio

Create a new column `Price-to-Rating Ratio` in the DataFrame that
calculates the price-to-rating ratio for each book. This ratio will help
us understand how the price of a book relates to its average rating.

</div>

<div class="cell code">

``` python
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code" tags="[]">

``` python
df['price_to_rating'] = df['price'] / df['rating']
```

</div>

<div class="cell code">

``` python
# save the dataframe to a new csv file
df.to_csv('activity_solutions_files/sol_01.csv', index=True)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code" tags="[]">

``` python
assert_pd_dataframe_variable_column_equals_csv('df', 'price_to_rating', 'sol_01.csv')
```

</div>

<div class="cell markdown">

##### Activity 2. Remove the "isbn" Column

The "isbn" column is not needed for our analysis. Write a script to
remove this column from the dataframe.

</div>

<div class="cell code">

``` python
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code" tags="[]">

``` python
df.drop(columns='isbn', inplace=True)
```

</div>

<div class="cell code" tags="[]">

``` python
# save the dataframe to a new csv file
df.to_csv('activity_solutions_files/sol_02.csv', index=True)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code" tags="[]">

``` python
assert_pd_dataframe_variable_equals_csv('df', 'sol_02.csv')
```

</div>

<div class="cell markdown">

##### Activity 3. Remove the Rows with Missing Values

Write a script to extract the publication year from the `publishDate`
column and create a new column named `YearPublished` in the dataframe.

</div>

<div class="cell code">

``` python
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

``` python
df['YearPublished'] = df['publishDate'].str.extract(r'(\d{4})')
```

</div>

<div class="cell code">

``` python
# save the dataframe to a new csv file
df.to_csv('activity_solutions_files/sol_03.csv', index=True)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
read_csv_kwargs = {'index_col': 0, 'dtype': {'YearPublished': 'int32'}}
assert_pd_dataframe_variable_column_equals_csv('df', 'YearPublished', 'sol_03.csv', read_csv_kwargs=read_csv_kwargs)
```

</div>

<div class="cell markdown">

##### Activity 4. Filter Books with Ratings Above 4.5

Create a new dataframe that only include books with ratings above 4.5.
Name this new dataframe `best_books`.

</div>

<div class="cell code">

``` python
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

``` python
best_books = df[df['rating'] >= 4.5]
```

</div>

<div class="cell code">

``` python
# save the dataframe to a new csv file
best_books.to_csv('activity_solutions_files/sol_04.csv', index=True)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
read_csv_kwargs = {'index_col': 0, 'dtype': {'YearPublished': 'int32'}}
assert_pd_dataframe_variable_equals_csv('best_books', 'sol_04.csv', read_csv_kwargs=read_csv_kwargs)
```

</div>

<div class="cell markdown">

##### Activity 5. Drop Books with Fewer than 100 Pages

Some entries in the dataset might represent short stories or other short
works. For this activity, remove all rows from the dataframe where the
number of pages is less than 100.

</div>

<div class="cell code">

``` python
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

``` python
df = df[df['pages'] >= 100]
```

</div>

<div class="cell markdown">

This line of code removes all rows from the dataframe where the number
of pages is less than 100.

</div>

<div class="cell code">

``` python
# save the dataframe to a new csv file
df.to_csv('activity_solutions_files/sol_05.csv', index=True)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
read_csv_kwargs = {'index_col': 0, 'dtype': {'YearPublished': 'int32'}}
assert_pd_dataframe_variable_equals_csv('df', 'sol_05.csv', read_csv_kwargs=read_csv_kwargs)
```

</div>

<div class="cell markdown">

##### Activity 6. Flag Books with multiple Awards

Create a new column `MultipleAwards` that flags books that have won
multiple awards. If a book has won more than one award, set the value of
`MultipleAwards` to `True`; otherwise, set it to `False`.

</div>

<div class="cell code">

``` python
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

``` python
df['MultipleAwards'] = df['awards'].apply(lambda x: len(eval(x)) > 1)
```

</div>

<div class="cell code">

``` python
# save the dataframe to a new csv file
df.to_csv('activity_solutions_files/sol_06.csv', index=True)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
read_csv_kwargs = {'index_col': 0}
assert_pd_dataframe_variable_column_equals_csv('df', 'MultipleAwards', 'sol_06.csv', read_csv_kwargs=read_csv_kwargs)
```

</div>

<div class="cell markdown">

##### Activity 7. Adding a New Book Entry

Add a new book entry to the dataframe with the following details:

``` python
new_boos = {
    "bookID": 10000,
    "title": "The Great Gatsby",
    "author": "F. Scott Fitzgerald",
}
```

> Add this new entry to the index `len(df)`.

</div>

<div class="cell code">

``` python
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

``` python
new_book = {
    "bookID": 10000,
    "title": "The Great Gatsby",
    "author": "F. Scott Fitzgerald"
    }
new_df = pd.DataFrame(new_book, index=[len(df)])
df = pd.concat([df, new_df])    
```

</div>

<div class="cell code">

``` python
# save the dataframe to a new csv file
df.to_csv('activity_solutions_files/sol_07.csv', index=True)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
read_csv_kwargs = {'index_col': 0}
assert_pd_dataframe_variable_equals_csv('df', 'sol_07.csv', read_csv_kwargs=read_csv_kwargs)
```

</div>

<div class="cell markdown">

##### Activity 8. Save the updated dataframe in new CSV file

Save the updated dataframe `df` in a new CSV file named
`updated_best_book.csv`. Save this file in current directory only.

> Make sure not to reset the index

</div>

<div class="cell code">

``` python
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code" tags="[]">

``` python
# save the dataframe to a new csv file
df.to_csv('updated_best_book.csv', index=False)
```

</div>

<div class="cell code" tags="[]">

``` python
# save the dataframe to a new csv file
df.to_csv('activity_solutions_files/sol_08.csv', index=False)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code" tags="[]">

``` python
read_csv_kwargs = {'index_col': 0}
assert_pd_dataframe_csv_equals_csv('updated_best_book.csv', 'sol_08.csv', read_csv_kwargs=read_csv_kwargs)
```

</div>

<div class="cell markdown">

##### Activity 9. Save the dataframe in CSV file.

Use the below dictionary and first convert this dictionary into
dataframe and store it in a dataframe `student_df` and then save this
dataframe in a CSV file called `student_data.csv`.

``` python
student_dict = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eva'],
    'Age': [18, 17, 19, 18, 17],
    'Grade': ['A', 'B', 'A', 'B', 'A']
}
```

</div>

<div class="cell code">

``` python
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code" tags="[]">

``` python
import pandas as pd

# Step 1: Given dictionary
student_dict = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eva'],
    'Age': [18, 17, 19, 18, 17],
    'Grade': ['A', 'B', 'A', 'B', 'A']
}

# Step 2: Convert the dictionary into a DataFrame
student_df = pd.DataFrame(student_dict)

# Step 3: Save the DataFrame to a CSV file
student_df.to_csv('student_data.csv', index=False)
```

</div>

<div class="cell code" tags="[]">

``` python
student_df.to_csv('activity_solutions_files/sol_09.csv', index=False)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code" tags="[]">

``` python
student_dict = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eva'],
    'Age': [18, 17, 19, 18, 17],
    'Grade': ['A', 'B', 'A', 'B', 'A']
}

expected_student_df = pd.DataFrame(student_dict)
assert_pd_dataframe_variable_equals_variable('student_df', 'expected_student_df', delete_afterwards=True)

assert_pd_dataframe_csv_equals_csv('student_data.csv', 'sol_09.csv')
```

</div>

<div class="cell markdown">

### The End!

</div>
