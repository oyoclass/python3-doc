## SciPy

SciPy is a scientific computation library that was made by the author of [NumPy](/extralibs/numpy). In fact, SciPy _uses_ NumPy for its functions. SciPy exists as a separate package built on top of NumPy and further optimizes some commonly used functions in Data Science.

### Examples

#### Linear Algebra

One good reason to use SciPy is that it has an enhanced set of features for linear algebra and matrix operations. Let's use SciPy to extract the eigen values and vectors from a matrix:

```python
from scipy import linalg
import numpy as np
matrix = np.array([[0,1],[-2,-3]])
eigenvals, eigenvects = linalg.eig(matrix)
print(f'matrix: \n{matrix}\n')
print(f'eigenvalues: \n{eigenvals}\n')
print(f'eigenvectors: \n{eigenvects}')
```

Output:

```text
matrix:
[[ 0  1]
 [-2 -3]]

eigenvalues:
[-1.+0.j -2.+0.j]

eigenvectors:
[[ 0.70710678 -0.4472136 ]
 [-0.70710678  0.89442719]]
```

#### Special Functions

SciPy has access to some special functions. One example are the combinatorics calculators:

##### Calculate 5 choose 2 (5C2)

```python
from scipy.special import comb
ans = comb(5, 2, exact = True)
print(ans)
```

Output:

```text
10
```

##### Calculate 5 permutation 2 (5P2)

```python
from scipy.special import perm
ans = perm(5, 2, exact = True)
print(ans)
```

Output:

```text
20
```

### Reference

-   [SciPy](https://docs.scipy.org/doc/scipy/) at _docs.scipy.org_
