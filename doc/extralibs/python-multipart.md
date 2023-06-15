## Python-Multipart

Python-Multipart is a library for handling `multipart/form-data` POST requests. This is usually only needed or used when running a web server and you have a place where users can upload files.

<div class="notebox notebox-info">
    <p class="notebox-title">
        Note
    </p>
    <p>
        This library is needed for handling POST requests with 
        <a href="../starlette"><b>Starlette</b></a>.
    </p>
</div>

### Example

#### Handling a Multipart Request

Below is an example of how to handle a basic multipart request using the [Bottle](../bottle) library for our server:

```python
from bottle import request, get, post, run
import multipart

@get('/')
def index_get():
    return 'hi'

@post('/')
def index_post():
    field_to_values = {}
    filenames = []
    ret = {
        'field_to_values': field_to_values,
        'filenames': filenames
    }
    def on_field(field):
        field_to_values[field.field_name.decode()] = field.value.decode()

    def on_file(file):
        filenames.append(file.field_name.decode())

    # Python-Multipart doesn't assume we are using WSGI, so we need to
    # manually create a header dictionary to pass to it.
    environ = request.environ
    headers = {'Content-Type': environ['CONTENT_TYPE']}
    if 'HTTP_X_FILE_NAME' in environ:
        headers['X-File-Name'] = environ['HTTP_X_FILE_NAME']
    if 'CONTENT_LENGTH' in environ:
        headers['Content-Length'] = environ['CONTENT_LENGTH']

    # Parse the form
    multipart.parse_form(headers, environ['wsgi.input'], on_field, on_file)

    return ret

# host must be 0.0.0.0 to work in the Python3 IDE
run(host='0.0.0.0', port=8000)
```

Then we need to take the URL generated in our running app to the right of our code and use it to make a POST request to our server.

<div class="notebox notebox-info">
    <p class="notebox-title">
        Note
    </p>
    <p>
        When you run your program, you will get a random URL in the form of:
    </p>
    <p>
        <b>https://(random).app.oyoprofile.com</b>
    </p>
    <p>
        Make sure you copy the whole URL for the next part of this example.
    </p>
</div>

Then we can open a command line tool (`cmd` in Windows or `Terminal` in macOS) and write the following:

```text
curl -X POST -d "key1=val1&key2=val2" https://(YOUR URL HERE)/
```

Our server will return the following and it will be printed in your terminal:

```text
{"field_to_values": {"key1": "val1", "key2": "val2"}, "filenames": []}
```

### Reference

-   [Python Multipart](https://andrew-d.github.io/python-multipart/index.html) at _github.io_
