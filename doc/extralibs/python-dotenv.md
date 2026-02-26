## python-dotenv

python-dotenv reads key-value pairs from a .env file and can set them as environment variables.

<div class="notebox notebox-danger">
    <p class="notebox-title">
        Warning
    </p>
    <p>
        When including private API keys in your .env file, make sure you <b>DO NOT</b> make your project <b>"Open Source"</b> when you share it.
    </p>
</div>

### Examples

1, Create a `.env` file in your project.

2, Set some environment variables in the `key=value` format like this:
```
DOMAIN=example.org
ADMIN_EMAIL=admin@${DOMAIN}
ROOT_URL=${DOMAIN}/app
```

3, In your code, load variables via this library.
```python
import os
from dotenv import load_dotenv

# load all environment variables from .env file
load_dotenv()
# test, it should print "admin@example.org"
print(os.environ.get("ADMIN_EMAIL", "[not set]"))
```

### Reference
* [python-dotenv doc](https://github.com/theskumar/python-dotenv)