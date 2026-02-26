## Flask-Session

Flask-Session is an extension for Flask that adds support for server-side sessions to your application.

<div class="notebox notebox-info">
    <p class="notebox-title">
        Info
    </p>
    <p>
    When saving session to the local file system, you will also need to install the <b>cachelib</b> package.
    </p>
</div>

### Example

To run this example code, you need to install `Flask`, `Flask-Session` and `cachelib` libraries.

```python
import os
import time

from flask import Flask, session
from flask_session import Session
from cachelib.file import FileSystemCache

app = Flask(__name__)

# Use local file system to store session data
app.config["SESSION_TYPE"] = "cachelib"
app.config['SESSION_CACHELIB'] = FileSystemCache(cache_dir='flask_session', threshold=5)

Session(app)

@app.route("/")
def index():
    return "For testing, please visit <a href='/set/'>/set/</a> and <a href='/get/'>/get/</a>."


@app.route('/set/')
def set():
    name = "John Doe " + str(time.time())
    session["name"] = name
    return f"Session 'name' has been set to [{name}]. Visit <a href='/get/'>/get/</a> to test."


@app.route("/get/")
def get():
    return "Hello, " + session.get("name", "[Unknown]")


if __name__ == '__main__':
    # host must be 0.0.0.0 to work in the Python3 IDE
    app.run(host='0.0.0.0', port=8080)
```
