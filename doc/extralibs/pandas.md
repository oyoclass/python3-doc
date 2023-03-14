## Pandas

Pandas is a Python library focused on data science and analysis. Pandas is built on top of [NumPy](../numpy) and focuses on working with tables of data called **DataFrames**.

### Examples

#### Creating a DataFrame

We can create a DataFrame in Pandas by simply passing it a dictionary of data:

```python
import random
import pandas as pd

def create_random_array(length, low_bound, high_bound):
    return [random.randint(low_bound, high_bound) for _ in range(length)]

# Values of a DataFrame dictionary must all be of the same length
data = {
    "A": create_random_array(5, 10, 20),
    "B": create_random_array(5, 10, 20),
    "C": create_random_array(5, 10, 20),
    "D": create_random_array(5, 10, 20)
}

dataframe = pd.DataFrame(data)
print(dataframe)
```

Output:

```text
    A   B   C   D
0  13  14  20  19
1  19  18  19  13
2  15  16  14  11
3  12  11  20  17
4  10  20  16  15
```

#### Filtering a DataFrame

Let's take our previous example and add a filter function and pass it to `applymap()`:

```python
import random
import pandas as pd

def create_random_array(length, low_bound, high_bound):
    return [random.randint(low_bound, high_bound) for _ in range(length)]

# Values of a DataFrame dictionary must all be of the same length
data = {
    "A": create_random_array(5, 10, 20),
    "B": create_random_array(5, 10, 20),
    "C": create_random_array(5, 10, 20),
    "D": create_random_array(5, 10, 20)
}
dataframe = pd.DataFrame(data)

# Let's create a filter function to pass to pandas.
# This simple filter will just zero any element that is less than 15:
def min_val_filter(item):
    if item < 15:
        return 0
    return item
filtered_frame = dataframe.applymap(min_val_filter)

print(filtered_frame)
```

Output:

```text
   A   B   C   D
0  0  17   0  16
1  0  20   0   0
2  0   0  18   0
3  0   0  16   0
4  0  20  17  16
```

Note that since our array is randomly populated each run, the results will be different each time.

### Reference

-   [Pandas](https://pandas.pydata.org/docs/) at _pandas.pydata.org_
