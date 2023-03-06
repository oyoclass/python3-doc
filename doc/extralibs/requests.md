## Requests

Requests is a Python library that simplifies the syntax for making HTTP requests. You can easily GET the content of webpages as well as POST data to them without needing to manually build query strings.

### Examples

#### GET Content from a Webpage

The basic way to load a webpage is with a GET request. The following code will send a GET request to a webpage, and load the result into a response object:

```python
import requests

query = {'exampleKey': 'exampleValue'}
resp = requests.get('https://httpbin.service.oyoclass.com/get', params=query)

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
    "Cf-Ray": "7a3b936cd84978d0-EWR",
    "Cf-Visitor": "{\"scheme\":\"https\"}",
    "Host": "httpbin.service.oyoclass.com",
    "User-Agent": "python-requests/2.28.2"
  },
  "origin": "23.92.19.165, 23.92.19.165",
  "url": "https://httpbin.service.oyoclass.com/get?exampleKey=exampleValue"
}
```

#### POST Data to a Webpage

We can also POST data to webpages with Requests. This action is like submitting form data or logging into a webpage, not trying to load a page:

```python
import requests

post_data = {'exampleKey': 'exampleValue'}
resp = requests.post('https://httpbin.service.oyoclass.com/post', data=post_data)

print(resp.text)
```

The target URL in the example is also a special echo endpoint:

```text
{
  "args": {},
  "data": "",
  "files": {},
  "form": {
    "exampleKey": "exampleValue"
  },
  "headers": {
    "Accept": "*/*",
    "Accept-Encoding": "gzip",
    "Cdn-Loop": "cloudflare",
    "Cf-Connecting-Ip": "23.92.19.165",
    "Cf-Ipcountry": "US",
    "Cf-Ray": "7a3b94b99a97c468-EWR",
    "Cf-Visitor": "{\"scheme\":\"https\"}",
    "Content-Length": "23",
    "Content-Type": "application/x-www-form-urlencoded",
    "Host": "httpbin.service.oyoclass.com",
    "User-Agent": "python-requests/2.28.2"
  },
  "json": null,
  "origin": "23.92.19.165, 23.92.19.165",
  "url": "https://httpbin.service.oyoclass.com/post"
}
```

### Requests

-   [Requests](https://requests.readthedocs.io/en/latest/) at _requests.readthedocs.io_
