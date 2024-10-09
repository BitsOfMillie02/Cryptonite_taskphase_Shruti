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

## Section 4: Redirecting errors
`hacker@piping~redirecting-errors:~$ /challenge/run > myflag 2> instructions`
<br/>
`hacker@piping~redirecting-errors:~$ cat myflag`
<br/>
[FLAG] Here is your flag
<br/>
This challenge helps us understand how to redirect errors. It has file desciptors which are the numbered communication channel, O standing for input, 1 for output which is the default and 2 for standard error. 
In this challenge i redirected using FD 2.

## Section 5: Redirecting Input
`hacker@piping~redirecting-input:~$ echo COLLEGE > PWN`
<br/>
`hacker@piping~redirecting-input:~$ /challenge/run < PWN`
<br/>
```
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read
the value 'COLLEGE' out of it!
```

## Section 6: Grepping stored results
`hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt`
<br/>
```
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
```
<br/>
`hacker@piping~grepping-stored-results:~$ grep 'pwn.college' /tmp/data.txt`
<br/>
pwn.college{knsHTzSsFhZc49WcRH1bYMWt9oE.dhTM4QDL4EDO0czW}
<br/>
In this challenge, I redirected the output and grepped for the flag.

## Section 7: Grepping live output
`hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college`
<br/>
```
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/xpq4yhadyhazkcsggmqd7rsgvxb3kjy4-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{8ee0eeYnIvAA-te6GXJal9mxstF.dlTM4QDL4EDO0czW}
```
<br/>
| which is the pipe operator is used to pipe into standard input to the right of the pipe from the standard output to the left of the pipe.

## Section 8 : Grepping Errors
`hacker@piping~grepping-errors:~$ /challenge/run 2>&1 | grep pwn.college`
<br/>
```
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/xpq4yhadyhazkcsggmqd7rsgvxb3kjy4-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{4a2FsGXEz80QvVtqsl73xmB78nd.dVDM5QDL4EDO0czW}
```
<br/>
>& operator redirects a file descriptor to another file descriptor. We need to convert standard error to standard output by using >& operator.

## Section 9: Duplicating piped data with tee
`hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn | tee output | /challenge/college`
<br/>
`hacker@piping~duplicating-piped-data-with-tee:~$ cat output`
<br/>
```
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "8Quiakr6"
```
<br/>
`hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret 8Quiakr6 | /challenge/college`
```
Processing...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{8Quiakr62IMHr2RCcBhhnw5xalp.dFjM5QDL4EDO0czW}
```

The tee command duplicates data flowing through the pipes to any number of files provided on the command line. In this challenge i passed the secret argument generated to /challenge/pwn.

## Section 10: Writing to multiple programs
`hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee >( /challenge/the ) >( /challenge/planet )`
<br/>
```
This secret data must directly and simultaneously make it to /challenge/the and
/challenge/planet. Don't try to copy-paste it; it changes too fast.
454660661940418040
Congratulations, you have duplicated data into the input of two programs!
```

## Section 11: Split - piping stderr and stdout
`hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack > >( /challenge/planet ) 2> >( /challenge/the )`
<br/>
```
Congratulations, you have learned a redirection technique that even experts
struggle with! Here is your flag:
pwn.college{A6kCXsXm7ai9CYAkzJMS7V8a-V8.dFDNwYDL4EDO0czW}
```
<br/>
