![[TemplateShack]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/TemplateShack/TemplateShack.png)

For this one we have to check the cookies of the website.

![[TemplateShack]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/TemplateShack/page.png)

We find a JWT Token.

![[TemplateShack]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/TemplateShack/jwt_token.png)

We go to `http://www.jwt.io` and paste the token in there.

![[TemplateShack]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/TemplateShack/jwt_token1.png)

We need to crack the secret key of the JWT token so we take the token, add it to a file and use john the ripper to crack it.

![[TemplateShack]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/TemplateShack/jwt_token2.png)

We now edit the  JWT Token on jwt.io again and change `guest` to `admin` and then add the password we found in the `verify signature` section.

![[TemplateShack]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/TemplateShack/jwt_token3.png)

Then we take the final JWT Token and then replace it with the current token in the browser.

![[TemplateShack]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/TemplateShack/jwt_token4.png)

We refresh the page and we see `admin` on the right.

![[TemplateShack]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/TemplateShack/admin_login.png)

We click on it and we get the new admin section.

![[TemplateShack]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/TemplateShack/sb_admin.png)

We click on Charts on the left and we see a 404 error with `/admin/charts.html`

![[TemplateShack]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/TemplateShack/sb_search.png)

Let us check for SSTI vulnerability. We add `{{7*7}}` and we see `/admin/49`. Confirmed this is SSTI.
TryHackMe has an amazing room on SSTI - https://tryhackme.com/room/learnssti

![[TemplateShack]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/TemplateShack/SSTI1.png)

We do some enumeration to find the index position of `subprocess.Popen`

![[TemplateShack]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/TemplateShack/SSTI2.png)

<br>

![[TemplateShack]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/TemplateShack/SSTI3.png)

<br>

![[TemplateShack]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/TemplateShack/SSTI4.png)

We now use the subprocess.Popen to check for RCE. whoami returns the current user.

![[TemplateShack]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/TemplateShack/SSTI5.png)

We do a `cat flag.txt` and we grab the flag.


![[TemplateShack]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/TemplateShack/SSTI6.png)

