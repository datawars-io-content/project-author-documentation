---
label: NumPy Assertions
expanded: true
order: J
---

# NumPy Array Assertion Functions

In this notebook, you’ll learn how to use the most common **NumPy array assertion functions**. Below are these functions:

1. **`assert_variable_type_np_array(var_name)`**  
   Checks whether a variable in `globals()` is a NumPy array (i.e., `np.ndarray`).

2. **`assert_np_array_equal(student_array, expected_array, exact=True, rtol=1e-7, atol=0)`**  
   Compares two arrays either **exactly** or **approximately** (if `exact=False`).  
   - **Exact** checks each element is identical.  
   - **Approximate** uses tolerances (`rtol`, `atol`) for floating-point comparisons.

3. **`assert_np_array_variable_equals_variable(student_var_name, expected_var_name, **kwargs)`**  
   Verifies two **global** variables contain matching arrays. Optionally set `exact=False` for approximate checks.

4. **`assert_np_array_variable_equals(student_var_name, expected_array, **kwargs)`**  
   Compares a **global variable** (student’s result) to an **in-memory array** (teacher’s or reference result).

5. **`assert_np_array_equals_pickle(student_array, pickle_name, read_pickle_kwargs=None, array_testing_kwargs=None)`**  
   Loads a **pickle** file containing a NumPy array, then compares it to `student_array`.

6. **`assert_np_array_variable_equals_pickle(student_variable_name, pickle_name, read_pickle_kwargs=None, array_testing_kwargs=None)`**  
   Loads a pickle file containing a NumPy array, then compares it to a **global** variable named `student_variable_name`.

7. **`assert_np_array_variable_equals_parquet(student_variable_name, parquet_name, read_parquet_kwargs=None, array_testing_kwargs=None)`**  
   Loads a **Parquet** file containing a NumPy array, then compares it to a **global** variable named `student_variable_name`.

8. **`assert_np_array_variable_equals_npy(student_variable_name, npy_name, array_testing_kwargs=None)`**  
   Loads a **.npy** file containing a NumPy array, then compares it to a **global** variable named `student_variable_name`.

---

## Loading the Utility

To use these assertion functions, ensure they are defined or imported in your notebook:

``` python
exec(open("utils.py").read())
```

Now you can start asserting student solutions with your reference arrays or data files.

---

## Activities

Below are sample **activities** demonstrating typical usage of these NumPy assertion functions. Each activity shows an example **solution** and the **assertion** that validates it.

+++Activity 1
### 1. Basic Variable Type Check

**Task**: Create a global variable `my_array` that should be a **NumPy array**. If it’s not (e.g., a list, dict, etc.), it should fail.

+++Solution

```python
my_array = np.array([10, 20, 30])
```

+++Assertions

```python
assert_variable_type_np_array("my_array")
```

If `my_array` isn’t found in `globals()` or is not an `np.ndarray`, it raises an `AssertionError`.

+++

---

+++Activity 2
### 2. Exact Element-by-Element Comparison

**Task**: Create an array named `student_arr` that exactly matches `[1, 2, 3]`.

+++Solution

```python
student_arr = np.array([1, 2, 3])
```

+++Assertions

```python
expected_arr = np.array([1, 2, 3])
assert_np_array_equal(student_arr, expected_arr)
```

Because we didn’t pass `exact=False`, the check is performed **element-by-element** with no tolerance for floating-point differences.

+++

---

+++Activity 3
### 3. Approximate Floating-Point Comparison

**Task**: Create a variable `floats_approx` close to `[1.0, 2.0, 3.0]` but with small floating differences.

+++Solution

```python
floats_approx = np.array([1.00001, 2.0001, 3.0])
```

+++Assertions

```python
expected = np.array([1.0, 2.0, 3.0])
# Use approximate comparison: exact=False, small rtol
assert_np_array_equal(floats_approx, expected, exact=False, rtol=1e-3)
```

If the differences are within `rtol=1e-3`, the test passes.

+++

---

+++Activity 4
### 4. Comparing Two Global Variables

**Task**: Suppose you produce two arrays, `student_result` and `expected_result`, in `globals()`. Ensure they match exactly.

+++Solution

```python
student_result = np.array([4, 5, 6])
expected_result = np.array([4, 5, 6])
```

+++Assertions

```python
assert_np_array_variable_equals_variable("student_result", "expected_result")
```

After the assertion, `expected_result` is **deleted** from `globals()` to avoid polluting the environment.

+++

---

+++Activity 5
### 5. Using Pickle for Data

**Task**: Load a pickle file named `array_data.pkl` that contains a 2D array, and store it in a variable `student_matrix`.

+++Solution

```python
student_matrix = np.array([[1, 2], [3, 4]])
```

```python
# Save the array in a pickle file
import pickle

with open('array_data.pkl', 'rb') as f:
    student_matrix = pickle.load(f)
```

+++Assertions

```python
# If we want to directly compare a loaded array to an in-memory expected array:
expected_matrix = np.array([[1, 2], [3, 4]])
assert_np_array_equal(student_matrix, expected_matrix)

# Alternatively, if we want to test student_matrix against the same pickle file:
assert_np_array_equals_pickle(student_matrix, 'array_data.pkl')
```

This ensures the student’s loaded array matches the **original** in the pickle.

+++

---

+++Activity 6
### 6. Comparing a Global Variable Against a Pickle

**Task**: Suppose the student’s code populates `my_pickled_data` in `globals()` and you want to confirm it matches the official reference data stored in `official_data.pkl`.

+++Solution

```python
# Student code might do:
my_pickled_data = np.array([[7, 8], [9, 10]])
# or maybe they loaded it from a pickle
```

```python
# Save it in a pickle file
import pickle

with open('official_data.pkl', 'wb') as f:
    pickle.dump(my_pickled_data, f)
```

+++Assertions

```python
assert_np_array_variable_equals_pickle(
    student_variable_name="my_pickled_data",
    pickle_name="official_data.pkl"
)
```

If the file is missing, or if the unpickled data is not a NumPy array, or if the arrays differ in shape or values, it raises `AssertionError`.


+++

---

+++Activity 7
### 7. Loading a NumPy Array from a Parquet File

**Task**: Load a Parquet file named `data.parquet` that contains a NumPy array, and store it in a variable `student_data`.

+++Solution

```python
student_data = np.array([[11, 12], [13, 14]])
```

```python
# Save the array in a Parquet file
import pandas as pd

df = pd.DataFrame(student_data)
df.to_parquet('data.parquet')
```

+++Assertions

```python
assert_np_array_variable_equals_parquet(
    student_variable_name="student_data",
    parquet_name="data.parquet"
)
```

This assertion checks if the student’s array matches the one stored in the Parquet file.

+++

---

+++Activity 8

### 8. Loading a NumPy Array from a .npy File

**Task**: Load a NumPy array from a file named `data.npy` and store it in a variable `student_data`.

+++Solution

```python
student_data = np.array([[15, 16], [17, 18]])
```

```python
# Save the array in a .npy file
np.save('data.npy', student_data)
```

+++Assertions

```python
assert_np_array_variable_equals_npy(
    student_variable_name="student_data",
    npy_name="data.npy"
)
```

This assertion checks if the student’s array matches the one stored in the .npy file.

+++

---

## Additional Notes

- Pass `exact=False, rtol=..., atol=...` to any of these functions if you need **approximate** floating-point comparisons.
- If your pickle contains something other than a NumPy array (e.g., a Python list), `AssertionError` is raised.
- If you want to compare arrays with **complex** data types or **object** arrays, these functions still work; any mismatch in shape or values triggers a fail.