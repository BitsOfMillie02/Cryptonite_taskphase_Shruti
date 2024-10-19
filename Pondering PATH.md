## Section 1: The PATH Variable
`hacker@path~the-path-variable:~$ PATH=""`
<br/>
`hacker@path~the-path-variable:~$ /challenge/run`
```
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{AcTg3arnznG_QpbBROo1ktykuCe.dZzNwUDL4EDO0czW}
```
## Section 2: Setting PATH
`hacker@path~setting-path:~$ ls /challenge/more_commands/`
```
win
```
`hacker@path~setting-path:~$ PATH=/challenge/more_commands/`
<br/>
`hacker@path~setting-path:~$ /challenge/run`
```
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{YIzl7r9ODdaRJXxDqV0ozsXk1wB.dVzNyUDL4EDO0czW}
```
## Section 3: Adding Commands
## Section 4: Hijacking Commands
