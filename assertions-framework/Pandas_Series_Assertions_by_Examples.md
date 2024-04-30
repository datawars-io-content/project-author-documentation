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
    version: 3.8.0
  nbformat: 4
  nbformat_minor: 5
---

<div class="cell markdown">

In this notebook, I've covered most used Pandas Series assertion
functions. Below are the functions that I've covered in this notebook.

1.  `assert_pd_series_variable_equals_csv()`

</div>

<div class="cell code">

``` python
exec(open('utils.py').read())
```

</div>

<div class="cell code">

``` python
import pandas as pd
```

</div>

<div class="cell code">

``` python
df = pd.read_csv('nba_player_stats_1985.csv', index_col='Player')
```

</div>

<div class="cell code">

``` python
df.head()
```

</div>

<div class="cell code">

``` python
# Game info
games_played = df['G']
minutes_played = df['MP']

# Field Goals info
field_goals = df['FG']
field_goals_attempts = df['FGA']

# Free Throws info
free_throws = df['FT']
free_throws_attempts = df['FTA']
```

</div>

<div class="cell markdown">

### Activities

</div>

<div class="cell markdown">

##### Activity 1. Calculate field goal accuracy

</div>

<div class="cell code">

``` python
field_goal_perc = ...
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code" scrolled="true">

``` python
field_goal_perc = (field_goals / field_goals_attempts) * 100
field_goal_perc.head()
```

</div>

<div class="cell code">

``` python
field_goal_perc.to_csv('activity_solutions_files/activity_1.csv',)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
assert_pd_series_variable_equals_csv('field_goal_perc', 'activity_1.csv')
```

</div>

<div class="cell markdown">

##### 2. Field goals per Game

</div>

<div class="cell code">

``` python
field_goals_per_game = ...
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

``` python
field_goals_per_game = field_goals / games_played
```

</div>

<div class="cell code">

``` python
field_goals_per_game.to_csv('activity_solutions_files/activity_2.csv',)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
assert_pd_series_variable_equals_csv('field_goals_per_game', 'activity_2.csv')
```

</div>

<div class="cell markdown">

##### 3. Calculate "Total Points"

</div>

<div class="cell code">

``` python
total_points = ...
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

``` python
total_points = (field_goals * 2) + free_throws
```

</div>

<div class="cell code">

``` python
total_points.to_csv('activity_solutions_files/activity_3.csv',)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
assert_pd_series_variable_equals_csv('total_points', 'activity_3.csv')
```

</div>

<div class="cell markdown">

### The End!

</div>
