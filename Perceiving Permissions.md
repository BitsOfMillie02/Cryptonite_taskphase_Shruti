## Section 1: Changing File Ownership
`hacker@permissions~changing-file-ownership:~$ chown hacker /flag`
<br/>
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
<br/>
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
<br/>
`hacker@permissions~fun-with-groups-names:~$ cat /flag`
```
pwn.college{kReBYEvfwgNsH5vTkpkDyBHqw19.dJzNyUDL4EDO0czW}
```
## Section 4: Changing Permissions
`hacker@permissions~changing-permissions:~$ ^C`
<br/>
`hacker@permissions~changing-permissions:~$ ls -l /flag`
```
-r-------- 1 root root 58 Oct 18 13:11 /flag
```
`hacker@permissions~changing-permissions:~$ chmod a+r /flag`
<br/>
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
<br/>
`hacker@permissions~executable-files:~$ /challenge/run`
```
Successful execution! Here is your flag:
pwn.college{8FRA5OLxfAQ34gEYffA_RKj6Pm5.dJTM2QDL4EDO0czW}
```
## Section 6: Permission Tweaking Practise
```
Commands:
1.	chmod u-w /challenge/pwn
2.	chmod uo+x /challenge/pwn
3.	chmod u-r /challenge/pwn
4.	chmod g-r /challenge/pwn
5.	chmod ug+wx /challenge/pwn
6.	chmod g+r /challenge/pwn
7.	chmod a-wx /challenge/pwn
8.	chmod u+wx /challenge/pwn
Code :
You set the permissions incorrectly! Restarting the game!
```
`hacker@permissions~permission-tweaking-practice:~$ /challenge/run`
```
Round 0 (of 8)!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": r--r--r--
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
```
`hacker@permissions~permission-tweaking-practice:~$ chmod u-w /challenge/pwn`
```
You set the correct permissions!
Round 1 (of 8)!

Current permissions of "/challenge/pwn": r--r--r--
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": r-xr--r-x
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
```
`hacker@permissions~permission-tweaking-practice:~$ chmod uo+x /challenge/pwn`
```
You set the correct permissions!
Round 2 (of 8)!

Current permissions of "/challenge/pwn": r-xr--r-x
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": --xr--r-x
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
```
`hacker@permissions~permission-tweaking-practice:~$ chmod u-r /challenge/pwn`
```
You set the correct permissions!
Round 3 (of 8)!

Current permissions of "/challenge/pwn": --xr--r-x
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": --x---r-x
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
```
`hacker@permissions~permission-tweaking-practice:~$ chmod g-r /challenge/pwn`
```
You set the correct permissions!
Round 4 (of 8)!

Current permissions of "/challenge/pwn": --x---r-x
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": -wx-wxr-x
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
```
`hacker@permissions~permission-tweaking-practice:~$ chmod ug+wx /challenge/pwn`
```
You set the correct permissions!
Round 5 (of 8)!

Current permissions of "/challenge/pwn": -wx-wxr-x
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": -wxrwxr-x
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
```
`hacker@permissions~permission-tweaking-practice:~$ chmod g+r /challenge/pwn`
```
You set the correct permissions!
Round 6 (of 8)!

Current permissions of "/challenge/pwn": -wxrwxr-x
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": ---r--r--
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
```
`hacker@permissions~permission-tweaking-practice:~$ chmod a-wx /challenge/pwn`
```
You set the correct permissions!
Round 7 (of 8)!

Current permissions of "/challenge/pwn": ---r--r--
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -wxr--r--
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
```
`hacker@permissions~permission-tweaking-practice:~$ chmod u+wx /challenge/pwn`
```
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
```
`hacker@permissions~permission-tweaking-practice:~$ chmod u+r /flag`
<br/>
`hacker@permissions~permission-tweaking-practice:~$ cat /flag`
```
pwn.college{0XNE4MienKRBlmBFLzOEd1lFVZX.dBTM2QDL4EDO0czW}
```
## Section 7: Permissions Setting Practise
```
Commands :
1.	chmod u=x,g=rx,o=wx /challenge/pwn
2.	chmod u=x,g=r,o-rwx /challenge/pwn
3.	chmod u-rwx,g=x,o=rw /challenge/pwn
4.	chmod u=rwx,g=wx,o=x /challenge/pwn
5.	chmod u=w,g=wx,o=wx /challenge/pwn
6.	chmod u=w,g=wx,o-rwx /challenge/pwn
7.	chmod u=rx,g=x,o=rx /challenge/pwn
8.	chmod u=rx,g=rx,o=w /challenge/pwn
Code:
```
`hacker@permissions~permissions-setting-practice:~$ /challenge/run`
```
Round 0 (of 8)!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": --xr-x-wx
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
```
`hacker@permissions~permissions-setting-practice:~$ chmod u=x,g=rx,o=wx /challenge/pwn`
```
You set the correct permissions!
Round 1 (of 8)!

Current permissions of "/challenge/pwn": --xr-x-wx
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": --xr-----
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
```
`hacker@permissions~permissions-setting-practice:~$ chmod u=x,g=r,o-rwx /challenge/pwn`
```
You set the correct permissions!
Round 2 (of 8)!

Current permissions of "/challenge/pwn": --xr-----
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -----xrw-
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
```
`hacker@permissions~permissions-setting-practice:~$ chmod u-rwx,g=x,o=rw /challenge/pwn`
```
You set the correct permissions!
Round 3 (of 8)!

Current permissions of "/challenge/pwn": -----xrw-
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rwx-wx--x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
```
`hacker@permissions~permissions-setting-practice:~$ chmod u=rwx,g=wx,o=x /challenge/pwn`
```
You set the correct permissions!
Round 4 (of 8)!

Current permissions of "/challenge/pwn": rwx-wx--x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": -w--wx-wx
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
```
`hacker@permissions~permissions-setting-practice:~$ chmod u=w,g=wx,o=wx /challenge/pwn`
```
You set the correct permissions!
Round 5 (of 8)!

Current permissions of "/challenge/pwn": -w--wx-wx
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": -w--wx---
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
```
`hacker@permissions~permissions-setting-practice:~$ chmod u=w,g=wx,o-rwx /challenge/pwn`
```
You set the correct permissions!
Round 6 (of 8)!

Current permissions of "/challenge/pwn": -w--wx---
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": r-x--xr-x
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
```
`hacker@permissions~permissions-setting-practice:~$ chmod u=rx,g=x,o=rx /challenge/pwn`
```
You set the correct permissions!
Round 7 (of 8)!

Current permissions of "/challenge/pwn": r-x--xr-x
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r-xr-x-w-
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
```
`hacker@permissions~permissions-setting-practice:~$ chmod u=rx,g=rx,o=w /challenge/pwn`
```
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
```
`hacker@permissions~permissions-setting-practice:~$ chmod u+r /flag`
<br/>
`hacker@permissions~permissions-setting-practice:~$ cat /flag`
```
pwn.college{YAZe4F4QnMGNQcC6tJiHVh5jhjy.dNTM5QDL4EDO0czW}
```
## Section 8: The SUID Bit
`hacker@permissions~the-suid-bit:~$ chmod u+s /challenge/getroot`
`hacker@permissions~the-suid-bit:~$ /challenge/getroot`
```
SUCCESS! You have set the suid bit on this program, and it is running as root!
Here is your shell...
root@permissions~the-suid-bit:~# cat /flag
pwn.college{0ndAoFIwrJwDFuGtcm6-VR4it-g.dNTM2QDL4EDO0czW}
```


