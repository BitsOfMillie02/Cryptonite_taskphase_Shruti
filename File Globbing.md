## Section 1: Matching with *
`hacker@globbing~matching-with-:~$ cd /c*/`
<br/>
`hacker@globbing~matching-with-:/challenge$ ./run`
<br/>
* is a glob which is thought of as a wildcard and used to replace files which have similiar pattern. Except for / or a leading . character, the * matches any part of the filename.
  For this challenge I used c* to write files beginning with c.
  ## Section 2: Matching with a ?
`hacker@globbing~matching-with-:~$ cd /?ha??enge`
<br/>
? character in any argument will be treated as single-character wildcard. Similiar to * but the only diffrence is treated as a single character.
<br/>
`hacker@globbing~matching-with-:/challenge$ ./run`
<br/>
I used the glob to write out challenge without using the letters c and l.
<br/>
## Section 3: Matching with []
`hacker@globbing~matching-with-:~$ cd /challenge/files`
<br/>
Similiar to * and ? [] is used to match with a set of characters enclosed within the square brackets.
<br/>
`hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[absh]`
<br/>
In this challenge, I accessed the file using the character b,a,s,h.
<br/>
## Section 4:Matching paths with []
`hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]`
<br/>
I globbed using the path as globbing occurs through path.
<br/>
## Section 5: Mixing Globs
## Section 6: Exclusionary Globbing
`hacker@globbing~exclusionary-globbing:~$ cd /challenge/files`
<br/>
`hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]*`
<br/>
To list the files not matched with the characters enclosed in [] brackets, we write the first character as a ! or a ^. Thus in this challenge, it will print out the files which dont start with p,w,n
<br/>
