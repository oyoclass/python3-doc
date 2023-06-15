## Set

A set is an unordered collection with no duplicate elements. Basic uses of sets include membership testing and eliminating duplicate entries. Set objects also support mathematical operations like union, intersection, difference, and symmetric difference.

You can use the `set()` function to make a set. Here is a quick example:

```python
basket = ['apple', 'orange', 'apple', 'pear', 'orange', 'banana']
fruit = set(basket)
print(fruit)     # {'apple', 'orange', 'pear', 'banana'}
```

### Empty Sets
Sets in Python3 are enclosed in curly braces (`{}`). However, in order to create an empty set, you would not use a set of empty curly braces (`{}`). To create an empty set, you would use the `set()` function with no parameters.

```python
var1 = set()
var2 = {}
print(type(var1))	#<class 'set'>
print(type(var2))	#<class 'dict'>
```

### Functions

* `set.add(elem)` : Adds element *elem* to the set.
* `set.copy()` : Returns a new set that is shallow copy of *set*.
* `set.difference(*others)` : Returns a new set with elements that are in the set that are not in the *others*.
	* `set - other`: Functions the same as `set.difference(other)` .
* `set.difference_update(*others)` : Updates the set, removing elements found in others.
* `set.discard(elem)` : Removes element *elem* from the set if it is present.
* `set.intersection(others)` : Returns a new set with elements common to the set and all *others*.
* `set.intersection_update(others)`: Updates the set, keeping only elements found in it and all *others*.
* `set.isdisjoint(other)` : Returns True if the set has no elements in common with other. Sets are disjoint if and only if their intersection is the empty set.
* `set.issubset(other)` : Test whether every element in the set is in *other*.
	* `set <= other`: Test whether every element is in *other*.
	* `set < other`: Test whether the set is a proper subset of *other*(`set <= other` and `set != other`).
* `set.issuperset(other)` : Test whether every element in *other* is in the set.
	* `set >= other`: Test whether every element in *other* is in the set.
	* `set > other`: Test whether the set is a proper superset of *other*(`set >= other` and `set != other`).
* `set.pop()` : Removes and returns an arbitrary element from the set.
* `set.remove(elem)` : Remove element *elem* from the set.  
* `set.symmetric_difference(other)` : Returns a new set with elements in either the set or *other* but **not both**.
	* `set ^ other`: Returns a set with elements in either the set or other but **not both**.
* `set.symmetric_difference_update(other)` : Updates the set, keeping only elements found in either set, but **not in both**.
* `set.union(others)` : Returns a new set with elements from the set and all *others*.
	* `set | other`: Returns a new set with elements from the set and *other*.
* `set.update(*others)` : Updates the set, adding elements from all *others*.


### Example

```python
a = set()
a.add(1)
a.add(2)
a.add(1)

print(a)                 # {1, 2}
print(len(a))            # 2

b = set([2,2,3])
print(b)                 # {2, 3}

print(a.intersection(b)) # {2}

c = set([3])
print(b.issuperset(c))   # True

print(a ^ b)             # {1, 3}
print(a >= b)            # False
print(c <= c)            # True
print(c < c)             # False
print(a.union(b))        # {1, 2, 3}
```

### Reference

* [Sets as a Data Structure](https://docs.python.org/3/tutorial/datastructures.html#sets) on *docs.python.org*.
* [Set as a Built-in Type](https://docs.python.org/3/library/stdtypes.html#set-types-set-frozenset) on *docs.python.org*. 