
## Table of Contents
  1. [Bash Basics](#1-bash-basics)
    1.1. [File Commands](#11-file-commands)
    1.2. [Directory Commands](#12-directory-commands)
    1.3. [SSH, System Info & Network Commands](#13-ssh-system-info--network-commands)
  1. [Basic Shell Programming](#2-basic-shell-programming)
    2.1. [Variables](#21-variables)
    2.3. [String Substitution](#22-string-substitution)
    2.4. [Functions](#23-functions)
    2.5. [Conditionals](#24-conditionals)
    2.6. [Loops](#25-loops)
  1. [Process Handling](#3-process-handling)
  1. [Tricks](#4-tricks)
  1. [Debugging](#5-debugging)

This is first line that you will in bash script files called `shebang`. The shebang line in any script determines the script's ability to be executed like an standalone executable without typing sh, bash, python, php etc beforehand in the terminal.

```
#!/bin/bash
```

# 1. Bash Basics

### a. `export`
Displays all environment variables and if you want to get detail of specific variable then use `echo $VARIABLE_NAME`  
Syntax:
```
export
```
Example:
```
$ export
SHELL=/bin/zsh
AWS_HOME=/Users/adnanadnan/.aws
LANG=en_US.UTF-8
LC_CTYPE=en_US.UTF-8
LESS=-R

$ echo $SHELL
/usr/bin/zsh
```

### b. `whereis`
Finds out where a specific binary is on your system.  
Syntax:
```
whereis `name`
```
Example:
```
$ whereis php
/usr/bin/php
```

### c. clear
Clears content on window

## 1.1. File Commands
<table>
   <tr>
      <td><a href="#a-ls">ls</a></td>
      <td><a href="#b-touch">touch</a></td>
      <td><a href="#c-cat">cat</a></td>
      <td><a href="#d-more">more</a></td>
      <td><a href="#e-head">head</a></td>
      <td><a href="#f-tail">tail</a></td>
      <td><a href="#g-mv">mv</a></td>
      <td><a href="#h-cp">cp</a></td>
      <td><a href="#i-rm">rm</a></td>
      <td><a href="#j-diff">diff</a></td>
   </tr>
   <tr>
      <td><a href="#k-wc">wc</a></td>
      <td><a href="#l-chmod">chmod</a></td>
      <td><a href="#m-gzip">gzip</a></td>
      <td><a href="#n-gunzip">gunzip</a></td>
      <td><a href="#o-gzcat">gzcat</a></td>
      <td><a href="#p-lpr">lpr</a></td>
      <td><a href="#q-lpq">lpq</a></td>
      <td><a href="#r-lprm">lprm</a></td>
      <td><a href="#s-grep">grep</a></td>
   </tr>
</table>

### a. `ls`
Lists your files. It has a lot of options like `-l` lists files in 'long format', which contains the exact size of the file, who owns the file and who has the right to look at it, and when it was last modified. `-a` lists all files, including hidden files. For more information on this command check this [link](https://ss64.com/bash/ls.html)  
Syntax:
```
ls `option`
```
Example:
<pre>
$ ls -al
rwxr-xr-x   33 adnan  staff    1122 Mar 27 18:44 .
drwxrwxrwx  60 adnan  staff    2040 Mar 21 15:06 ..
-rw-r--r--@  1 adnan  staff   14340 Mar 23 15:05 .DS_Store
-rw-r--r--   1 adnan  staff     157 Mar 25 18:08 .bumpversion.cfg
-rw-r--r--   1 adnan  staff    6515 Mar 25 18:08 .config.ini
-rw-r--r--   1 adnan  staff    5805 Mar 27 18:44 .config.override.ini
drwxr-xr-x  17 adnan  staff     578 Mar 27 23:36 .git
-rwxr-xr-x   1 adnan  staff    2702 Mar 25 18:08 .gitignore
</pre>

### b. `touch`
Creates or updates your file  
Syntax:
```
touch `filename`
```
Example:
```
$ touch trick.md
```

### c. `cat`
Places standard input into file. Means that it opens the file in terminal for you to edit  
Syntax:
```
cat > `filename`
```

### d. `more`
Shows the first part of a file (move with space and type q to quit)  
Syntax:
```
more `filename`
```

### e. `head`
Outputs the first 10 lines of file  
Syntax:
```
head `filename`
```

### f. `tail`
Outputs the last 10 lines of file. Use `-f` to output appended data as the file grows  
Syntax:
```
tail `filename`
```


### g. `mv`
Moves a file from one location to other  
Syntax:
```
mv `filename1` `filename2`
```
Where `filename1` is the source path to the file and `filename2` is the destination path to the file.

### h. `cp`
Copies a file from one location to other  
Syntax:
```
cp `filename1` `filename2`
```
Where `filename1` is the source path to the file and `filename2` is the destination path to the file.

### i. `rm`
Removes a file. But if you will apply this command on a directory directory, it will gives you an error
`rm: directory: is a directory`
So in order to remove directory you have to pass `-rf` to remove all the content of the directory recursively  
Syntax:
```
rm `filename`
```

### j. `diff`
Compares files, and shows where they differ  
Syntax:
```
diff `filename1` `filename2`
```

### k. `wc`
Tells you how many lines, words and characters there are in a file  
Syntax:
```
wc `filename`
```
Example:
```
$ wc demo.txt
7459   15915  398400 demo.txt
```
Where `7459` is lines, `15915` is words and `398400` is characters.

### l. `chmod`
Lets you change the read, write, and execute permissions on your files  
Syntax:
```
chmod -options `filename`
```

### m. `gzip`
Compresses files  
Syntax:
```
gzip `filename`
```

### n. `gunzip`
Un-compresses files compressed by gzip  
Syntax:
```
gunzip `filename`
```

### o. `gzcat`
Lets you look at gzipped file without actually having to gunzip it  
Syntax:
```
gzcat `filename`
```

### p. `lpr`
Print the file  
Syntax:
```
lpr `filename`
```

### q. `lpq`
Check out the printer queue  
Syntax:
```
lpq
```
Example:
```
$ lpq
Rank    Owner   Job     File(s)                         Total Size
active  adnanad 59      demo                            399360 bytes
1st     adnanad 60      (stdin)                         0 bytes
```

### r. `lprm`
Remove something from the printer queue  
Syntax:
```
lprm `jobnumber`
```

### s. `grep`
Looks for text inside files. You can use grep to search for lines of text that match one or many regular expressions, and outputs only the matching lines.  
Syntax:
```
grep `pattern` `filename`
```
Example:
```
$ grep admin /etc/passwd
_kadmin_admin:*:218:-2:Kerberos Admin Service:/var/empty:/usr/bin/false
_kadmin_changepw:*:219:-2:Kerberos Change Password Service:/var/empty:/usr/bin/false
_krb_kadmin:*:231:-2:Open Directory Kerberos Admin Service:/var/empty:/usr/bin/false
```
You can also force grep to ignore word case by using `-i` option. Also `-r` can be used to search all files under the specified directory like
```
$ grep -r admin /etc/
```
And `-w` to search for words only.

## 1.2. Directory Commands

<table>
   <tr>
      <td><a href="#a-mkdir">mkdir</a></td>
      <td><a href="#b-cd">cd</a></td>
      <td><a href="#c-pwd">pwd</a></td>
   </tr>
</table>

### a. `mkdir`
Makes a new directory  
Syntax:
```
mkdir `dirname`
```

### b. `cd`
Moves you from one directory to other. If you just run  
```
$ cd
```
Then it will moves you to home. Also this command accepts an optional `dirname`, which if provided will moves you to that directory.
```
cd `dirname`
```

### c. `pwd`
Tells you in which directory you currently are  
Syntax:
```
pwd
```

## 1.3. SSH, System Info & Network Commands

<table>
   <tr>
      <td><a href="#a-mkdir">ssh</a></td>
      <td><a href="#b-cd">whoami</a></td>
      <td><a href="#c-pwd">passwd</a></td>
      <td><a href="#d-quota">quota</a></td>
      <td><a href="#e-date">date</a></td>
      <td><a href="#f-cal">cal</a></td>
      <td><a href="#g-uptime">uptime</a></td>
      <td><a href="#h-w">w</a></td>
      <td><a href="#i-finger">finger</a></td>
      <td><a href="#j-uname">uname</a></td>
   </tr>
   <tr>
      <td><a href="#k-man">man</a></td>
      <td><a href="#l-df">df</a></td>
      <td><a href="#m-du">du</a></td>
      <td><a href="#n-last">last</a></td>
      <td><a href="#o-ps">ps</a></td>
      <td><a href="#p-kill">kill</a></td>
      <td><a href="#q-killall">killall</a></td>
      <td><a href="#r-top">top</a></td>
      <td><a href="#s-bg">bg</a></td>
      <td><a href="#t-fg">fg</a></td>
   </tr>
   <tr>
      <td><a href="#u-ping">ping</a></td>
      <td><a href="#v-whois">whois</a></td>
      <td><a href="#w-dig">dig</a></td>
      <td><a href="#x-wget">wget</a></td>
   </tr>
</table>

### a. `ssh`
ssh (SSH client) is a program for logging into a remote machine and for executing commands on a remote machine.  
Syntax:
```
ssh user@host
```
This command also accepts an option `-p` that can to used to connect to specific port.  
Syntax:
```
ssh -p `port` user@host
```

### b. `whoami`
Return current logged in username

### c. `passwd`
Allows the current logged user to change his password

### d. `quota`
Shows what your disk quota is
Syntax:
```
quota -v
```

### e. `date`
Shows the current date and time

### f. `cal`
Shows the month's calendar

### g. `uptime`
Shows current uptime

### h. `w`
Displays who is online

### i. `finger`
Displays information about user  
Syntax:
```
finger `username`
```

### j. `uname`
Shows kernel information  
Syntax:
```
uname -a
```

### k. `man`
Shows the manual for specified command  
Syntax:
```
man `command`
```

### l. `df`
Shows disk usage

### m. `du`
Shows the disk usage of the files and directories in filename (du -s give only a total)  
Syntax:
```
du `filename`
```

### n. `last`
Lists your last logins of specified user  
Syntax:
```
last `yourUsername`
```

### o. `ps`
Lists your processes  
Syntax:
```
ps -u `yourusername`
```

### p. `kill`
Kills (ends) the processes with the ID you gave  
Syntax:
```
kill `PID`
```

### q. `killall`
Kill all processes with the name  
Syntax:
```
killall `processname`
```

### r. `top`
Displays your currently active processes

### s. `bg`
Lists stopped or background jobs ; resume a stopped job in the background

### t. `fg`
Brings the most recent job in the foreground.

### u. `ping`
Pings host and outputs results  
Syntax:
```
ping `host`
```

### v. `whois`
Gets whois information for domain  
Syntax:
```
whois `domain`
```

### w. `dig`
Gets DNS information for domain  
Syntax:
```
dig `domain`
```

### x. `wget`
Downloads file  
Syntax:
```
wget `file`
```


# 2. Basic Shell Programming

Now lets discuss about some basic of shell programming. Lets start with creating variables first.

## 2.1. Variables

Creating variable in bash is similar to other language. There are no data types. A variable in bash can contain a number, a character, a string of characters. You have no need to declare a variable, just assigning a value to its reference will create it.

Example:
```
str="hello world"
```

The above line creates a variable `str` and assigns "hello world" to it. Then the value of variable is retrieved by putting the `$` in the beginning of variable name.

Example:
```
echo $str   # hello world
```

Also like other languages bash has also arrays. An array is variable containing multiple values. There's no maximum limit on the size of array. Array in bash are zero based. The first element is indexed with element 0. There are several ways for creating arrays in bash. Which are given below.

Examples:
```
array[0] = val
array[1] = val
array[2] = val
array=([2]=val [0]=val [1]=val)
array(val val val)
```
To display a value at specific index use following syntax

```
${array[i]}     # where i is the index
```

One thing to note that if no index is supplied, array element 0 is assumed. To find out how many values there are in the array check following syntax

```
${#array[@]}
```

Bash has also support for the ternary conditions. Check some examples below.

```
${varname:-word}    # if varname exists and isn't null, return its value; otherwise return word
${varname:=word}    # if varname exists and isn't null, return its value; otherwise set it word and then return its value
${varname:+word}    # if varname exists and isn't null, return word; otherwise return null
${varname:offset:length}    # performs substring expansion. It returns the substring of $varname starting at offset and up to length characters
```

## 2.2 String Substitution

Check some of the syntax on how to manipulate strings

```
${variable#pattern}         # if the pattern matches the beginning of the variable's value, delete the shortest part that matches and return the rest
${variable##pattern}        # if the pattern matches the beginning of the variable's value, delete the longest part that matches and return the rest
${variable%pattern}         # if the pattern matches the end of the variable's value, delete the shortest part that matches and return the rest
${variable%%pattern}        # if the pattern matches the end of the variable's value, delete the longest part that matches and return the rest
${variable/pattern/string}  # the longest match to pattern in variable is replaced by string. Only the first match is replaced
${variable//pattern/string} # the longest match to pattern in variable is replaced by string. All matches are replaced
${#varname}     # returns the length of the value of the variable as a character string
```

## 2.3. Functions
As in almost any programming language, you can use functions to group pieces of code in a more logical way or practice the divine art of recursion. Declaring a function is just a matter of writing function my_func { my_code }. Calling a function is just like calling another program, you just write its name.

Syntax:
```
functname() {
    shell commands
}
```

Example:
```
#!/bin/bash
function hello {
   echo world!
}
hello

function say {
    echo $1
}
say "hello world!"
```

When you will run above example the `hello` function will output "world!". The above two functions `hello` and `say` are identical. The main difference is function `say`. This function, prints the first argument it receives. Arguments, within funtions, are treated in the same manner as arguments given to the script.

## 2.4. Conditionals

The conditional statement in bash is similar to other programming languages. Conditions have many form like the most basic form is `if` expression `then` statement where statement is only executed if expression is true.

Syntax:
```
if [expression]; then
    will execute only if expression is true
else
    will execute if expression is false
fi
```

Sometime if conditions becoming confusing so you can write the same condition using the `case statements`.

Syntax:
```
case expression in
    pattern1 )
        statements ;;
    pattern2 )
        statements ;;
    ...
esac
```

Expression Examples:

```
statement1 && statement2  # both statements are true
statement1 || statement2  # one of the statement is true

str1=str2       # str1 matches str2
str1!=str2      # str1 does not match str2
str1<str2       # str1 is less than str2
str1>str2       # str1 is greater than str2
-n str1         # str1 is not null (has length greater than 0)
-z str1         # str1 is null (has length 0)

-a file         # file exists
-d file         # file exists and is a directory
-e file         # file exists; same -a
-f file         # file exists and is a regular file (i.e., not a directory or other special type of file)
-r file         # you have read permission
-r file         # file exists and is not empty
-w file         # your have write permission
-x file         # you have execute permission on file, or directory search permission if it is a directory
-N file         # file was modified since it was last read
-O file         # you own file
-G file         # file's group ID matches yours (or one of yours, if you are in multiple groups)

file1 -nt file2     # file1 is newer than file2
file1 -ot file2     # file1 is older than file2

-lt     # less than
-le     # less than or equal
-eq     # equal
-ge     # greater than or equal
-gt     # greater than
-ne     # not equal
```

## 2.5. Loops

There are three types of loops in bash. `for`, `while` and `until`.

Different `for` Syntax:
```
for x := 1 to 10 do
begin
  statements
end

for name [in list]
do
  statements that can use $name
done

for (( initialisation ; ending condition ; update ))
do
  statements...
done
```

`while` Syntax:
```
while condition; do
  statements
done
```

`until` Syntax:
```
until condition; do
  statements
done
```

# 3. Process Handling

myCommand &  # runs job in the background and prompts back the shell

jobs         # lists all jobs (use with -l to see associated PID)

kill -l      # returns a list of all signals on the system, by name and number
kill PID     # terminates process with specified PID

ps           # prints a line of information about the current running login shell and any processes running under it
ps -a        # selects all processes with a tty except session leaders

# 4. Tricks

## set an alias
Open `bash_profile` by running following command `nano ~/.bash_profile`
> alias dockerlogin='ssh www-data@adnan.local -p2222'  # add your alias in .bash_profile

## to quickly go to a specific directory
nano ~/.bashrc
> export hotellogs="/workspace/hotel-api/storage/logs"

source ~/.bashrc
cd hotellogs


# 5. Debugging
You can easily debug the bash script by passing different options to `bash` command. For example `-n` will not run commands and check for syntax errors only. `-v` echo commands before running them. `-x` echo commands after command-line processing.

Syntax:
```
bash -n scriptname
bash -v scriptname
bash -x scriptname
```
# Feedback
Suggestions/improvements
[welcome](https://github.com/idnan/lord-of-terminal/issues)!
