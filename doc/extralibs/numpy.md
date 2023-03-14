## NumPy

NumPy is a powerful number processing library, used by data scientists due to it being able to process large amounts of data much faster than native Python. This package works well with data visualization packages like [Matplotlib](../matplotlib/).

NumPy is used as the base of many other libraries like [Pandas](../pandas) and [SciPy](../scipy) and work together with them closely. It is very common for these libraries to take NumPy arrays in as arguments.

### Examples

#### Create and Add Matrices

The most basic function of NumPy is performing math with arrays and matricies:

```python
import numpy
# Create a 4x4 matrix of ones
ones_mat = numpy.ones((4, 4))
# Create a default numpy random number generator
rg = numpy.random.default_rng(1)
# Create a 4x4 matrix of random numbers
random_mat = rg.random((4, 4))
# Add the two matrices together
added_mat = numpy.add(ones_mat, random_mat)

print(f'ones_mat:\n{ones_mat}\n')
print(f'random_mat:\n{random_mat}\n')
print(f'added_mat:\n{added_mat}\n')
```

Output:

```text
ones_mat:
[[1. 1. 1. 1.]
 [1. 1. 1. 1.]
 [1. 1. 1. 1.]
 [1. 1. 1. 1.]]

random_mat:
[[0.51182162 0.9504637  0.14415961 0.94864945]
 [0.31183145 0.42332645 0.82770259 0.40919914]
 [0.54959369 0.02755911 0.75351311 0.53814331]
 [0.32973172 0.7884287  0.30319483 0.45349789]]

added_mat:
[[1.51182162 1.9504637  1.14415961 1.94864945]
 [1.31183145 1.42332645 1.82770259 1.40919914]
 [1.54959369 1.02755911 1.75351311 1.53814331]
 [1.32973172 1.7884287  1.30319483 1.45349789]]
```

#### Create a Sine Wave Graph with Matplotlib

NumPy is also useful for creating data to pass to a rendering library for data visualization, like [Matplotlib](../matplotlib):

```python
import numpy as np
import matplotlib.pyplot as plt

# Get x and y coordinates of sine wave
x = np.arange(0, 4*np.pi, 0.1)
y = np.sin(x)

# Make the graph
plt.plot(x, y)
plt.title('Sine')

# Show the figure.
plt.show()
```

Output:

<img src="../../assets/img/numpy-matplotlib-sine.png" width="400px"/>

### Reference

-   [NumPy](https://numpy.org/doc/stable/) at _numpy.org_
