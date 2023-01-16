##1 . Login
```
- Check if you are able to brute force the password
- Test for OAuth misconfigurations
- Check if you are able to bruteforce the login OTP
- Check for JWT mesconfigurations
- Test for SQL injection to bypass authenticationadmin" or 1=1;--
- Check if the application validates the OTP or Token
```
## 2. Password Reset
```
- Check if you are able to brute force the password reset OTP
- Test for token predectability
- Test for JWT misconfigurations
- Check if the password reset endpoint is vulnerable to IDOR
- Check if the password reset endpoint is vulnerable to Host Header injection
- Check if the password reset endpoint is leaking the token or OTP in the HTTP response
- Check if the application validates the OTP or Token
- Test for HTTP parameter Pollution (HPP)
```

## 3. XSS to Account Takeover
```
- If the application does not use auth token or you can’t access the cookies because the “HttpOnly” flag, 
  you can obtain the CSRF token and craft a request to change the user’s email or password
- Try to exfiltrate the cookies
- Try to exfiltrate the Auth Token
- If the cookie’s “domain” attribute is set, search for xss in the subdomains and use it to exfiltrate the cookies
```

## 4. CSRF to Account Takeover:
```
- Check if the email update endpoint is vulnerable to CSRF
- Check if the password change endpoint is vulnerable to CSRF
```

## 5. IDOR to Account Takeover:
```
- Check if the email update endpoint is vulnerable to IDOR
- Check if the password change endpoint is vulnerable to IDOR
- Check if the password reset endpoint vulnerable to IDOR
```
## 6. Subdomain takeover
```
- first-order: check if you can takeover xyz.example.com, you can host any malicious code to steal users info or cookies
- second-order (broken link hijacking): if you found a broken link in a webpage (https://nonexistentlink.com/app.js) 
  and you can takeover this domain, you can host any malicious javascript file and use it to steal users info or cookies
```
