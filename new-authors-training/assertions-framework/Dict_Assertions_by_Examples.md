---
expanded: true
order: D
---


In this you'll learn how to use most used Dictionary assertion
functions. Below are the functions that are covered.

  1.  `assert_dict_variable_equals_variable(student_variable_name, expected_variable_name, delete_afterwards=True)`: Checks that the student's dictionary in `student_variable_name` matches the dictionary in `expected_variable_name`.
  2.  `assert_dict_variable_equals_json(student_variable_name, json_file_name)`: Checks that the student's dictionary in `student_variable_name` matches the dictionary contained in the solution JSON file named `json_file_name`.
  3.  `assert_dict_variable_equals_pickle(student_variable_name, pickle_file_name)`: Checks that the student's dictionary in `student_variable_name` matches the dictionary contained in the solution pickle file named `pickle_file_name`.

Load the `utils.py` file to use the assertion functions.

``` python
exec(open("utils.py").read())
```

### Activities

Now, with activities examples, you'll learn how to use the assertion functions.

We'll use the below fruits data for the activities.

``` python
fruits_data = [('apple', 'red', 0.99), ('banana', 'yellow', 0.59), ('orange', 'orange', 0.79), ('grape', 'purple', 1.29), ('kiwi', 'green', 1.09), ('pineapple', 'yellow', 1.99), ('strawberry', 'red', 0.69), ('watermelon', 'green', 2.49), ('mango', 'orange', 1.49), ('peach', 'orange', 1.79), ('pear', 'green', 0.89), ('plum', 'purple', 0.79), ('raspberry', 'red', 2.99), ('blueberry', 'blue', 3.99), ('blackberry', 'black', 4.99)]
fruits_data
```

+++Activity 1
##### 1. Create a student dictionary

Use below data to create a dictionary named `student_dict`.

``` python
student_name = ['Albert', 'John', 'Peter', 'James', 'Robert']
student_age = [23, 24, 22, 25, 23]
student_city = ['New York', 'Los Angeles', 'Chicago', 'Houston', 'Phoenix']
```

Expected Output:

``` python
{'Albert': {'age': 23, 'city': 'New York'},
 'John': {'age': 24, 'city': 'Los Angeles'},
 'Peter': {'age': 22, 'city': 'Chicago'},
 'James': {'age': 25, 'city': 'Houston'},
 'Robert': {'age': 23, 'city': 'Phoenix'}}
```

+++Solution
Solution:

``` python
student_name = ['Albert', 'John', 'Peter', 'James', 'Robert']
student_age = [23, 24, 22, 25, 23]
student_city = ['New York', 'Los Angeles', 'Chicago', 'Houston', 'Phoenix']

student_dict = {}

for i in range(len(student_name)):
    student_dict[student_name[i]] = {'age': student_age[i], 'city': student_city[i]}

student_dict
```

+++Assertions

As the expected output is small dictionary, so we use `assert_dict_variable_equals_variable()` function to assert the solution with the student dictionary.

Assertions:

``` python
expected_output = {'Albert': {'age': 23, 'city': 'New York'},
 'John': {'age': 24, 'city': 'Los Angeles'},
 'Peter': {'age': 22, 'city': 'Chicago'},
 'James': {'age': 25, 'city': 'Houston'},
 'Robert': {'age': 23, 'city': 'Phoenix'}}
assert_dict_variable_equals_variable('student_dict', 'expected_output')
```
+++


+++Activity 2
##### 2. Create a fruits dictionary

Use the `fruits_data` list to create a dictionary named `fruits` where the key is the fruit name and the value is a dictionary containing the color and price of the fruit.

Expected Output:

``` python
{'apple': {'color': 'red', 'price': 0.99},
 'banana': {'color': 'yellow', 'price': 0.59},
 'orange': {'color': 'orange', 'price': 0.79},
 'grape': {'color': 'purple', 'price': 1.29},
 ...
}
```

``` python
# Try your solution here
fruits = ...
```

+++Solution
Solution:

``` python
fruits = {}
for fruit in fruits_data:
    name = fruit[0]
    color = fruit[1]
    price = fruit[2]
    fruits[name] = {'color': color, 'price': price}

fruits
```

+++Assertions

In the previous activity, we used `assert_dict_variable_equals_variable()` function to assert the solution with the student dictionary. But here the expected output is large, so we use `assert_dict_variable_equals_json()` function to assert the solution with the student dictionary.

``` python
# save json file
import json
with open('activity_solutions_files/solution_01.json', 'w') as f:
    json.dump(fruits, f)
```

Assertions:

``` python
# new assertions
assert_dict_variable_equals_json('fruits', 'solution_01.json')
```
+++


+++Activity 3
##### 3. Create a Dictionary of only red color fruits

Store the result in a variable `red_fruits`.

``` python
# Try your solution here
red_fruits = ...
```

+++Solution
Solution:

``` python
red_fruits = {}

for fruit in fruits:
    name = fruit
    if fruits[name]['color'] == 'red':
        red_fruits[name] = fruits[name]
        
red_fruits
```

+++Assertions
Assertions:

``` python
expected_red_fruits = {'apple': {'color': 'red', 'price': 0.99},
 'strawberry': {'color': 'red', 'price': 0.69},
 'raspberry': {'color': 'red', 'price': 2.99}}
assert_dict_variable_equals_variable('red_fruits', 'expected_red_fruits')
```
+++


+++Activity 4
##### 4. Create a Dictionary of only red and blue color fruits

Store the result in a variable `red_blue_fruits`, here the key is the
color and value is the tuple containing two values - color and its
price.

``` python
# Write your solution here
red_blue_fruits = ...
```

+++Solution
Solution:

``` python
red_blue_fruits = {}

for fruit in fruits:
    name = fruit
    if fruits[name]['color'] == 'red' or fruits[name]['color'] == 'blue':
        red_blue_fruits[name] = tuple(fruits[name].values())
        
red_blue_fruits
```

    {
      'apple': ('red', 0.99),
      'strawberry': ('red', 0.69),
      'raspberry': ('red', 2.99),
      'blueberry': ('blue', 3.99)
    }
    

+++Assertions

As we know that when we save tuple in json file, it will be saved as list. So, we use pickle file to save the expected output and then use `assert_dict_variable_equals_pickle()` function to assert the solution with the student dictionary.

``` python
# save in pickle file
import pickle
with open('activity_solutions_files/solution_04.pkl', 'wb') as f:
    pickle.dump(red_blue_fruits, f)
```

Assertions:

``` python
# new assertions
assert_dict_variable_equals_pickle('red_blue_fruits', 'solution_04.pkl')
```
+++
