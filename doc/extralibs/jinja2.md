## Jinja2

Jinja2 is a templating engine. It allows you to inject variables and write code similar to Python directly into text files, which can be very useful for building webpages.

### Examples

#### Render a Template from File

First, create a template named `template.html` in your project's directory:
```html
<!DOCTYPE html>
<html>
    <head>
        <title>My Template</title>
    </head>
    <body>
        {% for i in range(count_to) %}{{i}} {% endfor %}

        {% if say_hi %}
            Hi!
        {% else %}
            Goodbye!
        {% endif %}
    </body>
</html>
```

Then, in `main.py`:

```python
from jinja2 import Environment, FileSystemLoader

environment = Environment(loader=FileSystemLoader('./'))
template = environment.get_template('template.html')

print(template.render(count_to=10, say_hi=False))
```

Results:

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My Template</title>
    </head>
    <body>
        0 1 2 3 4 5 6 7 8 9 

        
            Goodbye!
        
    </body>
</html>
```


### Reference

-   [Jinja2](https://jinja.palletsprojects.com/en/3.1.x/) at _jinja.palletsprojects.com_
