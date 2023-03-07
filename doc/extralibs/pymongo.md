## PyMongo

PyMongo is a Python library that provides an interface for using MongoDB. MongoDB is a **NoSQL** database, which means **it does not use Structured Query Language** like [SQLite](/modules/sqlite/). MongoDB is useful for an easy to understand database interface without the rigidity a traditional relational SQL database may have.

<div class="notebox notebox-info">
    <p class="notebox-title">
        Note
    </p>
    <p>
        Python3 Editor does not provide access to a locally running Mongo database. You can, however, connect to a Mongo cloud database using the Python3 Editor. Mongo provides a free tier for their cloud database service and you can get one by making an account with them.
    </p>
    <p>
        We have written a short guide on how to properly set up a Mongo cloud instance to work with Python3 Editor. You can check it out here:
    </p>
    <p>
        <a href="https://docs.oyoclass.com/cloudservices/datastores/mongo">
            <b>
                MongoDB Free Cloud Database
            </b>
        </a>
    </p>
</div>

### Examples

#### Connect to Your Database

Before we can write or read anything to our new cloud database, we need to actually have our code connect to it. Mongo provides a pre-built connection URL that you can copy and paste into your code. To find this URL, do the following:

1\. Find your cloud cluster, and click the **Connect** button:

<img src="../../assets/img/mongo-connect1.png" width="400px">

2\. Click on **Connect your application** in the window that pops up:
<img src="../../assets/img/mongo-connect2.png" width="400px">

3\. Select **Python** and **3.11 or later** in the dropdowns, and follow the directions about replacing **<password\>** in the provided URL with the password you chose when setting up your cluster's user account:

<img src="../../assets/img/mongo-connect3.png" width="500px">

After you do all that, you can finally paste the code provided into Python3 Editor and test your connection with the database:

<div class="notebox notebox-info">
    <p class="notebox-title">
        Note
    </p>
    <p>
        For this example and all the following examples, they will provide dummy database URLs that you must replace with the one provided by your Mongo cloud instance.
    </p>
</div>

```python
import pymongo

client = pymongo.MongoClient("mongodb+srv://admin:<password>@<your cluster>.mongodb.net/?retryWrites=true&w=majority")

# this will fail if the provided URL or database has a problem
client.server_info()
print("Database connected successfully")
```

If you have done everything correctly, then congratulations! You have successfully created and connected to a MongoDB cloud instance properly configured to work with the Python3 Editor.

#### Creating a New Document
