## SQLAlchemy

SQLAlchemy is an SQL database engine library for Python. It uses its own syntax for handling database operations with Python objects and writes the SQL queries for you. SQLAlchemy can be useful if you're uncomfortable writing your own SQL queries directly with [SQLite](/modules/sqlite/).

### Examples

#### Create a Table

First thing we need to do is create a table in our database:

```python
from sqlalchemy import create_engine, MetaData, Table, Column, Integer, String
engine = create_engine('sqlite:///college.db', echo = True)
meta = MetaData()

students = Table(
   'students', meta,
   Column('id', Integer, primary_key = True),
   Column('firstname', String),
   Column('lastname', String),
)
meta.create_all(engine)
```

In our console, we can see that SQLAlchemy will print the raw SQL query:

```sql
CREATE TABLE students (
    id INTEGER NOT NULL,
    firstname VARCHAR,
    lastname VARCHAR,
    PRIMARY KEY (id)
)
```

#### Insert a Row

In the following snippet, we will insert a student with the `firstname` field set to `'Karen'`:

```python
import sqlalchemy as db
engine = db.create_engine('sqlite:///college.db', echo = True)
conn = engine.connect()
meta = db.MetaData()

# Get access to the students table
students = db.Table('students', meta, autoload_with=engine)
# Create the insert SQL statement
ins = students.insert().values(firstname='Karen')

# Begin a transaction
trans = conn.begin()
# Execute insert in transaction
conn.execute(ins)
# Commit the transaction
trans.commit()
```

We can't see our result immedaitely, but we will read from this table in the next example to see the student we inserted:

#### Read a Row

We can read an entire table with a `select()` call:

```python
import sqlalchemy as db
engine = db.create_engine('sqlite:///college.db', echo = True)
conn = engine.connect()
meta = db.MetaData()

# Get access to the students table
students = db.Table('students', meta, autoload_with=engine)
s = students.select()
res = conn.execute(s)

for row in res.fetchall():
    print(row)
```

This will print out the data:

```text
(1, 'Karen', None)
```

It's our student that we inserted before! They were given an `id` of **1** and since we did not specify a `lastname` for our student, it has been left null (**None** in Python)

#### Update a Row

Let's write a program to update a student with `id==1` to have the `lastname` **Karenston**:

```python
import sqlalchemy as db
engine = db.create_engine('sqlite:///college.db', echo = True)
conn = engine.connect()
meta = db.MetaData()

# Get access to the students table
students = db.Table('students', meta, autoload_with=engine)
s = students.update().where(students.c.id==1).values(lastname='Karenston')
trans = conn.begin()
res = conn.execute(s)
trans.commit()
```

Now, if we run the `fetchall()` example from before, our program will now output:

```text
(1, 'Karen', 'Karenston')
```

#### Delete a Row

Finally, let's delete the row we've been working with. The process is almost identical to the `update()` example:

```python
import sqlalchemy as db
engine = db.create_engine('sqlite:///college.db', echo = True)
conn = engine.connect()
meta = db.MetaData()

# Get access to the students table
students = db.Table('students', meta, autoload_with=engine)
s = students.delete().where(students.c.id==1)
trans = conn.begin()
res = conn.execute(s)
trans.commit()
```

Now our database table is empty once again.

### Reference

-   [SQLAlchemy](https://www.sqlalchemy.org/) at _sqlalchemy.org_
