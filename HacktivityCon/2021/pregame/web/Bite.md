![[Bite]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/Bite/bite.png)

First off we browse around and we can click the links on the right and we notice the following.

![[Bite]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/Bite/lfi_1.png)

We try some LFI for `flag.txt` but we get .php appended to it.

![[Bite]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/Bite/lfi_2.png)

We try `flag` and it says the flag is at `/flag.txt`.

![[Bite]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/Bite/lfi_3.png)

We know that it is appending .php to whatever we add to it.

![[Bite]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/Bite/lfi_4.png)

Let's try add a null byte by adding `%00`

![[Bite]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/HacktivityCon/2021/pregame/images/Bite/lfi_flag.png)

BINGO!
