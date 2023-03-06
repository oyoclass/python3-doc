## urllib — URL handling

This module has several sub-modules that works with URLs, and you can check out the sub-modules in [Python's standard documentation](https://docs.python.org/3.6/library/urllib.html).

We will show some examples for the most commonly used submodules `urllib.request` and `urllib.parse`.

### urllib.request

A common usage of this module is fetching data from the internet.

#### Example 1) Get a webpage's source code

```python
from urllib.request import urlopen

source_code = urlopen("http://sabrinaw.oyosite.com").read().decode("utf-8")
print(source_code)
```

This will print the source code as a string from the website "sabrinaw.oyosite.com".

<div class="notebox notebox-info">
    <p class="notebox-title">
        Note
    </p>
    <p>
        If you are using the code above to get the source code from a website, it is not uncommon that the function will return a "forbidden" error instead of the actual source code. The reason is that many websites have restrictions on who can fetch their code.
    </p>
    <p>
        For example, the website may check if you are an actual browser or a spider robot, and it will return an empty string or a "forbidden" error if they think you are a robot.
    </p>
</div>

#### Example 2) Get CSV data and parse it with the CSV lib

A comma-separated values (CSV) file is a delimited text file that uses a comma to separate values. Each line of the file is a data record. Each record consists of one or more fields, separated by commas. [Read more on Wikipedia >>](https://en.wikipedia.org/wiki/Comma-separated_values).

Suppose we have a CSV file for a Code Conquest Hackathon:

```csv
Name, Nickname, Age, Kingdom, Soldier Type, Rank
Reuben,The Hammer,59,Prubadour,Lancer,Sergeant
Everitt,The Whisper,27,Prubadour,Pikeman,Major
Reinhardt,The Mammoth,56,Prubadour,Healer,Private
Mel,The Hawk,53,Truisian,Pikeman,Sergeant
```

We can upload this file to our OYO website, and then read from the url. For example:

```python
import urllib.request, csv

page = urllib.request.urlopen("http://sabrinaw.oyosite.com/testing/data3.html")
reader = csv.reader(
    page.read().decode('utf-8').splitlines(),
    skipinitialspace=True
)

for row in reader:
    # row now is a python list
    print(row)
```

#### Example 3) Calling API

Most APIs provide [JSON](https://en.wikipedia.org/wiki/JSON) format data. Here we will use an IP-to-Location API to get the location information from an IP address.

```python
from urllib.request import urlopen
import json

ip = input("Input the IP you want to query: ")
url = f"http://ip-api.com/json/{ip}"
location = json.loads(urlopen(url).read())
print("Approx. Location:", location["city"], location["region"])
```

Run it (suppose we want to query the IP 67.84.146.84):

```markdown
Input the IP you want to query: 67.84.146.84
Approx. Location: Ronkonkoma NY
```

#### Use OYOclass Proxy

Some schools may have firewalls that block domains. For example, if your school blocks access to the "ip-api.com" domain, you won't get data returned like the above. In these cases, you can use our proxy by simply prepending `https://proxy.oyoclass.com/` to any URL that you want to fetch data from.

```python
from urllib.request import urlopen
import json

ip = input("Input the IP you want to query: ")
url = f"https://proxy.oyoclass.com/http://ip-api.com/json/{ip}"
location = json.loads(urlopen(url).read())
print("Approx. Location:", location["city"], location["region"])
```

Here is another example. This is an API you can use to get the bitcoin price in USD: `https://api.coingecko.com/api/v3/simple/price?ids=bitcoin&vs_currencies=usd`.

Suppose your school blocks the "coingecho.com" domain, you can just prepend `https://proxy.oyoclass.com/` to it:

```python
from urllib.request import urlopen
import json
url = "https://proxy.oyoclass.com/https://api.coingecko.com/api/v3/simple/price?ids=bitcoin&vs_currencies=usd"
data = json.loads(urlopen(url).read())
print(data)
```

Run it:

```
{'bitcoin': {'usd': 65274}}
```

### urllib.parse

This submodule can help parse a URL string and split it into different components. [Read more >>](https://docs.python.org/3.6/library/urllib.parse.html#module-urllib.parse).

#### Example

```python
from urllib.parse import urlparse

url = "https://oyoclass.com/settings/account?name=python#anchor"
parsed = urlparse(url)
print(parsed)
print(parsed.scheme)
print(parsed.netloc)
print(parsed.path)
print(parsed.query)
print(parsed.fragment)
```

Run it:

```
ParseResult(scheme='https', netloc='oyoclass.com', path='/settings/account', params='', query='name=python', fragment='anchor')
https
oyoclass.com
/settings/account
name=python
anchor
```
