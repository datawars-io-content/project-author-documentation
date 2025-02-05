---
label: PyTorch Assertions
expanded: true
order: L
---

In this notebook, you'll learn how to use most used PyTorch assertion functions.

1. `assert_pytorch_tensor_variable_name_equals_serialized(student_variable_name, location)`: Checks if student tensor object is equals to expected tensor. The expected tensor is stored in a pickle file.
2. `assert_pytorch_tensor_variable_name_is_in_expected_device(student_variable_name, expected_device)`: Checks if student tensor object is in expected device. The expected device is a string.
3. `assert_vision_transform_variable_name_equals_serialized(student_variable_name, location, **kwargs)`: Checks if student transformation pipeline object is equals to expected transformation pipeline. The expected transformation pipeline is stored in a pickle file.
4. `assert_dataset_vision_image_folder_variable_name_equals_serialized(student_variable_name, location)`: Checks if student dataset(image directory) image folder object is equals to expected dataset image folder. The expected dataset image folder is stored in a pickle file.


Load the `utils.py` file to use the assertion functions.

``` python
exec(open("utils.py").read())
```


### Activities

Now, with activities examples, you'll learn how to use the assertion functions. 

+++Activity 1
##### 1: Create a 2d PyTorch tensor.

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

or, serialize the tensor using the below code.

``` python
location = 'expected_tensor_1.pt' # Using this, we don't need to mention the activity_solutions_files path in the assertion.
serialize_pickle(student, location)
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

+++Activity 3
##### 3: Test the transformation pipeline.

If student create a transformation pipeline with below parameters, then assert it with the expected transformation pipeline.

``` python
import torchvision.transforms as transforms
student = transforms.Compose([
    transforms.RandomResizedCrop(224),
    transforms.RandomHorizontalFlip(),
    transforms.ToTensor(),
    transforms.Normalize(mean=[0.485, 0.456, 0.406], std=[0.229, 0.224, 0.225])
])
```

+++Solution
Solution:

``` python
import torchvision.transforms as transforms
student = transforms.Compose([
    transforms.RandomResizedCrop(224),
    transforms.RandomHorizontalFlip(),
    transforms.ToTensor(),
    transforms.Normalize(mean=[0.485, 0.456, 0.406], std=[0.229, 0.224, 0.225])
])
```

As we have created a transformation pipeline, save the transformation pipeline in a file using below code in a pickle file.

``` python
location = 'expected_transform_1.pt' # Using this, we don't need to mention the activity_solutions_files path in the assertion.
serialize_pickle(student, location)
```

+++Assertions

Assertions:

``` python
assert_vision_transform_variable_name_equals_serialized('student', 'expected_transform_1.pt')
```
+++


+++Activity 4
##### 4: Test the dataset image folder.

If student create a dataset image folder with below parameters, then assert it with the expected dataset image folder.

``` python
import torchvision.datasets as datasets
student = datasets.ImageFolder(root='path/to/data', transform=student)
```

> Here, the `path/to/data` is the path to the image folder and `student` is the transformation pipeline created in the previous activity example.

+++Solution
Solution:

``` python
import torchvision.datasets as datasets
student = datasets.ImageFolder(root='path/to/data', transform=student)
```

As we have created a dataset image folder, save the dataset image folder in a file using below code in a pickle file.

``` python
location = 'expected_dataset_image_folder_1.pt' # Using this, we don't need to mention the activity_solutions_files path in the assertion.
serialize_pickle(student, location)
```

+++Assertions

Assertions:

``` python
assert_dataset_vision_image_folder_variable_name_equals_serialized('student', 'expected_dataset_image_folder_1.pt')
```

