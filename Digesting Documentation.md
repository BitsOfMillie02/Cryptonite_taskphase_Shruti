## Section 1: Learning from Documentation 
`hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag`
<br/>
To run the program passing an argument of '--giveflag' to /challenge/challenge
<br/>
## Section 2: Learning Complex Usage
`hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag`
```
Correct argument! Here is the /flag file:
pwn.college{UUKxkSf34_lfLHDFJANrgVuzvSD.dVjM5QDL4EDO0czW}
```
In this challenge the argument --printfile is to be provided to the path of the flag.
<br/>
## Section 3: Reading Manuals
`hacker@man~reading-manuals:~$ man challenge`
<br/>

```
CHALLENGE(1)                                      Challenge Commands                                     CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --gfkjnf NUM
              print the flag if NUM is 587

AUTHOR
       Written by Zardus.

REPORTING BUGS
       The repository for this dojo: <https://github.com/pwncollege/linux-luminarium/>

SEE ALSO
       man(1) bash-builtins(7)
```
       
`hacker@man~reading-manuals:~$ /challenge/challenge --gfkjnf 587`
<br/>
man command stands for manula which will print the manual of the argument passed to it.

## Section 4: Searching Manuals
`hacker@man~searching-manuals:~$ man challenge`
 <br/> 
`hacker@man~searching-manuals:~$ /challenge/challenge --pefl`
 <br/> 
/ is used to search for manuals. n to go the next result while N to go to the previous result. Also ? is used to search backwards.
## Section 5: Searching For Manuals
`hacker@man~searching-for-manuals:~$ man man`
 <br/> 
which gives the output 
```
MAN(1)                                        Manual pager utils                                       MAN(1)

NAME
       man - an interface to the system reference manuals

SYNOPSIS
       man [man options] [[section] page ...] ...
       man -k [apropos options] regexp ...
       man -K [man options] [section] term ...
       man -f [whatis options] page ...
       man -l [man options] file ...
       man -w|-W [man options] page ...

DESCRIPTION
       man  is the system's manual pager.  Each page argument given to man is normally the name of a program,
       utility or function.  The manual page associated with each of these arguments is then found  and  dis‐
       played.   A section, if provided, will direct man to look only in that section of the manual.  The de‐
       fault action is to search in all of the available sections following  a  pre-defined  order  (see  DE‐
       FAULTS), and to show only the first page found, even if page exists in several sections.

       The table below shows the section numbers of the manual followed by the types of pages they contain.

       1   Executable programs or shell commands
       2   System calls (functions provided by the kernel)
       3   Library calls (functions within program libraries)
       4   Special files (usually found in /dev)
       5   File formats and conventions, e.g. /etc/passwd
hacker@man~searching-for-manuals:~$ man -k challenge
pyjbhpnxtr (1)       - print the flag!
```
`hacker@man~searching-for-manuals:~$ man pyjbhpnxtr`
```
CHALLENGE(1)                                  Challenge Commands                                 CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --pyjbhp NUM
              print the flag if NUM is 755

AUTHOR
       Written by Zardus.

REPORTING BUGS
       The repository for this dojo: <https://github.com/pwncollege/linux-luminarium/>
```
`hacker@man~searching-for-manuals:~$ /challenge/challenge --pyjbhp 755`
`Correct usage! Your flag: pwn.college{UIDXp-7yjO5bGV5hVMpnAxtr-qK.dZTM4QDL4EDO0czW}`
## Section 6: Helpful Programs
`cd challenge`
 <br/> 
`hacker@man~helpful-programs:/challenge$ ls`
 <br/> 
DESCRIPTION.md  challenge
 <br/> 
`hacker@man~helpful-programs:/challenge$ /challenge/challenge --help`
 <br/> 
```
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
hacker@man~helpful-programs:/challenge$ ./challenge -p
The secret value is: 627
```
 <br/> 
`hacker@man~helpful-programs:/challenge$ ./challenge -g 627`
 <br/> 
 
 ## Section 7:Help for Builtins
`hacker@man~help-for-builtins:~$ help challenge`
 <br/> 
```
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!

    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

You must be sure to provide the right value to --secret. That value
is "IZPy6n7n".
```
 <br/> 
`hacker@man~help-for-builtins:~$ challenge --secret IZPy6n7n`
 <br/> 
 Builtin are commands built in to the shell and are handled internally by the shell. Used help to find the secret value and then passing value as an argument.


