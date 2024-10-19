## Section 1: Chaining With Semicolons
`hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn; /challenge/college`
```
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{40iyt92mmsE1eYerFI3vPSZA3Kl.dVTN4QDL4EDO0czW}
```
## Section 2: Your First Shell Script
`hacker@chaining~your-first-shell-script:~$ touch script3.sh`
<br/>
`hacker@chaining~your-first-shell-script:~$ vi script3.sh`
<br/>
`hacker@chaining~your-first-shell-script:~$ bash script3.sh`
```
Great job, you've written your first shell script! Here is the flag:
pwn.college{ERsrvqeMJC4ti-JzWU8CbjIMFxq.dFzN4QDL4EDO0czW}
```
## Section 3: Redirecting Script Output
`hacker@chaining~redirecting-script-output:~$ touch script4.sh`
<br/>
`hacker@chaining~redirecting-script-output:~$ vi script4.sh`
<br/>
`hacker@chaining~redirecting-script-output:~$ bash script4.sh | /challenge/solve`
```
Correct! Here is your flag:
pwn.college{Y8216zJiMmNj_VMn5OMxeD-Cr0p.dhTM5QDL4EDO0czW}
```
## Section 4: Executable Shell Scripts
`hacker@chaining~executable-shell-scripts:~$ touch script5.sh`
<br/>
`hacker@chaining~executable-shell-scripts:~$ vi script5.sh`
<br/>
`hacker@chaining~executable-shell-scripts:~$ chmod a+rwx script5.sh`
<br/>
`hacker@chaining~executable-shell-scripts:~$ ./script5.sh`
```
Congratulations on your shell script execution! Your flag:
pwn.college{4zW2XX0_ZGD5bOrlSSGa2MsQCVL.dRzNyUDL4EDO0czW}
```
