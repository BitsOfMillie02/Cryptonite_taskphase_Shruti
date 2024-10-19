## Section 1: Changing File Ownership
`hacker@permissions~changing-file-ownership:~$ chown hacker /flag`
`hacker@permissions~changing-file-ownership:~$ ls -l`
```
total 28
-rw-r--r-- 1 hacker hacker   4 Oct  9 05:43 COLLEGE
-rw-r--r-- 1 hacker hacker   8 Oct  9 06:00 PWN
-rw-r--r-- 1 hacker hacker   0 Oct  9 15:08 college
-rw-r--r-- 1 root   hacker  58 Oct  9 17:37 f
-rw-r--r-- 1 hacker hacker 829 Oct  9 05:54 instructions
-rw-r--r-- 1 hacker hacker  93 Oct  9 05:54 myflag
lrwxrwxrwx 1 hacker hacker  25 Oct  6 13:06 not-the-flag -> /home/hacker/not-the-flag
-rw-r--r-- 1 root   hacker  77 Oct  9 17:13 output
-rw-r--r-- 1 hacker hacker 435 Oct  9 05:51 the-flag
```
`hacker@permissions~changing-file-ownership:~$ cat /flag`
```
pwn.college{wPA5NtkNf5l0YARKq4oz1tKYDzM.dFTM2QDL4EDO0czW}
```
## Section 2: Groups And Files
`hacker@permissions~groups-and-files:~$ chgrp hacker /flag`
`hacker@permissions~groups-and-files:~$ cat /flag`
```
pwn.college{Ixopmqi1kfVzcwKoSTBJ929fV9A.dFzNyUDL4EDO0czW}
```
## Section 3: Fun With Groups Names
`hacker@permissions~fun-with-groups-names:~$ id`
```
uid=1000(hacker) gid=1000(grp26362) groups=1000(grp26362)
```
`hacker@permissions~fun-with-groups-names:~$ chgrp grp26362 /flag`
`hacker@permissions~fun-with-groups-names:~$ cat /flag`
```
pwn.college{kReBYEvfwgNsH5vTkpkDyBHqw19.dJzNyUDL4EDO0czW}
```
## Section 4: Changing Permissions
`hacker@permissions~changing-permissions:~$ ^C`
`hacker@permissions~changing-permissions:~$ ls -l /flag`
```
-r-------- 1 root root 58 Oct 18 13:11 /flag
```
`hacker@permissions~changing-permissions:~$ chmod a+r /flag`
`hacker@permissions~changing-permissions:~$ cat /flag`
```
pwn.college{4HSGod_AgWjcVk5_bDUHpSAG3-y.dNzNyUDL4EDO0czW}
```
## Section 5: Executable Files
`hacker@permissions~executable-files:~$ ls -l /challenge/run`
```
-r--r--r-- 1 hacker hacker 32 Jul  4 06:37 /challenge/run
```
`hacker@permissions~executable-files:~$ chmod a+x /challenge/run`
`hacker@permissions~executable-files:~$ /challenge/run`
```
Successful execution! Here is your flag:
pwn.college{8FRA5OLxfAQ34gEYffA_RKj6Pm5.dJTM2QDL4EDO0czW}
```
## Section 6: Permission Tweaking Practise
## Section 7: Permissions Setting Practise
## Section 8: The SUID Bit
`hacker@permissions~the-suid-bit:~$ chmod u+s /challenge/getroot`
`hacker@permissions~the-suid-bit:~$ /challenge/getroot`
```
SUCCESS! You have set the suid bit on this program, and it is running as root!
Here is your shell...
root@permissions~the-suid-bit:~# cat /flag
pwn.college{0ndAoFIwrJwDFuGtcm6-VR4it-g.dNTM2QDL4EDO0czW}
```


