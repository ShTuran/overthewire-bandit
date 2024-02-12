# OverTheWire Bandit Challenges -> in progress...

This repository contains my solutions and write-ups for the OverTheWire Bandit challenges. 

To start playing the Bandit game, visit OverTheWire Bandit. You can connect to the Bandit server via SSH using the provided credentials.

# bash

*ssh bandit0@bandit.labs.overthewire.org -p 2220*

Replace bandit0 with the appropriate level number as you progress through the game.

# Spoiler alert

Write-up solutions are included, NOT flags!

## This repository is intended for educational purposes only. Do not use the solutions provided here to cheat or undermine the learning experience.
## Highly recommended use Google and understand what each command do!
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Level 0->1

You have to read the file named **readme** 

  `cat readme`

# Level 1->2

You have to read the file named **-** , use full path instead of just `cat -`.

  `cat ./-`   
  
  or 
  
  `cat < -`

# Level 2->3

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 3->4

Hidden directories will not show up with simple `ls`

after  `cd inhere`

use `ls -la` 

`l` - will give detailed info about each file/folder

`a` - will show the hidden files


# Level 4->5

File is only human-readable and there are a lot of files in the directory, so reading them one by one will not be efficient, 

instead we can use:

  `file` 

command to determine what kind of files are there:

Note that,  __ASCII__ or __Unicode__ probably will be our needed file.

and one more thing 

use:  

  `./-file*` 

this 

.  -> is our current directory

-file* -> will find the files start with word '-file'  and  '*' -> match zero or more of the preceding character

so, final command:

`file ./-file*`

or just use:

`file ./*`

which they both will return the same thing.
 

# Level 5->6

*Note that, your solution may differ.*

We will try to 'find' a file with specific attributes:

Did I just used the word 'find'...

So, `find` command will be useful.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Since we are searching for human-readable file using:

  `grep ASCII`

  grep will search for specific pattern defined by the user.

  `|` will take first command output and inputs to the second command.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In previous task, we got that '.' is our current directory:

`find .`

and we since we are searching for a file, so:

`find . -type f`

and file size:

`-size 1033c`

c is for the bytes

Side note: 

    b – for 512-byte blocks (this is the default if no suffix is used)
    
    c – for bytes
    
    w – for two-byte words
    
    k – for Kilobytes (units of 1024 bytes)
    
    M – for Megabytes (units of 1048576 bytes)
    
    G – for Gigabytes (units of 1073741824 bytes)

and the text mentioned that file is not executable, so:

`! -executable`

finally:

`grep ASCII | find . -type f -size 1033c ! -executable`



# Level 6->7

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 7->8

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 8->9

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 9->10

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 10->11

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 11->12

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 12->13

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 13->14

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 14->15

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 15->16

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 16->17

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 17->18

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 18->19

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 19->20

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 21->22

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 22->23

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 23->24

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 24->25

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 25->26

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 26->27

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 27->28

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 28->29

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 29->30

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 30->31

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 31->32

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 32->33

File named with spaces, oh jezz:

  `cat spaces\ in\ this\ filename`

  or 

  `cat 'spaces in this filename'`


# Level 33->34

# Congratulations on completing the Bandit challenges!  Well done! 🎉 


