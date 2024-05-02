In this notebook, you'll learn how to use most used matplotlib assertion functions.
There is only one assertion function for checking the expected figure
with the actual figure.

1. `assert_plt_student_fig_matches_png_fname(student_figure_variable_name, expected_png_fname)`: Checks if student figure object is equals to expected png image.

Load the `utils.py` file to use the assertion functions.

``` python
exec(open("utils.py").read())
```

``` python
df = pd.read_csv('hs_rate_poverty.csv')
df.head()
```



### Activities

Now, with activities examples, you'll learn how to use the assertion functions. We have `df` dataframe that contains the data of high school graduation rates and poverty rates across different U.S. states.

+++Activity 1
##### 1: Plotting and Comparing Socio-Economic Indicators with Matplotlib

Create a visualization featuring two point plots on the same graph:

The first one representing normalized poverty rates, using
`df['normalized_poverty_rate']` and using a blue marker (that is already
provided).

The second one representing normalized high schoool graduation rates,
using `df['normalized_hs_rate']`, and using a red `x` marker (already
provided).

This visualization will enable a comparative analysis of these two
crucial socio-economic indicators across different states using
Matplotlib.

Your visualization should have a size of `(14, 7)` and look something
like:

![](images/plot-1.png)


``` python
# Creating a figure and an axis
fig, ax = plt.subplots(figsize=(14, 7))

# Plotting the data using scatter plots
ax...(..,.., label='High School Graduation Rates', marker='o', color='b')
ax...(..,.. label='Poverty Rates', marker='x', color='r')

# Adding labels and title
ax.set_xlabel('States', fontsize=10, color='blue')
ax.set_ylabel('Normalized Rates')
ax.set_title('Comparison of High School Graduation and Poverty Rates by State')

# Rotating x-axis labels by 90 degrees
ax.set_xticklabels(df['State'], fontsize=8,rotation=90)
# Adding a legend
ax.legend()
```

+++Solution
Solution:

``` python
# Creating a figure and an axis
fig, ax = plt.subplots(figsize=(14, 7))

# Plotting the data using scatter plots
ax.plot(df['State'], df['normalized_hs_rate'], label='High School Graduation Rates', marker='o', color='b')
ax.plot(df['State'], df['normalized_poverty_rate'], label='Poverty Rates', marker='x', color='r')

# Adding labels and title
ax.set_xlabel('States', fontsize=10, color='blue')
ax.set_ylabel('Normalized Rates')
ax.set_title('Comparison of High School Graduation and Poverty Rates by State')

# Rotating x-axis labels by 90 degrees
ax.set_xticklabels(df['State'], fontsize=8,rotation=90)
# Adding a legend
ax.legend()
```

+++Assertions

As we have to assert student variable with expected png image, we will use `assert_plt_student_fig_matches_png_fname()` function.

This is how you can save the figure and assert it with the expected image.

``` python
fig.savefig('activity_solutions_files/expected_plot_1.png')
```

Assertions:

``` python
assert_plt_student_fig_matches_png_fname("fig", 'expected_plot_1.png')
```
+++


+++Activity 2
##### 2: Scatter Plotting Socio-Economic Indicators

Create a scatter plot to visualize and analyze the relationship between
the two key socio-economic indicators: the normalized high school
graduation rate (`normalized_hs_rate`) and the poverty rate
(`normalized_poverty_rate`) across different U.S. states.

Use `normalized_hs_rate` in the X axis and `normalized_poverty_rate` in
the Y axis. Your plot should look something like:

![](images/plot-2.png)


``` python
# Plotting the scatter plot
fig, ax = plt.subplots(figsize=(14, 7))
ax....(..., ...)

# Adding labels and title
ax.set_xlabel('Normalized High School Graduation Rate')
ax.set_ylabel('Normalized Poverty Rate')
ax.set_title('Statewise Comparison of High School Graduation and Poverty Rates')
```

+++Solution
Solution:

``` python
# Plotting the scatter plot
fig, ax = plt.subplots(figsize=(14, 7))
ax.scatter(df['normalized_hs_rate'], df['normalized_poverty_rate'])

# Adding labels and title
ax.set_xlabel('Normalized High School Graduation Rate')
ax.set_ylabel('Normalized Poverty Rate')
ax.set_title('Statewise Comparison of High School Graduation and Poverty Rates')
```


+++Assertions
``` python
fig.savefig('activity_solutions_files/expected_plot_2.png')
```

Assertions:

``` python
assert_plt_student_fig_matches_png_fname("fig", 'expected_plot_2.png')
```
+++
