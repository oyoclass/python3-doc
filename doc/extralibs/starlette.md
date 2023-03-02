## Starlette

Starlette is an ASGI framework that allows for ease of building async web services in Python. To work properly, it must be used together with an ASGI server to run the service such as [Uvicorn](/extralibs/uvicorn/).

### Examples

#### Basic ASGI Server

First install the uvicorn library, then paste the following into `main.py`:

```python
from starlette.applications import Starlette
from starlette.responses import PlainTextResponse
from starlette.routing import Route
import uvicorn


async def homepage(request):
    return PlainTextResponse('Hello, World!')


async def greeting(request):
    username = request.path_params['username']
    return PlainTextResponse(f'Greetings, {username}!')


app = Starlette(debug=True, routes=[
    Route('/', homepage),
    Route('/greetings/{username}', greeting)
])

if __name__ == '__main__':
    # host must be 0.0.0.0 to work in the Python3 Editor
    uvicorn.run(app, host='0.0.0.0', port=8000)
```

When you visit "/", you will see a page like this:
<img src="../../assets/img/starlette-greetings-index.png" width="400px">

And when you visit "/greetings/jordan", you will see a page like this:
<img src="../../assets/img/starlette-greetings-jordan.png" width="400px"/>

### Reference

-   [Starlette](https://www.starlette.io/) at _starlette.io_
