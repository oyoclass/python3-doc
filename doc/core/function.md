## Functions
Most of the functions work the same way in both Python2 and Python3. However, there are a few functions that have different return types. For example, the `round()` function in Python2 returns a floating-point number, while `round` in Python3 returns an integer (unless specified).

Below are a list of commonly used built-in functions. 

### Built-in functions

* `abs`
* `all`
* `any`
* `bin`
* `bool`
* `chr`
* `dict`
* `dir`
* `divmod`
* `enumerate`
* `filter`
* `float`
* `hex`
* `int`
* `isinstance`
* `issubclass`
* `len`
* `list`
* `long`
* `map`
* `max`
* `min`
* `oct`
* `ord`
* `pow`
* `print`
* `range`
* `raw_input`
* `reduce`
* `repr`
* `reversed`
* `round`
* `set`
* `slice`
* `sorted`
* `str`
* `sum`
* `tuple`
* `xrange`
* `zip`

For information about how to use the above functions, check out [built-in functions](https://docs.python.org/3/library/functions.html) on Python's official documentation.

#### Example

```python
print(bin(3))        # 0b11
print(hex(255))      # 0xff
print(abs(-5))       # 5
print(pow(3, 2))     # 9
print(round(3.5))    # 4
print(round(3.2))    # 3
print(oct(8))        # 0o10
print(ord('A'))      # 65
print(chr(97))       # a

a = [1,4,5,2,3]
print(sorted(a))     # [1, 2, 3, 4, 5]
```

### User-defined functions

You can define your own function by using the `def` keyword.

Example:

```python
def my_add(a, b):
    c = a + b
    return c

print(my_add(1, 2))  # 3
```


### Reference

* [Built-in Functions](https://docs.python.org/3/library/functions.html) at *docs.python.org*