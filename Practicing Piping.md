## Section 1: Redirecting Output
`hacker@piping~redirecting-output:~$ echo PWN > COLLEGE`
<br/>
'>' charcater is used to redirect the files. In this challenge I redirected the file PWN to COLLEGE using the '>' character.
<br/>
## Section 2: Redirecting more output

`hacker@piping~redirecting-more-output:~$ /challenge/run > myflag`
<br/>
Redirecting to myflag
<br/>
```
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{Uo98NGAqPe-D_waB9kuzNsJuV_8.dVjN1QDL4EDO0czW}
```
## Section 3: APPENDING OUTPUT
<br/>
`hacker@piping~appending-output:~$ /challenge/run >> /home/hacker/the-flag`
<br/>
```
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do
the first write directly to the file, and the second write, I'll do to stdout
(if it's pointing at the file). If you redirect the output in append mode, the
second write will append to (rather than overwrite) the first write, and you'll
get the whole flag!

hacker@piping~appending-output:~$ cat /home/hacker/the-flag
 |
\|/ This is the first half:
 v
pwn.college{kgDG-k30G0-5fMIYVLDohf9eklC.ddDM5QDL4EDO0czW}
                              ^
     that is the second half /|\
```
<br/>
## Section 4: Redirecting errors
`hacker@piping~redirecting-errors:~$ /challenge/run > myflag 2> instructions`
<br/>
`hacker@piping~redirecting-errors:~$ cat myflag`
<br/>
[FLAG] Here is your flag
<br/>
This challenge helps us understand how to redirect errors. It has file desciptors which are the numbered communication channel, O standing for input, 1 for output which is the default and 2 for standard error. 
In this challenge i redirected using FD 2.
<br/>
