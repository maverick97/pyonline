PyOnline
========
PyOnline is a online Python interpreter.

Details
-------
The backend (Python interpreter) is actually a web application made with [Google App Engine](https://cloud.google.com/products/app-engine/).

It can be accessed via www.pyonlineapi.appspot.

The user interface is built with Touchdevelop where it constantly interacts with the web application.

So basically, any application that can access the web can use this interpreter.

Usage
-----
Each user will need to access the API with a user_id, which is
generated on the client's side. Actually, anything will do, as long as it is randomly generated and is 8 characters long.

**Example:**
`http:/www.pyonlineapi.appspot/process/<user_id>`

The code will be sent via a POST request in a url encoded manner.
Then, accessed at the same url with a GET request.

**Example:**
```python
>> from urllib import urlencode
>> from urllib2 import urlopen
>> # Urlencode key-value pair, where key must be 'code'
>> data = { 'code': "print 'hello world'" }
>> data = urlencode(data)
>> # Send POST request with extra data parameter in urlopen
>> urlopen('http://www.pyonline.appspot/process/eRbBHp2c', data)
>> result = urlopen('http://www.pyonline.appspot/process/eRbBHp2c')
>> result.read() # hello world
hello world
```

Authors and Contributors
------------------------
Maverick Chan

Support or Contact
------------------
Having trouble with PyOnline? Contact Maverick at guanhao3797@gmail.com or through @guanhao97 on Twitter.
