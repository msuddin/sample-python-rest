# Sample-python-rest

## Purpose

Question: What is the purpose of this project?

Answer: To understand how to use REST with Python
* Using Flask - it's a Python micro web framework that acts as a web server listening for REST requests

## Requirements
The relevant Flask Rest library needs to be installed for this API to work (run's in the background and listen for REST calls)
```
pip3 install flask-restful
```

## Instructions
From the root directory of the project, we firstly need to run the Flask web server:
```
python3 app.py
```
This should print out the following output. This indicates that the web server is listening for REST requests on ttp://127.0.0.1:5000/:
```
➜  sample-python-rest git:(master) python3 sample-python-rest/app.py
 * Serving Flask app "app" (lazy loading)
 * Environment: production
   WARNING: This is a development server. Do not use it in a production deployment.
   Use a production WSGI server instead.
 * Debug mode: on
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 630-421-997
```
Now let's perform a curl request:
```
curl http://127.0.0.1:5000/Hero/Batman
```
The expected (or similar) output should be:
```
"Batman"
```

## Implementation Notes
* Parameter name in add_resource must match parameter name in Rest methods e.g.
```
App.py
...
api.add_resource(Hero, '/Hero/<string:get_name>')
...
```
```
Hero.py
...
def get(self, get_name):
...
```
* 