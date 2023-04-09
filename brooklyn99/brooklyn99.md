nmap results

┌──(kali㉿kali)-[~/…/tryhackme/thm/brooklyn99/nmap_results]
└─$ nmap -sC -sV -vv 10.10.41.112 -oA results
Starting Nmap 7.93 ( https://nmap.org ) at 2023-04-08 20:02 EDT
NSE: Loaded 155 scripts for scanning.
NSE: Script Pre-scanning.
NSE: Starting runlevel 1 (of 3) scan.
Initiating NSE at 20:02
Completed NSE at 20:02, 0.00s elapsed
NSE: Starting runlevel 2 (of 3) scan.
Initiating NSE at 20:02
Completed NSE at 20:02, 0.00s elapsed
NSE: Starting runlevel 3 (of 3) scan.
Initiating NSE at 20:02
Completed NSE at 20:02, 0.00s elapsed
Initiating Ping Scan at 20:02
Scanning 10.10.41.112 [2 ports]
Completed Ping Scan at 20:02, 0.09s elapsed (1 total hosts)
Initiating Parallel DNS resolution of 1 host. at 20:02
Completed Parallel DNS resolution of 1 host. at 20:02, 0.00s elapsed
Initiating Connect Scan at 20:02
Scanning 10.10.41.112 [1000 ports]
Discovered open port 21/tcp on 10.10.41.112
Discovered open port 22/tcp on 10.10.41.112
Discovered open port 80/tcp on 10.10.41.112
Completed Connect Scan at 20:02, 4.00s elapsed (1000 total ports)
Initiating Service scan at 20:02
Scanning 3 services on 10.10.41.112
Completed Service scan at 20:02, 6.20s elapsed (3 services on 1 host)
NSE: Script scanning 10.10.41.112.
NSE: Starting runlevel 1 (of 3) scan.
Initiating NSE at 20:02
NSE: [ftp-bounce 10.10.41.112:21] PORT response: 500 Illegal PORT command.
Completed NSE at 20:02, 2.86s elapsed
NSE: Starting runlevel 2 (of 3) scan.
Initiating NSE at 20:02
Completed NSE at 20:02, 0.65s elapsed
NSE: Starting runlevel 3 (of 3) scan.
Initiating NSE at 20:02
Completed NSE at 20:02, 0.00s elapsed
Nmap scan report for 10.10.41.112
Host is up, received syn-ack (0.088s latency).
Scanned at 2023-04-08 20:02:33 EDT for 14s
Not shown: 997 closed tcp ports (conn-refused)
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
| ssh-hostkey: 
|   2048 167f2ffe0fba98777d6d3eb62572c6a3 (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDQjh/Ae6uYU+t7FWTpPoux5Pjv9zvlOLEMlU36hmSn4vD2pYTeHDbzv7ww75UaUzPtsC8kM1EPbMQn1BUCvTNkIxQ34zmw5FatZWNR8/De/u/9fXzHh4MFg74S3K3uQzZaY7XBaDgmU6W0KEmLtKQPcueUomeYkqpL78o5+NjrGO3HwqAH2ED1Zadm5YFEvA0STasLrs7i+qn1G9o4ZHhWi8SJXlIJ6f6O1ea/VqyRJZG1KgbxQFU+zYlIddXpub93zdyMEpwaSIP2P7UTwYR26WI2cqF5r4PQfjAMGkG1mMsOi6v7xCrq/5RlF9ZVJ9nwq349ngG/KTkHtcOJnvXz
|   256 2e3b61594bc429b5e858396f6fe99bee (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBItJ0sW5hVmiYQ8U3mXta5DX2zOeGJ6WTop8FCSbN1UIeV/9jhAQIiVENAW41IfiBYNj8Bm+WcSDKLaE8PipqPI=
|   256 ab162e79203c9b0a019c8c4426015804 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIP2hV8Nm+RfR/f2KZ0Ub/OcSrqfY1g4qwsz16zhXIpqk
80/tcp open  http    syn-ack Apache httpd 2.4.29 ((Ubuntu))
|_http-server-header: Apache/2.4.29 (Ubuntu)
| http-methods: 
|_  Supported Methods: GET POST OPTIONS HEAD
|_http-title: Site doesn't have a title (text/html).
Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

NSE: Script Post-scanning.
NSE: Starting runlevel 1 (of 3) scan.
Initiating NSE at 20:02
Completed NSE at 20:02, 0.00s elapsed
NSE: Starting runlevel 2 (of 3) scan.
Initiating NSE at 20:02
Completed NSE at 20:02, 0.00s elapsed
NSE: Starting runlevel 3 (of 3) scan.
Initiating NSE at 20:02
Completed NSE at 20:02, 0.00s elapsed
Read data files from: /usr/bin/../share/nmap
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 14.42 seconds






