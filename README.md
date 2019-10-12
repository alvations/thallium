# thallium
Cos I can't get selenium to work...

## With chromedriver_binary

For some people [`chromedriver_binary`](https://github.com/danielkaiser/python-chromedriver-binary/) works:

```python
from selenium import webdriver
import chromedriver_binary

driver = webdriver.Chrome()
driver.get("http://www.python.org")
assert "Python" in driver.title
```

But not for me =(

[out]:

```
---------------------------------------------------------------------------
SessionNotCreatedException                Traceback (most recent call last)
<ipython-input-1-329381aca80b> in <module>
      2 import chromedriver_binary
      3
----> 4 driver = webdriver.Chrome()
      5 driver.get("http://www.python.org")
      6 assert "Python" in driver.title

SessionNotCreatedException: Message: session not created: This version of ChromeDriver only supports Chrome version 78
```

# With pyderman

For some other people [`pyderman`](https://github.com/shadowmoose/pyderman) works:

```python
from selenium import webdriver
import pyderman as driver
path = driver.install(browser=driver.chrome)

driver = webdriver.Chrome(path)
driver.get("http://www.python.org")
assert "Python" in driver.title
```

Yes, this worked for me... But I think we can do better.


<! --
# With thallium

```python
from thallium import WebDriver

class WebDriver:
    def __init__(self):

driver.get("http://www.python.org")
assert "Python" in driver.title


driver = WebDriver('chrome')
driver.get("http://www.python.org")
assert "Python" in driver.title
```


https://github.com/SeleniumHQ/selenium/blob/master/py/selenium/webdriver/__init__.py

-->
