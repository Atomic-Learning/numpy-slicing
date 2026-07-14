# 1D Arrays

Slicing a 1D NumPy array is very similar to slicing a Python list:

```py-cell
import numpy as np

x = np.array(["a", "b", "c", "d", "e"])

# Start and stop indices
print(x[1:4])
# Start, stop and step
print(x[1:4:2])
```

Just like Python lists, we can omit the start or stop index to slice from the beginning or to the end of the array:

```py-cell
import numpy as np

x = np.array(["a", "b", "c", "d", "e"])

# Slice from the beginning to index 3 (exclusive)
print(x[:3])

# Slice from index 2 (inclusive) to the end
print(x[2:])
```

# Multi-dimensional Arrays

We can also slice multi-dimensional arrays, separating the slice for each dimension with a comma:

```py-cell
import numpy as np

x = np.array([["a", "b", "c"], ["d", "e", "f"], ["g", "h", "i"]])

# Slice the first two rows and the last two columns
print(x[:2, 1:])

# Slice every other entry of the first two rows
print(x[:2, ::2])
```

# Slices as Views

The array returned by slicing a NumPy array is a view of the original array, not a copy. This means that if we modify the slice, the original array will also be modified:

```py-cell
import numpy as np

x = np.array(["a", "b", "c", "d", "e"])
y = x[1:4]
y[0] = "z"
print(x)  # Original array is modified because y is a view
```