## BeautifulSoup4

BeautifulSoup4 is a library that parses HTML and XML files and provides an easy interface for extracting information out of them. Can be very useful when combined with the [Requests](/extralibs/requests/) library for scraping data off of webpages.

### Examples

#### Get Title of Webpage with requests

After installing the requests library, paste the following code into `main.py`:

```python
from bs4 import BeautifulSoup
import requests

url = "https://www.wikipedia.org/"
req = requests.get(url)
soup = BeautifulSoup(req.text, "html.parser")

print(soup.title)
```

Results:

```html
<title>Wikipedia</title>
```

### Reference

-   [BeautifulSoup4](https://www.crummy.com/software/BeautifulSoup/bs4/doc/) at _crummy.com_
