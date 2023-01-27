# Internal IP Address Disclosure
On any IIS server where you get a 302 you can try stripping the Host header and using HTTP/1.0 and inside the response the Location header could point you to the internal IP address:
```
nc -v domain.com 80
openssl s_client -connect domain.com:443
```
Response disclosing the internal IP:
```
GET / HTTP/1.0       

HTTP/1.1 302 Moved Temporarily
Cache-Control: no-cache
Pragma: no-cache
Location: https://192.168.5.237/owa/
Server: Microsoft-IIS/10.0
X-FEServer: NHEXCHANGE2016
```
# Execute .config files
You can upload .config files and use them to execute code. One way to do it is appending the code at the end of the file inside an HTML comment
More information and techniques to exploit this vulnerability here [https://soroush.secproject.com/blog/2014/07/upload-a-web-config-file-for-fun-profit/](https://soroush.secproject.com/blog/2014/07/upload-a-web-config-file-for-fun-profit/)

# IIS Discovery Bruteforce
Download the list from hacktricks here :
