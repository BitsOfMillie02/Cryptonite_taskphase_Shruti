## Section 1: Learning from Documentation 
`hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag`
<br/>
To run the program passing an argument of '--giveflag' to /challenge/challenge
<br/>
## Section 2: Learning Complex Usage
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


