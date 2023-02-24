## bottle

bottle is an ultra-lightweight web framework that works with just the Python
Standard Library. bottle also supports html template frameworks like 
<a href="/extralibs/jinja2/">Jinja2</a> for building more robust websites.

### Quick Examples

#### Say hello

```python
from bottle import route, run, template

@route('/')
def index():
    return "index page"


@route('/hello/<name>')
def hello(name):
    return template('<b>Hello {{name}}</b>!', name=name)


run(host='0.0.0.0', port=8080)
```

Copy and paste the above code to the Python3 Editor and click run, you will see the website running on the right.

When you visit "/", you will see the page like this:
<img src="../../assets/img/bottle-hello-index.png" width="400px">

When you visit "/hello/john", you will see the page like this:
<img src="../../assets/img/bottle-hello-john.png" width="400px">

Read more at <a href="https://bottlepy.org/docs/dev/">bottlepy.org</a>