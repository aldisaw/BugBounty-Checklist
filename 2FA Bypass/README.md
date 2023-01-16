## 1. Response and Status Code Manipulation
```
1) Enter correct OTP
2) Intercept response
3) Enter wrong OTP
4) Intercept response and change it with correct response

If Status Code is 4xx
Change it to 200 OK
```

## 2. Direct bypass
```
To bypass 2FA, just try to access the next endpoint directly (you need to know the path of the next endpoint). 
If this doesn't work, try to change the Referrer header as if you came from the 2FA page

example :
site.com/otp -> site.com/new_password
```

## 3. Brute Force
```
Is there any limit on the number of codes that you can try, so you can just brute force it? Be careful with a possible "silent" rate limit, 
always try several codes and then the real one to confirm the vulnerability.
```
## 4. Developer’s Check
```
1) Right click on submit button (continue or etc ...)
2) Inspect element
3) Fuctions like “checkOTP(event)”
4) Type function in console
```
[https://shahjerry33.medium.com/otp-bypass-developers-check-5786885d55c6](https://shahjerry33.medium.com/otp-bypass-developers-check-5786885d55c6)

## 5. Reusing Token
```
Maybe you can reuse an already used token inside the account to authenticate.
```

## 6. Sharing unused tokens
```
Request 2 tokens from account A and X. Use the A's token in X's account.
```
## 7. Password Reset Function
```
1) Create an Account and Turn On 2FA.
2) Logout from that account.
3) Now, Go to forget Password-Reset page.
4) Change your password.
5) Now try to log in.
6) If you are not asked to enter a 2FA code, You can report.
```
## 8. OAuth
```
Login using OAuth platform (Google, Facebook...) to bypass 2FA.
```
## 10. CSRF/Clickjacking
```
Check if there is a CSRF or a Clickjacking vulnerability to disable the 2FA.
```
## 11. Bypass 2FA arbitrary input
```
null 
000000
0
ASADSas
```
## 12. Information Disclosure
```
Check whether 2FA page is disclosing some sensitive info that you didn't know previously (like mobile number).
```
## 13. Bypass using JSON
```
{
        "code":[
                "1000",
                "1001",
                "1002",
                "1003",
                "1004",
                ...
                "9999"
                ]
}
```

### Reference
- [https://www.youtube.com/watch?v=X2WfhBYQ2fY](https://www.youtube.com/watch?v=X2WfhBYQ2fY)
- https://book.hacktricks.xyz/pentesting-web/2fa-bypass
