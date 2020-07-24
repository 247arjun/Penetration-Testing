# Web Applications
Applications running on web servers, accessible via web browsers.

## HTTP Protocol Basics

HTTP works on top of TCP protocol = After a TCP connection is established

Request <> Response

HTTP is a stateless protocol

HTTP Message format
```
Headers \r \n
\r \n
Message Body \r \n
```
Header contains a request followed by some header fields.

### HTTP Request

Request has a verb (`GET`, `POST` etc.)

Verb is followed by path (`/`) and protocol version (`HTTP 1.1`).

Each field has the format `Header-name: header value`

#### Example HTTP Request

```
GET / HTTP/1.1
Host: www.google.com
User-Agent: Mozilla/5.0
Accept: text/html
Accept-Language: en-US, en;q=0.5
Accept-Encoding: gzip, deflate
Connection: keep-alive
```
The `User-Agent` reveals the local OS version to the server.

### HTTP Response

HTTP Error Codes

#### Example HTTP Response

```
HTTP/1.1 200 OK
Date: Wed, 19 Nov 2019 11:24:31 GMT
Cache-Control: private, max-age=0
Content-Type: text/html
Content-Encoding: gzip
Server: Apache/2.2.15 (CentOS)
Content-Length: 99032


<Page Content>
```
### HTTPS
HTTP over SSL/TLS runs clear-text HTTP over SSL/TLS, a cryptographic protocol.

HTTPS does not protect against XSS/SQLi

## HTTP Cookies

Make HTTP stateful

Server can set a cookie via the `Set-Cookie` HTTP header field, in a response message.

A cookie contains:
- The actual content
- An expiration date
- A path
- The domain
- Optional flags

```
Set-Cookie: ID=Value; expires=Thu, 21-May-2015 13:12:30 GTM; path=/; domain=.example.site; HttpOnly
```

## Sessions
A mechanism that lets a website store variables specific for a given visit on the **server side**.

Each user session is identified by a **session id** or token assigned to the client. 

These may be saved as session cookies by the client.

Session cookies just contain a single parameter value pair referring to the session.

```
SESSION=0WcTsaaf80
PHPSESSID=13ljAKasdf
JSESSIONID=u2oiASD4ja
```

Session IDs can also be transmitted via `GET` requests.

`http://example.site/resource.php?sessid=k27rds7h8w`


## Same Origin Policy (SOP)
Prevents JavaScript code from getting/setting properties on a resource coming from a **different origin**.

The browser uses `Protocol`, `Hostname` and `Port` to determine if JS can access a resource.

SOP only applies to the actual code of a script.

## Burp Suite

Intercepting proxy

Allows you to:
- intercept requests and responses between browser and server (Proxy)
- - Build requests manually (Repeater)
- Crawl a website
- Fuzz a web app

