## String

You can define a string using two single-quotes, two double-quotes, or two triple-quotes. For example, you can declare a string using `s = "hello"`. Once you have a string, you can apply any of the methods listed in the **functions** portion.

### Formatting Strings in Python

In Python2:
```python
i = 1
s = "abc"
mystr1 = "{} {}".format(i, s)
mystr2 = "%d %s" % (i, s)
print(mystr1)				#1 abc
print(mystr2)				#1 abc
```

In Python3:
```python
i = 1
s = "abc"
mystr1 = "{} {}".format(i, s)
mystr2 = f"{i} {s}"
print(mystr1)				#1 abc
print(mystr2)				#1 abc
```

There are multiple ways to format strings in Python2 and Python3. If you look at the above examples, you can see that `"{} {}".format(i, s)` works in both Python2 and Python3. 

In Python2, you can use the `%` operator with strings to format strings through _string interpolation_. You should not use this function in Python3 because it is **deprecated**. The new way to do _string interpolation_ in Python3 is through the use of the `f` operator.


### Functions

* `str.capitalize()`
* `str.center(width[, fillchar])`
* `str.count(sub[, start[, end]])`
* `str.endswith(suffix)`
* `str.expandtabs([tabsize])`
* `str.find(sub[, start[, end]])`
* `str.format(*args, **kwargs)`
* `str.index(sub[, start[, end]])`
* `str.isalnum()`
* `str.isalpha()`
* `str.isdigit()`
* `str.islower()`
* `str.isnumeric()`
* `str.isspace()`
* `str.istitle()`
* `str.isupper()`
* `str.join(iterable)`
* `str.ljust(width[, fillchar])`
* `str.lower()`
* `str.lstrip([chars])`
* `str.partition(sep)`
* `str.replace(old, new[, count])`
* `str.rfind(sub[, start[, end]])`
* `str.rindex(sub[, start[, end]])`
* `str.rjust(width[, fillchar])`
* `str.rpartition(sep)`
* `str.rstrip([chars])`
* `str.split(`_`sep=None, maxsplit=-1`_`)`
* `str.splitlines([keepends])`
* `str.startswith(prefix[, start[, end]])`
* `str.strip([chars])`
* `str.swapcase()`
* `str.title()`
* `str.upper()`
* `str.zfill(width)`

For information about how to use above functions, check out [String Methods](https://docs.python.org/3/library/stdtypes.html#string-methods) in Python's official documentation.

### Example

```python
a = "hello world"
print(a.capitalize())        # Hello world
print(a.upper())             # HELLO WORLD
print(a.find("world"))       # 6
print(a.split())             # ['hello', 'world']
print(a.isalnum())           # False

b = "hello {0} {1}"
print(b.format("Albert", "Einstein"))    # hello Albert Einstein
```

### Reference

* [String Methods](https://docs.python.org/3/library/stdtypes.html#string-methods) at *docs.python.org*