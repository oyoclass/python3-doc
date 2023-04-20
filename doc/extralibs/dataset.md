## Dataset 

The "dataset" library makes reading and writing data in SQLite databases as simple as reading and writing JSON files.


### Example: Simple Student Roster

We can rewrite the example in the [SQLite documentation](../../modules/sqlite) with this `dataset` library.

```python
import dataset

db = dataset.connect('sqlite:///example.db')

table = db["students"]
table.insert({
    "last_name": "Doe",
    "first_name": "John",
    "age": 16,
    "gpa": 3.2
})
table.insert({
    "last_name": "Doe",
    "first_name": "Jane",
    "age": 13,
    "gpa": 3.8
})
table.insert({
    "last_name": "Smith",
    "first_name": "Ronald",
    "age": 14,
    "gpa": 2.7
})

# find all students that age > 15
students = table.find(age={">": 15})
for student in students:
    print(student)


# find one student whose first name is "Jane"
jane = table.find_one(first_name="Jane")
print(jane)
```

Run the code:
```
Students with age > 13:
OrderedDict([('id', 1), ('last_name', 'Doe'), ('first_name', 'John'), ('age', 16), ('gpa', 3.2)])
OrderedDict([('id', 3), ('last_name', 'Smith'), ('first_name', 'Ronald'), ('age', 14), ('gpa', 2.7)])

Student with name Jane:
OrderedDict([('id', 2), ('last_name', 'Doe'), ('first_name', 'Jane'), ('age', 13), ('gpa', 3.8)])
```

In the above example, we first connect to a database file named "example.db", if the file doesn't exist, `dataset` will automatically create this file, then we insert 3 students into the table, then we query all students whose age is greater than 13. We also made a query to find a student whose name is "Jane". You can see that with the `dataset` library, we don't need to write SQL statements like `SELECT`, `INSERT`, it makes the operation much easier.


### Reference

For more examples on query, insert, update and delete, please head to the `dataset` official documentation: [https://dataset.readthedocs.io/](https://dataset.readthedocs.io/)
