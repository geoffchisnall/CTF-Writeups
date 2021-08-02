![[01 - HIVE Registration Office.png]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/RTLCTF/2021/images/01%20-%20HIVE%20Registration%20Office.png)

We had to download a config.zip file which contained the following:

![[01 - config contents.png]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/RTLCTF/2021/images/01%20-%20config%20contents.png)

I downloaded a tool called AccessData Registry Viewer.

I loaded the SAM file and immediately I browsed to where the user information was located.

Here we find both the login count and the last time the user changed their password.

![[01  - user_info.png]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/RTLCTF/2021/images/01%20%20-%20user_info.png)

Last Password Change Time - 15:54:49 2021/07/04
Logon Count - 2817

Next up I loaded the SYSTEM file.

Here I searched for BIOSVendor and we find what we are looking for.

![[01 - machine_info.png]](https://github.com/geoffchisnall/CTF-Writeups/blob/main/RTLCTF/2021/images/01%20-%20machine_info.png)

Manufacturer's name: HP
BIOS Vendoer's Name: Insyde

Combining them to the flag format we get the flag.

RTL{15:54:49 2020/04/19_HP_Insyde_2817}

