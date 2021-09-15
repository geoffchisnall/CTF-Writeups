![[WaffleLand]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/WaffleLand/waffleland.png)

We browse to the site and we see a search bar and login button to the right.

![[WaffleLand]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/WaffleLand/waffle1.png)

Let's check for SQLi.

![[WaffleLand]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/WaffleLand/waffle2.png)

We get an error so now we can start enumerating for things.
![[WaffleLand]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/WaffleLand/waffle_sqlii_1.png)

**NOTE**
I FORGOT TO TAKE A SCREEN SHOT OF THE FOLLOWING
When I tried `'UNION SELECT NULL-- -` I got a 403 Forbidden error which was telling me there was some kind of WAF preventing me injecting thus it meant I needed to escape things.

We can do this by using `/**/`

Let's try get the ammount of columns in the database.

![[WaffleLand]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/WaffleLand/waffle_sqli_2.png)

We continue to add more `NULL` until we get something back.

![[WaffleLand]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/WaffleLand/waffle_sqli_3.png)

![[WaffleLand]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/WaffleLand/waffle_sqli_4.png)

I guessed that there is a database called `user` - From previous CTF experiences.

![[WaffleLand]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/WaffleLand/waffle_sqli_5.png)

Then we just guess the columns for username and password and we get given the username and password.

![[WaffleLand]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/WaffleLand/waffle_sqli_6.png)

We use this to login to the website.

![[WaffleLand]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/WaffleLand/waffle_flag.png)

Flag given!
