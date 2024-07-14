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

And then show the content of file with `cat 'filename  '`


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

  Since we are searching for human-readable file using:

  `grep ASCII`

  grep will search for specific pattern defined by the user.

  `|` will take first command output and inputs to the second command.



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

To decode the data which encoded with base64

`base64 -d data.txt`

# Level 11->12

Here you can use CyberChef to decode the ROT13

But if you prefer to use CLI:

`cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'`

The tr command in Unix-based systems is used for translating or deleting characters. 

`tr 'SET1' 'SET2'`

    SET1 is the list of characters to be replaced.
    SET2 is the list of characters to replace them with.


# Level 12->13

create a directory under /tmp and then copy the 'data.txt' file here

`xxd` - make a hex dump or do the reverse.

`xxd -r data.txt > data1.txt`

And when we view the file it is a - gzip compressed data

change the extension of 'data.txt' to 'data.gz'

`gzip -d data.gz`

And when we view the file it is a - bzip compressed data

change the extension of 'data.txt' to 'data.bz2'

`bzip2 -d data.gz`

 after that file will be in --- data: POSIX tar archive (GNU)

 change the extension to '.tar'

 then 

 `tar -xf data.tar`

 IT WILL REPEATED PROCESS which mentioned above

 You just need to adjust the extension and tren decompress several times.


# Level 13->14

If we want to login via the key, will use -i flag. 
(Type this command inside the level13)

`ssh -i sshkey.private bandit14@localhost -p 2220`

'sshkey.private' a file was given us!

# Level 14->15

Here we can use various commands but I think `nc` is the nicest choice

`nc localhost 30000`

after that copy the password which we got in the previous level in directory of   `/etc/bandit_pass/bandit14`

# Level 15->16

`ncat --ssl localhost 30001` after that command we need to paste the password of level 15.

# Level 16->17

First let's use `nmap` to listen ports between [31000-32000]

`nmap -p 31000-32000 --script=ssl-cert localhost`

once we found out what port number is using ssl

`ncat --ssl locahost [port-number]`

paste your previous answer in here..

then you will get the key 

after copying the file -  give it appropriate [400] permissions to work.

which, if you use `-i` while connecting ssh it will pass you next level 


# Level 17->18

`diff passwords.old passwords.new`

but we will not be able to get in.

Go to the next level and read it!

# Level 18->19

It is related with : Level 17->18

`ssh -t  bandit18@bandit.labs.overthewire.org -p 2220 /bin/sh`

ssh -t: This initiates an SSH connection. The -t option forces pseudo-terminal allocation, which can be useful if you need to run an interactive command on the remote server.

/bin/sh: This specifies the command to run on the remote server after the connection is established. /bin/sh is the command for a basic shell, which will allow you to interact with the server’s command line.

and then paste the previous password; you will get a shell

read the `readme` file which contains password for the level 19.


# Level 19->20

If you execute the file without any argument, it shows how to use it.
And, if you type any command after the executable, it will run it as owner of it

`./bandit20 cat /etc/bandit_pass/bandit20`


# Level 20->21

Here, we need to open 2 session on the same level.

In one terminal type `cat /etc/bandit_pass/bandit20 | nc -l localhost 7777` -> in this terminal you will get the password.

In another terminal type `./suconnect 7777`


# Level 21->22

This was relatively simple, you just need go to the necessary directory and see the inside of cron jobs.


# Level 22->23 SPOILER:FLAG DEMONSTRATED!

![WhatsApp Image 2024-07-14 at 20 30 53](https://github.com/user-attachments/assets/d680fd6c-e4d4-41b8-84f2-7cafc494e8a0)


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
