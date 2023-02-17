THere is I try to create local server which is run with SSL on port 443. 
language: Python 3
OS: Windows 11 home

### Creating a Self-Signed SSL Certificate

```
openssl genrsa -aes256 -passout pass:gsahdg -out server.pass.key 4096
openssl rsa -passin pass:gsahdg -in server.pass.key -out server.key
rm server.pass.key  
openssl req -new -key server.key -out server.csr

openssl x509 -req -sha256 -days 365 -in server.csr -signkey server.key -out server.crt

```

### Python3 Code

```
from flask import Flask
app = Flask(__name__)
app.run('0.0.0.0', debug=True, port=443, ssl_context=('C:\\Users\\test2\\Documents\\funproject\\server\\server.crt', 'C:\\Users\\test2\\Documents\\funproject\\server\\server.key'))
```



## Refrence 
* [https://kracekumar.com/post/54437887454/ssl-for-flask-local-development/](https://kracekumar.com/post/54437887454/ssl-for-flask-local-development/)
* https://devcenter.heroku.com/articles/ssl-certificate-self
