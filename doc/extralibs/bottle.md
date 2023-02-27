## bottle

bottle is an ultra-lightweight web framework that works with just the Python
Standard Library. bottle also supports html template frameworks like 
<a href="/extralibs/jinja2/">Jinja2</a> for building more robust websites.

### Examples

#### Say Hello

```python
from bottle import route, run, template

@route('/')
def index():
    return 'index page'


@route('/hello/<name>')
def hello(name):
    return template('<b>Hello {{name}}</b>!', name=name)

# host must be 0.0.0.0 to work in the Python3 Editor
run(host='0.0.0.0', port=8080)
```

Copy and paste the above code to the Python3 Editor and click run, you will see the website running on the right.

When you visit "/", you will see a page like this:
<img src="../../assets/img/bottle-hello-index.png" width="400px">

And when you visit "/hello/john", you will see a page like this:
<img src="../../assets/img/bottle-hello-john.png" width="400px">

Read more at <a href="https://bottlepy.org/docs/dev/">bottlepy.org</a>