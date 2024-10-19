## Section 1: Listing Processes
`hacker@processes~listing-processes:~$ ps -ef`
```
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 12:45 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/default/bin/dojo-init /ru
root           7       1  0 12:45 ?        00:00:00 /run/dojo/bin/sleep 6h
root          68       1  0 12:45 ?        00:00:00 /challenge/18496-run-2577
root          72      68  0 12:45 ?        00:00:00 sleep 6h
hacker        73       0  0 12:45 pts/0    00:00:00 /run/dojo/bin/ssh-entrypoint
hacker        90      73  0 12:46 pts/0    00:00:00 ps -ef
```
`hacker@processes~listing-processes:~$ /challenge/18496-run-2577`
```
Yahaha, you found me! Here is your flag:
pwn.college{4_FSwW13rcgIgbTke_5Ts2edko7.dhzM4QDL4EDO0czW}
Now I will sleep for a while (so that you could find me with 'ps').
```
ps stands for "process snapshot" or "process status" and it lists the processes running in terminal. Each process has a number that uniquely identifies every running process in a Linux environment known as the numerical identifier (the Process ID, or PID).
<br/>
Standard Syntax: -e to list every process and -f for full format output, including arguments which can be combined into a single argument -ef.
<br/>
BSD Syntax:  a to list processes for all users, x to list processes that aren't running in the terminal, and u for a "user-readable" output which can be combined into a single argument aux.
<br/>
## Section 2: Killing Processes
`hacker@processes~killing-processes:~$ ps -ef`
```
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 12:48 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/default/bin/dojo-init /ru
root           7       1  0 12:48 ?        00:00:00 /run/dojo/bin/sleep 6h
root          71       1  0 12:48 ?        00:00:00 su -c /challenge/.launcher hacker
hacker        73      71  0 12:48 ?        00:00:00 /challenge/dont_run
hacker        74      73  0 12:48 ?        00:00:00 sleep 6h
hacker        75       0  0 12:48 pts/0    00:00:00 /run/dojo/bin/ssh-entrypoint
hacker        92      75  0 12:48 pts/0    00:00:00 ps -ef
```
`hacker@processes~killing-processes:~$ kill 73`
<br/>
`hacker@processes~killing-processes:~$ /challenge/run`
```
Great job! Here is your payment:
pwn.college{w-G_yTHW_bfytdx97Ch6jopVC9y.dJDN4QDL4EDO0czW}
```
To terminate processes we use the kill command in such a way that gives it a chance to get its affairs in order before ceasing to exist. In this challenge, I first terminated the the first process and then ran it. I used the kill command to terminate the dont_run process.
<br/>
## Section 3: Interrupting Processes
`hacker@processes~interrupting-processes:~$ /challenge/run`
```
I could give you the flag... but I won't, until this process exits. Remember,
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{I95GflmYMx-xo3tCqfkDB3Yq4Pi.dNDN4QDL4EDO0czW}
```
Ctrl-C sends an "interrupt" instruction to the application which is waiting on input from the terminal and causes the application to exit or interrupt. In this challenge, I used Ctrl-C to interrupt the process to get the command.
<br/>
## Section 4: Suspending Processes
`hacker@processes~suspending-processes:~$ /challenge/run`
```
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root          82      65  0 12:51 pts/0    00:00:00 bash /challenge/run
root          84      82  0 12:51 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can
background me with Ctrl-Z or, if you're not ready to do that for whatever
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
```
`hacker@processes~suspending-processes:~$ /challenge/run`
```
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root          82      65  0 12:51 pts/0    00:00:00 bash /challenge/run
root          89      65  0 12:52 pts/0    00:00:00 bash /challenge/run
root          91      89  0 12:52 pts/0    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{YJjvLaDSC8Shc1wBtk1gQyU2swf.dVDN4QDL4EDO0czW}
```
Ctrl-Z is used to suspend processes to the background. In this challenge, I launched another copy of run on itself on the same terminal by first launching it, suspending it using Ctrl-Z and then launching it again to get the flag.
<br/>
## Section 5: Resuming Processes
`hacker@processes~resuming-processes:~$ /challenge/run`
```
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
```
`hacker@processes~resuming-processes:~$ fg`
```
/challenge/run
I'm back! Here's your flag:
pwn.college{UMOx4QJbiwJ1JF5_HMdNf2pzVS2.dZDN4QDL4EDO0czW}
```
The fg command is a builtin command that resumes the suspended process and puts it back in the foreground of the terminal. In this challenge, I first suspended the process and then resumed it using the fg command.
<br/>
## Section 6: Backgrounding Processes
`hacker@processes~backgrounding-processes:~$ /challenge/run`
```
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root          82 S+   bash /challenge/run
root          84 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the
background, and then launch a new version of me! You can background me with
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
```
`hacker@processes~backgrounding-processes:~$ /challenge/run`
```
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root          82 T    bash /challenge/run
root          89 S+   bash /challenge/run
root          91 R+   ps -o user=UID,pid,stat,cmd

I found a second version of me, but it's suspended! Please resume it in the
background with the 'bg' command, then run me again.
hacker@processes~backgrounding-processes:~$ bg
[1]+ /challenge/run &



Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out.
```
`hacker@processes~backgrounding-processes:~$ /challenge/run`
```
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root          82 S    bash /challenge/run
root         103 S    sleep 6h
root         104 S+   bash /challenge/run
root         106 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{oR9m8BGOqKOPRdnDoaX52RtKtUR.ddDN4QDL4EDO0czW}
```
## Section 7: Foregrounding Processes
`hacker@processes~foregrounding-processes:~$ /challenge/run`
```
To pass this level, you need to suspend me, resume the suspended process in the
background, and *then* foreground it without re-suspending it! You can
background me with Ctrl-Z (and resume me in the background with 'bg') or, if
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
```
`hacker@processes~foregrounding-processes:~$ bg /challenge/run`
```
[1]+ /challenge/run &



Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out. After that, resume me into the foreground with 'fg';
I'll wait.
```
`hacker@processes~foregrounding-processes:~$ fg /challenge/run`
```
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{0b5cKyMLmtHavH3M0lhuVm9h_m7.dhDN4QDL4EDO0czW}
```
## Section 8: Starting Backgrounded Processes
`hacker@processes~starting-backgrounded-processes:~$ /challenge/run &`
```
[1] 85



hacker@processes~starting-backgrounded-processes:~$ Yay, you started me in the background! Because of that, this text will probably
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{4kPFKsoL_bQf-OOcd8Hsvy730C1.dlDN4QDL4EDO0czW}
```
To directly start the backgrounding we can append an & to the command.
<br/>
## Section 9: Process Exit Codes
`hacker@processes~process-exit-codes:~$ /challenge/get-code`
```
Exiting with an error code!
```
`hacker@processes~process-exit-codes:~$ echo $?`
```
19
```
`hacker@processes~process-exit-codes:~$ /challenge/submit-code 19`
```
CORRECT! Here is your flag:
pwn.college{capuSrpozYnNv0-bj4l7r0x4zmG.dljN4UDL4EDO0czW}
```
Every shell command like programs each exit with an exit code when they finish running or terminate which is used to check if the process succeeded in its functionality. A ? variable is used to access the exit code of the most recently termianted command. Commands that succeed return 0 and commands that fail return a non-zero value most commonly 1.
<br/>




