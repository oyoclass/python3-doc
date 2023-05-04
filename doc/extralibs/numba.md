## numba

`numba` is a Just-In-Time compiler for Python array and numerical functions that gives you the power to speed up your applications with high performance functions written directly in Python<sup>[1]</sup>.

### Examples

The following sample code is taken from the `numba` official documentation<sup>[2]</sup>. It first defines a `go_fast` function with using the `tanh` function of `numpy`, then simply adds a `@jit` decorator to speed up the code execution.

```python
from numba import jit
import numpy as np

x = np.arange(100).reshape(10, 10)

@jit(nopython=True) 
def go_fast(a):
    trace = 0.0
    for i in range(a.shape[0]):   # Numba likes loops
        trace += np.tanh(a[i, i]) # Numba likes NumPy functions
    return a + trace              # Numba likes NumPy broadcasting

print(go_fast(x))
```

For more examples, please head to `numba` official documentation<sup>[2]</sup>.


### Reference
* \[1\]: [https://numba.readthedocs.io/en/stable/user/overview.html](https://numba.readthedocs.io/en/stable/user/overview.html)
* \[2\]: [https://numba.readthedocs.io/](https://numba.readthedocs.io/)