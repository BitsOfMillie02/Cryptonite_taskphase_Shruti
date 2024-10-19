## Section1: Becoming Root With SU
`hacker@users~becoming-root-with-su:~$ su`
```
Password: where password is hack-the-planet
```
`root@users~becoming-root-with-su:/home/hacker# cat /flag`
```
pwn.college{wcPTsqNhaPN_lB7I-akJfqjXGPX.dVTN0UDL4EDO0czW}
```
## Section 2: Other Users With SU
`hacker@users~other-users-with-su:~$ su zardus`
```
Password: where the password is dont-hack-me
```
`zardus@users~other-users-with-su:/home/hacker$ /challenge/run`
```
Congratulations, you have become Zardus! Here is your flag:
pwn.college{wBH5XRv88qo7f0-iXNJ3CteTbjV.dZTN0UDL4EDO0czW}
```
## Section 3: Cracking Passwords
`hacker@users~cracking-passwords:~$ john /challenge/shadow-leak`
```
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
aardvark         (zardus)
1g 0:00:00:21 100% 2/3 0.04549g/s 264.9p/s 264.9c/s 264.9C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
```
`hacker@users~cracking-passwords:~$ su zardus`
```
Password:
```
`zardus@users~cracking-passwords:/home/hacker$ /challenge/run`
```
Congratulations, you have become Zardus! Here is your flag:
pwn.college{MnfdsuHihsOFjj-tkJxopE9w1PO.ddTN0UDL4EDO0czW}
```
## Section 4: Using Sudo
`hacker@users~using-sudo:~$ sudo cat /flag`
```
pwn.college{4zA3lBO_8AZogQ6knHMk5UtUSoa.dhTN0UDL4EDO0czW}
```
