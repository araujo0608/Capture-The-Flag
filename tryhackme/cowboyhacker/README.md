# WRITE-UP COWBOYHACKER

![homepage](files/ctf-homepage.png)

[Click here to access the room](https://tryhackme.com/room/cowboyhacker#)
---

## QUESTION 01: Find open ports on the machine

> Well, just do a simple scan. You can use any port scan tool you prefer. I gonna use nmap.

> I like save nmap scan in other file, but if you don't like just run `nmap -A [target]`

**STEP 01:** Run `nmap -A [target] > file.txt`

In my case:
  `nmap -A 10.10.81.241 > scan.txt`

Result:

  ![scan](files/nmap-scan.png)

  * Nice, three ports are open.
    * 21 `ftp`
    * 22 `ssh`
    * 80 `http`

  * The FTP have Anonymous login allowed, interesting!

  * And we have a website running on port 80 with Apache 2.4.18

  <br>

  ![website](files/website.png)

  Always check the source code, it may have sensitive information commented out.

  ![source](files/source-webpage.png)

  But in this case, i found nothing relevant. Only possible usernames to log into ssh.
