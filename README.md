# python-flask

## Install Virtual Environment & Flask
1. Generate Virtual environment
```
python3 -m venv venv
```

2. Run virtualenv to create virtual environment
```
virtualenv venv
```

output:
```
created virtual environment CPython3.9.1.final.0-64 in 702ms
  creator CPython3Posix(dest=/Users/kecci/python/python-flask/venv, clear=False, no_vcs_ignore=False, global=False)
  seeder FromAppData(download=False, pip=bundle, setuptools=bundle, wheel=bundle, via=copy, app_data_dir=/Users/kecci/Library/Application Support/virtualenv)
    added seed packages: pip==21.0.1, setuptools==52.0.0, wheel==0.36.2
  activators BashActivator,CShellActivator,FishActivator,PowerShellActivator,PythonActivator,XonshActivator
```

3. Use virtual environment:
```
source venv/bin/activate
```

4. After we have virtual environment, install flask
```
(venv) $ pip install flask
```

5. Check if we've already install flask
```
$ python3

Python 3.9.1 (default, Feb  3 2021, 07:38:02)
[Clang 12.0.0 (clang-1200.0.32.29)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> import flask
```
If no error it should be flask already installed

## Hello Application
1. make directory app
```
(venv) $ mkdir app
```

2. create file `app/__init__.py` (as init)
```py
from flask import Flask

app = Flask(__name__)

from app import routes
```
Note: must with `__`

3. create file `app/routes.py` (as routes)
```py
from app import app

@app.route('/')
@app.route('/index')
def index():
    return "Hello, World!"
```

4. create file `python_flask.py` (as main directory)
```
from app import app
```

so we can see the tree like this
```
python-flask/
  venv/
  app/
    __init__.py
    routes.py
  python_flask.py
```

## Run application

to run app, we can set env flask_app to our main file, then execute flask run
```
FLASK_APP=python_flask.py flask run
```

output:
```
 * Serving Flask app "python_flask"
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
```

we can access to:
```
http://localhost:5000/
or
http://localhost:5000/index
```

