## Section 1: The Root
`hacker@paths~the-root:~$ /pwn`
<br/>
The path which starts from the rrot directory is called as absolute path.
## Section 2: Program And Absolute Paths
`hacker@paths~program-and-absolute-paths:~$ /challenge/run`
<br/>
Executing the challenge program run which is in the challenege directory which is in turn in the / directory.
## Section 3: Position thy self
`hacker@paths~position-thy-self:~$ /challenge/run` 
<br/>
`hacker@paths~position-thy-self:~$ cd /var/log`
<br/>
`hacker@paths~position-thy-self:/var/log$ /challenge/run`
<br/>
Executing /challenge/run gave me the directory to cd into '/var/log'. Executing /challenge/run once again to get the flag.
Learned how to cd into a directory.
## Section 4: Position elsewhere
`hacker@paths~position-elsewhere:~$ /challenge/run`
<br/>
`hacker@paths~position-elsewhere:~$ cd /usr/share/doc`
<br/>
`hacker@paths~position-elsewhere:/usr/share/doc$ /challenge/run`
<br/>
Executing /challenge/run gave me the directory to cd into '/usr/share/doc'. Executing /challenge/run once again to get the flag.
Learned how to cd into a directory.
## Section 5: Position yet elsewhere
`hacker@paths~position-yet-elsewhere:~$ /challenge/run` - You are not currently in the /usr/aarch64-linux-gnu/include/gnu directory.
<br/>
`hacker@paths~position-yet-elsewhere:~$ cd /usr/aarch64-linux-gnu/include/gnu`
<br/>
`hacker@paths~position-yet-elsewhere:/usr/aarch64-linux-gnu/include/gnu$ /challenge/run`
<br/>
Thus challenge/run is as absolute path invoked from the right directory. Executing /challenge/run gave me the directory to cd into '/usr/share/doc'. Executing /challenge/run once again to get the flag.
Learned how to cd into a directory.
## Section 6: Implicit relative paths, from/
`hacker@paths~implicit-relative-paths-from-:~$ cd /`
<br/>
`hacker@paths~implicit-relative-paths-from-:/$ challenge/run`
<br/>
We have to specify a particular file, depending on where the terminal prompt is located. A relative path is any path that does not start at root and cwd is the directory that the prompt is currently located at.
I first cd into the directiry / and then used a relative path not starting from / to invoke the challenge.
## Section 7: Explcit relative paths, from/
`hacker@paths~explicit-relative-paths-from-:~$ cd /`
<br/>
`hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run`
<br/>
Every directory has two implicit entries '.' and '..'. '.' refers to the same directory.
## Section 8: Implicit relative path
`hacker@paths~implicit-relative-path:~$ cd /challenge`
<br/>
`hacker@paths~implicit-relative-path:/challenge$ ./run`
<br/>
Linux explicitly avoids automatically looking in the current directory when provided with a "naked" path. This is a preventive measure to accidnetly exceute programs which has the same name.
## Section 8: Home sweet home
