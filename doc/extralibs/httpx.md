## HTTPX

HTTPX is an HTTP client for Python, similar to [Requests](/extralibs/requests) which can be used synchronously and asynchronously.

### Examples

#### Basic Web Requests

<div class="notebox notebox-info">
    <p class="notebox-title">
        Note
    </p>
    <p>
        Typical web requests can be performed exactly the same way as they can with the 
        <a href="/extralibs/requests">
            <b>Requests</b>
        </a>
        package. The examples on that page can work exactly the same with <b>HTTPX</b>, just replace the package name.
    </p>
</div>

The basic way to load a webpage is with a GET request. The following code will send a GET request to a webpage, and load the result into a response object:

```python
import httpx

query = {'exampleKey': 'exampleValue'}
resp = httpx.get('https://httpbin.service.oyoclass.com/get', params=query)

print(resp.text)
```

Most webpages will give their raw HTML, however this site acts like an echo for testing:

```text
{
  "args": {
    "exampleKey": "exampleValue"
  },
  "headers": {
    "Accept": "*/*",
    "Accept-Encoding": "gzip",
    "Cdn-Loop": "cloudflare",
    "Cf-Connecting-Ip": "23.92.19.165",
    "Cf-Ipcountry": "US",
    "Cf-Ray": "7a45cdbb68178c3b-EWR",
    "Cf-Visitor": "{\"scheme\":\"https\"}",
    "Host": "httpbin.service.oyoclass.com",
    "User-Agent": "python-httpx/0.23.3"
  },
  "origin": "23.92.19.165, 23.92.19.165",
  "url": "https://httpbin.service.oyoclass.com/get?exampleKey=exampleValue"
}
```

#### Using a Client to Share Request Parameters

If you want a set of parameteres to be shared across a range of requests, you should use a request client:

```python
import pprint
import httpx

headers = {'user-agent': 'example-app/1.0'}
with httpx.Client(headers=headers) as client:
    resp1 = client.get('https://httpbin.service.oyoclass.com/get', params={"num": 1})
    resp2 = client.get('https://httpbin.service.oyoclass.com/get', params={"num": 2})

print('Request 1:')
pprint.pprint(resp1.json())
print('\nRequest2:')
pprint.pprint(resp2.json())
```

Output (extra headers have been removed to make output more clear):

```text
Request 1:
{'args': {'num': '1'},
 'headers': {'User-Agent': 'example-app/1.0'},
 'url': 'https://httpbin.service.oyoclass.com/get?num=1'}

Request2:
{'args': {'num': '2'},
 'headers': {'User-Agent': 'example-app/1.0'},
 'url': 'https://httpbin.service.oyoclass.com/get?num=2'}
```

#### asyncio Support

**HTTPX** offers an async client which works with Python's builtin **asyncio**:

```python
import asyncio
import httpx

async def main():
    async with httpx.AsyncClient() as client:
        resp = await client.get('https://httpbin.service.oyoclass.com/get')
        print(resp.text)

asyncio.run(main())
```

Output for this example is the same for the first example:

```text
{
  "args": {
    "exampleKey": "exampleValue"
  },
  "headers": {
    "Accept": "*/*",
    "Accept-Encoding": "gzip",
    "Cdn-Loop": "cloudflare",
    "Cf-Connecting-Ip": "23.92.19.165",
    "Cf-Ipcountry": "US",
    "Cf-Ray": "7a45cdbb68178c3b-EWR",
    "Cf-Visitor": "{\"scheme\":\"https\"}",
    "Host": "httpbin.service.oyoclass.com",
    "User-Agent": "python-httpx/0.23.3"
  },
  "origin": "23.92.19.165, 23.92.19.165",
  "url": "https://httpbin.service.oyoclass.com/get?exampleKey=exampleValue"
}
```

### Reference

-   [HTTPX](https://www.python-httpx.org/) at _python-httpx.org_
