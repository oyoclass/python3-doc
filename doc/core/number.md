
## Number

You can use integer and floating-point numbers in Python3. For example,

```python
a = 1
b = 2
print(a + b)        # 3
print(b * 3)        # 6
print(1 + 2 * 3)    # 7
print((1 + 2) * 3)  # 9

c = 1.5
print(c * 2)        # 3.0

print(1 / 3)        # 0.3333333333333333
print(1.0 / 3)      # 0.3333333333333333
```

####Converting Numbers to Integer and Floating-Point Numbers:

* `int(x)`: Converts `x` to integer
* `float(x)`: Converts `x` to floating-point number


Example:
```python
print(int(12.3))   	# 12
print(int("234"))   # 234
print(float(12))    # 12.0
```	

### Differences Between Python2 and Python3
In Python2:
```python
x = 5 / 2.0 		# x = 2.5
x = 5 / 2			# x = 2
x = 5 // 2			# x = 2
```

In Python3: 
```python
x = 5 / 2.0			# x = 2.5
x = 5 / 2			# x = 2.5
x = 5 // 2			# x = 2
```
The main difference for the mathematical operations between Python2 and Python3 is `5 / 2`. 
In Python2, single-slash division returns *integer divison*. This means that the remainder part of the result is discarded. In Python3, single-slash division returns *regular division*, where the remainder remains a part of the answer. 

When you do floor division (`5 // 2`) or an integer divided by a float (`5 / 2.0`), the result is the same in both Python 2 and Python3.  


### Major Change from Python2

The **long** type in Python has been removed. There are no long-type integers in Python3. 


### Reference
* [Numeric Types](https://docs.python.org/3/library/stdtypes.html#numeric-types-int-float-complex) at *docs.python.org*