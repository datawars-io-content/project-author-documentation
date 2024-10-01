---
expanded: true
order: I
---

In this notebook, you'll learn how to use most used PyTorch assertion functions.

1. `assert_pytorch_tensor_variable_name_equals_serialized(student_variable_name, location)`: Checks if student tensor object is equals to expected tensor. The expected tensor is stored in a pickle file.
2. `assert_pytorch_tensor_variable_name_is_in_expected_device(student_variable_name, expected_device)`: Checks if student tensor object is in expected device. The expected device is a string.

Load the `utils.py` file to use the assertion functions.

``` python
exec(open("utils.py").read())
```


### Activities

Now, with activities examples, you'll learn how to use the assertion functions. 

+++Activity 1
##### 1: Create a 2d PtTorch tensor.

Use below list to create a 2d PyTorch tensor ans store it in a variable `student`.

``` python
data = [[1, 2, 3], [4, 5, 6]]
```

```python
import torch
student = ...
```

+++Solution
Solution:

``` python
import torch
data = [[1, 2, 3], [4, 5, 6]]
student = torch.tensor(data)
print(student)
```

As we have created a tensor, save the tensor in a file using below code in a pickle file.

``` python
import pickle
with open('activity_solutions_files/expected_tensor_1.pt', 'wb') as f:
    pickle.dump(student, f)
```

+++Assertions

``` python
assert_pytorch_tensor_variable_name_equals_serialized('student', 'expected_tensor_1.pt')
```
+++


+++Activity 2
##### 2: Change the device of the tensor.

Change the device of the tensor to `cuda` and store it in a variable `student`.

```python
student = student...
```

+++Solution
Solution:

``` python
student = student.to('cuda')
```

As we have changed the device of the tensor, save the tensor in a file using below code in a pickle file.

``` python
import pickle
with open('activity_solutions_files/expected_tensor_2.pt', 'wb') as f:
    pickle.dump(student, f)
```

+++Assertions

Assertions:

``` python
assert_pytorch_tensor_equals_serialized(student, 'expected_tensor_2.pt')
```
+++
