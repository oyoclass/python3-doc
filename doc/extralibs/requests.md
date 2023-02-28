## Requests

Requests is a Python library that simplifies the syntax for making HTTP 
requests. You can easily GET the content of webpages as well as POST data to
them without needing to manually build query strings.

### Examples

#### GET Content from a Webpage

```python
import requests

query = {'exampleKey': 'exampleValue'}
resp = requests.get('https://httpbin.service.oyoclass.com/get', params=query)

print(resp.text)
```

#### POST Data to a Webpage
```python
import requests

post_data = {'exampleKey': 'exampleValue'}
resp = requests.post('https://httpbin.service.oyoclass.com/post', data=post_data)

print(resp.text)
```

Read more at <a href="https://requests.readthedocs.io/en/latest/">requests.readthedocs.io</a>