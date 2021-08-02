This challenge we were given a photo. 

Doing an exiftool on the file we find something interesting.

![[02 - photo_info.png]]

We get, what looks like hex.
We can convert this using xxd.

![[02 - hex_convert.png]]

We get a pastebin url.

Browsing to it we get the following and find a base64 string.

![[02 - pastebin.png]]

We convert this and we get the flag

![[02 - base64.png]]








