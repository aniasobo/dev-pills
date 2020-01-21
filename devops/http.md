# HTTP

* [Source: HTTP zine by Julia Evans](https://wizardzines.com/zines/http/)

**HTTP** is the **protocol** that the browser uses when it visits a website.

## **HTTP/2** is a new version of HTTP:

* all methods, status codes, request/response bodies and headers stay the same
* it's faster than HTTP because of its
  *  binary format
  *  compressed headers
  *  ability to receive mulitple requests on the same TCP connection at the same time
* easy switch on many CDNs, Nginx even if your server only supports HTTP/1.1

## CORS - cross-origin resource sharing

* cross-origin requests are not allowed by default
* `Access-Control-Allow-Origin` header controls which requests are allowed
