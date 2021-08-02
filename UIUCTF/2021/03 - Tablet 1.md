![[03 - tablet1.png]]

We download the file and unzip it.
We are given a number of files to work through.

I manually went through the info to find anything of interest and eventually found a file called webssh.db

![[03 - websshdb.png]]

In there we find a private ssh key, password, host, user and port.

![[03 - details.png]]

We save the ssh private key.
We run the following command

![[03 - nossh.png]]

Seems like we can only use sftp.

![[03 - sftp.png]]

We do a ls -la and see what we have. We find a .bash_history.
Let's copy that file and see what the user has run.

![[03 - bash_history.png]]

We see the user copied the exfiltrated data to /srv/...

![[03 - exfiltrated.png]]

We copy this file to our machine.

![[03 - important_data.png]]

We view the image and we see the flag.

![[03 - red sus.png]]
