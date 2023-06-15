## Standard Output and Input

### Standard Output

The most common way to output something is using `print` function:

```python
print(2 * 3)
print("hello")
arr = [1, 2, 3, 4]
print(arr)
```

Output:

```
6
hello
[1, 2, 3, 4]
```

---

Or you can use `sys.stdout.write`:

```python
from sys import stdout
arr = [1, 2, 3, 4]
stdout.write("hello ")
stdout.write(str(arr))
```

<div class="notebox notebox-info">
    <p class="notebox-title">
        Note
    </p>
    <p>
        The parameter of <code>write</code> must be a String.
    </p>
</div>

Output:

```
hello [1, 2, 3, 4]
```

### Standard Input

To get user input, you can use the `input` function:

```python
name = input("What's your name?")
print "hello", name
```

#### Change from Python2

The `raw_input` function from Python2 is no longer supported in Python3. The `input()` function in Python3 works the same way as the `raw_input()` function in Python2.

The `input()` function in Python3 _always_ returns a String. You must cast the variable to use the variable as a different type.

```python
num = input("Give me a number")
print(num)               # 12
print(num * 2)           # 1212

# now convert it to number
num = int(num)
print(num * 2)           # 24
```

---

You can also read user's input by using `sys.stdin.read` or `sys.stdin.readline`:

```python
from sys import stdin

name = stdin.readline()
print(name)

# Only reads 3 characters
name = stdin.readline(3)
print(name)
```
