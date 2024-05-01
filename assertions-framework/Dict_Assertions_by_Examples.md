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
    version: 3.10.14
  nbformat: 4
  nbformat_minor: 2
  orig_nbformat: 4
---

<div class="cell markdown">

In this notebook, I've covered most used Dictionary assertion functions.
Below are these functions:

1.  `assert_dict_variable_equals_variable(student_variable_name, expected_variable_name, delete_afterwards=True)`
2.  `assert_dict_variable_equals_json(student_variable_name, json_file_name)`
3.  `assert_dict_variable_equals_pickle(student_variable_name, pickle_file_name)`

</div>

<div class="cell code">

``` python
exec(open("utils.py").read())
```

</div>

<div class="cell markdown">

### Activities

</div>

<div class="cell code">

``` python
fruits_data = [('apple', 'red', 0.99), ('banana', 'yellow', 0.59), ('orange', 'orange', 0.79), ('grape', 'purple', 1.29), ('kiwi', 'green', 1.09), ('pineapple', 'yellow', 1.99), ('strawberry', 'red', 0.69), ('watermelon', 'green', 2.49), ('mango', 'orange', 1.49), ('peach', 'orange', 1.79), ('pear', 'green', 0.89), ('plum', 'purple', 0.79), ('raspberry', 'red', 2.99), ('blueberry', 'blue', 3.99), ('blackberry', 'black', 4.99)]
fruits_data
```

</div>

<div class="cell markdown">

##### Activity 1. Create a fruits dictionary

</div>

<div class="cell code">

``` python
# Try your solution here
fruits = ...
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

``` python
fruits = {}
for fruit in fruits_data:
    name = fruit[0]
    color = fruit[1]
    price = fruit[2]
    fruits[name] = {'color': color, 'price': price}

fruits
```

</div>

<div class="cell code">

``` python
# save json file
import json
with open('activity_solutions_files/solution_01.json', 'w') as f:
    json.dump(fruits, f)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
# new assertions
assert_dict_variable_equals_json('fruits', 'solution_01.json')
```

</div>

<div class="cell markdown">

##### Activity 2. Create a Dictionary of Colors and Fruits

</div>

<div class="cell code">

``` python
# Try your solution here
colors = ...
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

``` python
colors = {}

for fruit in fruits:
    name = fruit
    colors.setdefault(fruits[name]['color'], []).append(name)

colors
```

</div>

<div class="cell code">

``` python
# save json file
with open('activity_solutions_files/solution_02.json', 'w') as f:
    json.dump(colors, f)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
# new assertions
assert_dict_variable_equals_json('colors', 'solution_02.json')
```

</div>

<div class="cell markdown">

##### Activity 3. Create a Dictionary of only red color fruits

Store the result in a variable `red_fruits`.

</div>

<div class="cell code">

``` python
# Try your solution here
red_fruits = ...
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code">

``` python
red_fruits = {}

for fruit in fruits:
    name = fruit
    if fruits[name]['color'] == 'red':
        red_fruits[name] = fruits[name]
        
red_fruits
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
expected_red_fruits = {'apple': {'color': 'red', 'price': 0.99},
 'strawberry': {'color': 'red', 'price': 0.69},
 'raspberry': {'color': 'red', 'price': 2.99}}
assert_dict_variable_equals_variable('red_fruits', 'expected_red_fruits')
```

</div>

<div class="cell markdown">

##### Activity 4. Create a Dictionary of only red and blue color fruits

Store the result in a variable `red_blue_fruits`, here the key is the
color and value is the tuple containing two values - color and its
price.

</div>

<div class="cell code">

``` python
# Write your solution here
red_blue_fruits = ...
```

</div>

<div class="cell markdown">

Solution:

</div>

<div class="cell code" execution_count="10">

``` python
red_blue_fruits = {}

for fruit in fruits:
    name = fruit
    if fruits[name]['color'] == 'red' or fruits[name]['color'] == 'blue':
        red_blue_fruits[name] = tuple(fruits[name].values())
        
red_blue_fruits
```

<div class="output execute_result" execution_count="10">

    {'apple': ('red', 0.99),
     'strawberry': ('red', 0.69),
     'raspberry': ('red', 2.99),
     'blueberry': ('blue', 3.99)}

</div>

</div>

<div class="cell code">

``` python
# save in pickle file
import pickle
with open('activity_solutions_files/solution_04.pkl', 'wb') as f:
    pickle.dump(red_blue_fruits, f)
```

</div>

<div class="cell markdown">

Assertions:

</div>

<div class="cell code">

``` python
# new assertions
assert_dict_variable_equals_pickle('red_blue_fruits', 'solution_04.pkl')
```

</div>

<div class="cell markdown">

### The End!

</div>
