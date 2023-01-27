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
Download the list from hacktricks here : https://github.com/aldisaw/BugBounty-Checklist/blob/main/Internet%20Information%20Services%20(IIS)/iisfinal.txt

# Microsoft IIS tilde character “~” Vulnerability/Feature – Short File/Folder Name Disclosure
You can try to enumerate folders and files inside every discovered folder (even if it's requiring Basic Authentication) using this technique.
The main limitation of this technique if the server is vulnerable is that it can only find up to the first 6 letters of the name of each file/folder and the first 3 letters of the extension of the files.
You can use https://github.com/irsdl/IIS-ShortName-Scanner to test for this vulnerability:
```
java -jar iis_shortname_scanner.jar 2 20 http://10.13.38.11/dev/dca66d38fd916317687e1390a420c3fc/db/
```

# ASP.NET Trace.AXD enabled debugging
ASP.NET include a debugging mode and its file is called trace.axd.
It keeps a very detailed log of all requests made to an application over a period of time.
This information includes remote client IP's, session IDs, all request and response cookies, physical paths, source code information, and potentially even usernames and passwords.
![112974448-2690b000-915b-11eb-896c-f41c27c44286](https://user-images.githubusercontent.com/22369983/215054422-6e02cd8d-a98d-4252-86a6-adda34219e1d.png)


## Reference
https://book.hacktricks.xyz/network-services-pentesting/pentesting-web/iis-internet-information-services
