## uvicorn

uvicorn is an ASGI web server implementation for Python. It allows for hosting
an ASGI server and serving requests. It is highly recommended that uvicorn be used
together with an ASGI framework library, like <a href="/extralibs/starlette/">starlette</a>.

### Example

#### Standalone uvicorn Hello World

```python
import uvicorn


async def app(scope, receive, send):
    assert scope['type'] == 'http'

    await send({
        'type': 'http.response.start',
        'status': 200,
        'headers': [
            [b'content-type', b'text/plain'],
        ],
    })
    await send({
        'type': 'http.response.body',
        'body': b'Hello, world!',
    })

if __name__ == "__main__":
    # host must be 0.0.0.0 to work in the Python3 Editor
    uvicorn.run('main:app', host='0.0.0.0', port=8080, log_level='info')
```

If you would like to have routing to different pages in your app, you should use an
ASGI framework like <a href="/extralibs/starlette/">starlette</a>, otherwise you will 
have to parse the `scope['path']` variable and handle the different request paths yourself.

Read more at <a href="https://www.uvicorn.org/">uvicorn.org</a>