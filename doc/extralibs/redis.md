## Redis

Redis is an in-memory datastore which boasts high speed data storage and access. Redis is most often used for caching frequently used data that doesn't need to be stored forever, such as client sessions for a web service. redis-py is a Python library that allows interfacing with Redis.

<div class="notebox notebox-info">
    <p class="notebox-title">
        Note
    </p>
    <p>
        Python3 Editor does not provide access to a locally running Redis instance. You can, however, connect to a Redis cloud database using the Python3 Editor. Redis provides a free tier for their cloud database service and you can get one by making an account with them.
    </p>
    <p>
        We have written a short guide on how to properly set up a Redis cloud instance to work with Python3 Editor. You can check it out here:
    </p>
    <p>
        <a href="https://docs.oyoclass.com/cloudservices/datastores/redis">
            <b>
                Redis Free Cloud Database
            </b>
        </a>
    </p>
</div>

### Connecting to Your Database

First, open up your Redis account and go to your database list. Here, click on the **Connect** button:

<img src="../../assets/img/redis-connect1.png" width="700px">

In the following list, click on **Redis Client**:

<img src="../../assets/img/redis-connect2.png" width="400px">

In the menu that appears, select **Python** as your client, then copy the code into your Python3 Editor project:

<img src="../../assets/img/redis-connect3.png" width="400px">

<div class="notebox notebox-info">
    <p class="notebox-title">
        Note
    </p>
    <p>
        If you click the <b>Copy</b> button above, Redis will automatically insert your database's password into the code snippet. A password is added by default when you create your database.
    </p>
    <p>
        If you want to set your own password, you can click on your database, and scroll down you can find the <b>Security</b> section which includes the password Redis generated:
    </p>
    <p>
        <img src="../../assets/img/redis-database-password.png" width="400px">
    </p>
    <p>
        <b>Make sure you don't share this password with anyone.</b>
    </p>
</div>

Congratulations! You're now ready to use your Redis cloud with Python3 Editor.

### Examples

#### Create and Read Keys

Storing keys and values are simple with Redis. We can use the `set()` method to set a value in Redis:

```python
import redis

r = redis.Redis(
  host='<YOUR DATABASE>.cloud.redislabs.com',
  port=11588,
  password='<YOUR PASSWORD>'
)

r.set('example_key', 'example_val')
print(r.get('example_key'))
print(r.get('not_exist_key'))
```

Output:

```text
b'example_val'
None
```

Notice two things:

1. our **example_val** string got automatically converted to bytes
2. when we attempt to access a key that doesn't exist, we get `None`, not an error

#### Update Keys

If we want to update an existing key, we can just overwrite it:

```python
import redis

r = redis.Redis(
  host='<YOUR DATABASE>.cloud.redislabs.com',
  port=11588,
  password='<YOUR PASSWORD>'
)

r.set('example_key', 'val1')
print(r.get('example_key'))
r.set('example_key', 'val2')
print(r.get('example_key'))
```

Output:

```text
b'val1'
b'val2'
```

#### Delete Keys

We can also delete keys with the `delete()` method:

```python
import redis

r = redis.Redis(
  host='<YOUR DATABASE>.cloud.redislabs.com',
  port=11588,
  password='<YOUR PASSWORD>'
)

r.set('example_key', 'val1')
print(r.get('example_key'))
r.delete('example_key')
print(r.get('example_key'))
```

Output:

```text
b'val1'
None
```

### Reference

-   [redis-py](https://redis-py.readthedocs.io/en/stable/) at _readthedocs.io_
