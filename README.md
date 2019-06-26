# APITest

### Pre-requisites:

-Python 2.7

-tavern


Install tavern module via pip:

```shell
$ pip install tavern
```
### Running tests:

Using pytest:

Go to the base folder of this github repo and type:


```shell
$ py.test
============================= test session starts ==============================
platform linux2 -- Python 2.7.14, pytest-4.6.3, py-1.8.0, pluggy-0.12.0
rootdir: /home/chango/gitrepos/APITest
plugins: tavern-0.26.4
collected 1 item                                                               

test_minimal.tavern.yaml .                                               [100%]
===================== 1 passed, 2 warnings in 0.46 seconds =====================
```
All tests under this location will be found and run.

Using the command line:

```shell
$ tavern-ci test_minimal.tavern.yaml
```
Programmatically via python:

```python
from tavern.core import run

success = run("test_minimal.tavern.yaml", {})

if not success:
    print("Error running tests")
```
### Choice of tool:

Tavern is an open source framework, declarative and extensible.
So no need to write code from the start, just describe your test.
If later on there is some functionality need that is not covered by the framework, a python function can be written.

### Testing strategy

For each endpoint:

 Test all possible request methods (GET, POST, PUT, PATCH, DELETE and OPTIONS)

For each request method:

 Check request header and body,

 Check response header and body

 Check response codes

For headers, check required/optional/missing/not supported values

For body, check wrong data type, empty, null, invalid json


