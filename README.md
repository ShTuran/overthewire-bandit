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

This was relatively simple, that's why here is direct command we have to use:

`find / -type f -user bandit7  -group bandit6 -size 33c`



# Level 7->8

I suggest to read about "grep" command which is helpful to search within the file.

`grep "millionth" data.txt`

# Level 8->9

`sort` command will give alphabeticly order
`uniq -c` command will show how many times they are repeated

`sort data.txt | uniq -c` 

# Level 9->10

`strings` - print the sequences of printable characters in files

`strings data.txt | grep "===="`

# Level 10->11




# Level 11->12



# Level 12->13



# Level 13->14




# Level 14->15




# Level 15->16



# Level 16->17




# Level 17->18



# Level 18->19




# Level 19->20




# Level 21->22




# Level 22->23




# Level 23->24




# Level 24->25




# Level 25->26




# Level 26->27



# Level 27->28




# Level 28->29




# Level 29->30



# Level 30->31



# Level 31->32


# Level 32->33



# Level 33->34
# Congratulations on completing the Bandit challenges!  Well done! 🎉 
