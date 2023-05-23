## What is Python3?

Quote from Python's official website:

> Python is an easy to learn, powerful programming language. It has efficient high-level data structures and a simple but effective approach to object-oriented programming. Python’s elegant syntax and dynamic typing, together with its interpreted nature, make it an ideal language for scripting and rapid application development in many areas on most platforms.

Currently Python has two versions: Python2 and Python3. Python3 is the new version of Python. Quote from wikipedia:

> Python 3.0 (also called "Python 3000" or "Py3K") was released on December 3, 2008. It was designed to rectify fundamental design flaws in the language—the changes required could not be implemented while retaining full backwards compatibility with the 2.x series, which necessitated a new major version number. The guiding principle of Python 3 was: "reduce feature duplication by removing old ways of doing things".

Python2 won't be maintained after January 1, 2020. If you are new to programming, you should learn Python3 instead of Python2. However, if you are already familiar with Python2, learning Python3 will be very easy for you.


## About OYOclass' Python3 IDE (Beta)

The Python3 IDE (Beta) is an application built into the OYOclass platform, which can be used to write Python3 code. OYOclass' Python3 IDE uses Python version 3.11 behind the scenes. The term "IDE" stands for "Integrated Development Environment", it provides a set of tools for programmers to write, edit and compile code efficiently. 

The following links from Python's official website can help you get started.

* [The Python Tutorial](https://docs.python.org/3.6/tutorial/index.html)
* [The Python Language Reference](https://docs.python.org/3.6/reference/index.html)
* [The Python Standard Library](https://docs.python.org/3.6/library/index.html)


## Quick Start

Copy the following code samples to OYOclass' Python3 Editor. Then, click the "Run" button.

**Print**

```python
print("Hello World")
print(123)
print(1 + 2)
print(1 + 2 * 3)
```

**User Input**

```python
name = input("What's your name?\n")
age = input("How old are you?\n")
print(f"Hello {name}, you are {age} years old")
```

**Loop**

```python
for i in range(1, 6):
    print("* " * i)
```

**Call Web API**

```python
from urllib.request import urlopen
import json

req = urlopen("https://cataas.com/cat?json=true")
data = json.loads(req.read())
print(f"Open the URL to see a cat: \n https://cataas.com{data['url']}")
```

## Beyond OYOclass' Python3 Editor (Beta)
  
If you would like to do more with Python and go beyond the capabilities of OYOclass' Python3 Editor, please download and install the Python:

* [Download Python](https://www.python.org/downloads/): The version you download from Python's website is most likely greater than or equal to version 3.11. 
* [Python3's Official Documentation](https://docs.python.org/3/)
* [Resources in Awesome Python's Repository](https://github.com/vinta/awesome-python)