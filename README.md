# Unix Cheat Sheet

A collection of some of the most useful Git commands

## Table of Contents

1. [File System](#file-system)
    * [Listing Directories and Files](#listing-directories-and-files)
    * [Changing Working Directory](#changing-working-directory)
    * [Making Directories and Files](#making-directories-and-files)
    * [Removing Directories and Files](#removing-directories-and-files)
    * [Opening Directories and Files](#opening-directories-and-files)
    * [Copying Files](#copying-files)
    * [Moving Directories and Files](#moving-directories-and-files)
    * [Linking Files](#linking-files)
    * [Displaying the Contents of a File](#displaying-the-contents-of-a-file)
    * [Commands](#commands)
    * [Aliases](#aliases)
2. [Systen Info](#system-info)
3. [Process Management](#process-management)
4. [Permissions](#permissions)
    * [Changing Permissions](#changing-permissions)
    * [Making Executables](#making-executables)
5. [Networking](#networking)
    * [Sending Request](#sending-requests)
    * [Copying Remote Files](#copying-remote-files)
    * [SSH](#ssh)
    * [Processes](#processes)
6. [Text Processing](#text-processing)
7. [Searching](#searching)
8. [Compression](#compression)
9. [Shortcuts](#shortcuts)
10. [Redirections](#redirections)
11. [Others](#others)

## File System

### Listing Directories and Files

List items in current directory.

```bash
ls
```

List items in current directory in a single column.

```bash
ls -1
```

List items in current directory and show in long format to see perimissions, size, and modification date.

```bash
l
```

List items in current directory and show in long format to see perimissions, size, and modification date.

```bash
ls -l
```

List items in current directory and show in long format to see perimissions, human readable size, and modification date.

```bash
ls -lh
```

List all items in current directory, including hidden files.

```bash
ls -a
```

List directory entries instead of contents.

```bash
ls -d <directory>
```

List only hidden files.

```bash
ls -ld .??*
```

**-rw-r--r--@ the at symbol signifies that the file was downloaded from the internet, etc.**

### Changing Working Directory

Change current directory to directory.

```bash
cd <directory>
```

Change directory to home.

```bash
cd
```

Go up one directory.

```bash
cd ..
```

Go to the root directory.

```bash
cd /
```

Go to to your home directory.

```bash
cd ~
```

Go to the last directory you were just in.

```bash
cd -
```

### Making Directories

Make directory.

```bash
mkdir <directory>
```

Create or update file.

```bash
touch <file>
```

### Removing Directories and Files

Remove empty directory.

```bash
rmdir <directory>
```

Remove directory recursively.

```bash
rm -r <directory>
```

Ignore nonexistent files, never prompt.

```bash
rm -f <directory>
```

Remove file.

```bash
rm <file>
```

Prompt before every removal.

```bash
rm -i <file>
```

Remove files that match a pattern.

```bash
rm <pattern>
```

### Opening Directories and Files

Open current directory.

```bash
open .
```

Open files and directories.

```bash
open <path>
```

Specifies the application to use for opening the file.

```bash
open <file> -a <bin>
```

Causes the file to be opened with the default text editor, as determined via LaunchServices.

```bash
open -t <file>
```

### Copying Files

Copy file1 to file2.

```bash
cp <file1> <file2>
```

Copy directory dir1 to dir2 recursively.

```bash
cp -r <dir1> <dir2>
```

### Moving Directories and Files

Move (rename) path1 to path2.

```bash
mv <path1> <path2>
```

### Linking Files

Create hard link

```bash
ln <file> <link>
```

Create symbolic link.

```bash
ln -s <file> <link>
```

### Displaying the Contents of a File

Output the contents of file.

```bash
cat <file>
```

View file with page navigation.

```bash
less <file>
```

Output the first 10 lines of file.

```bash
head <file>
```

Output the first 3 lines of file.

```bash
head -3 <file>
```

Output the last 10 lines of file.

```bash
tail <file>
```

Output the last 3 lines of file.

```bash
tail -3 <file>
```

Output the contents of file as it grows, starting with the last 10 lines.

```bash
tail -f <file>
```

### Commands

Execute command for all directories or files in a given path.

```bash
find <path> -type <type> -exec chmod 644 {} \;
```

Execute command for all directories or files in a given path.

```bash
find <path> -type <type> -iname "*.csv" -exec cp {} ~/csv_files/ \;
```

Execute command for all directories or files in a given path.

```bash
find <path> -type <type> | xargs <bin>
```

Execute command for all directories or files in a given path and prints each command that will be executed.

```bash
find <path> -type <type> | xargs -t <bin>
```

Execute command for all directories or files in a given path and prints the command to be executed and prompts the user to run it.

```bash
find <path> -type <type> | xargs -p <bin>
```

Change permissions for all files, skipping dirs.

```bash
find . -type f | xargs chmod 664
```

Change permissions for all dirs, skipping files.

```bash
find . -type d | xargs chmod 755
```

Change permissions for all dirs with whitespaces, skipping files.

```bash
find . -type d -print0 | xargs -0 chmod 755
```

Find directories with permissions other than 664.

```bash
find -type f -not -perm 664
```

Find directories with permissions other than 755.

```bash
find -type d -not -perm 755
```

### Aliases

Create an alias for a command.

```bash
alias <name>="<command>"
```

## System Info

Show system’s host name.

```bash
hostname
```

Shut down machine.

```bash
shutdown
```

Restart machine.

```bash
reboot
```

Show the current date and time.

```bash
date
```

Display how long the system has been running.

```bash
uptime
```

Display how long the system has been running.

```bash
w
```

Who you are logged in as.

```bash
whoami
```

Show the manual for bin.

```bash
man <bin>
```

Show free disk space.

```bash
df
```

Show directory space usage.

```bash
du <file>
```

Show directory space usage with human readable size.

```bash
du -h <file>
```

Count number of lines/words/characters in file.

```bash
wc <file>
```

Count number of bytes in file.

```bash
wc -c <file>
```

Count number of lines in file.

```bash
wc -l <file>
```

Count number of characters in file.

```bash
wc -m <file>
```

Count number of words in file.

```bash
wc -w <file>
```

Show possible locations of bin.

```bash
whereis <bin>
```

Where the bin is located.

```bash
which <bin>
```

Print symlink free path as well.

```bash
which -s <bin>
```

Show this month's calendar.

```bash
cal
```

Show this years's calendar.

```bash
cal <year>
```

## Process Management

Display all currently active processes.

```bash
ps
```

Display all running processes.

```bash
top
```

Sort processes by primary sort key in descending order.

```bash
top -o <key>
```

Sort processes by cpu in descending order.

```bash
top -u
```

Kill process id pid.

```bash
kill <pid>
```

Force kill process id pid.

```bash
kill -9 <pid>
```

kill all processes by name.

```bash
killall <name>
```

Kills process by port number.

```bash
lsof -P | grep ':<port>' | awk '{print $2}' | xargs kill -9
```

## Permissions

### Changing Permissions

Change permissions of file to ugo - u is the user's permissions, g is the group's permissions, and o is everyone else's permissions. The values of u, g, and o can be any number between 0 and 7.

* 7 — full permissions
* 6 — read and write only
* 5 — read and execute only
* 4 — read only
* 3 — write and execute only
* 2 — write only
* 1 — execute only
* 0 — no permissions

```bash
chmod <ugo> <path>
```

User can read and write - good for files.

```bash
chmod 600 <path>
```

User can read, write, and execute - good for scripts.

```bash
chmod 700 <path>
```

User can read and write, and everyone else can only read - good for web pages.

```bash
chmod 644 <path>
```

User can read, write, and execute, and everyone else can read and execute - good for programs that you want to share.

```bash
chmod 755 <path>
```

Change owner and group-related information for a file or directory.

```bash
chown <user> <path>
```

### Making Executables

Add the executable bit (x) to the user, group and others.

```bash
chmod +x <file>
```

RemoveAdd the executable bit (x) to the user, group and others.

```bash
chmod -x <file>
```

## Networking

Ping host and output results.

```bash
ping <host>
```

Get information for domain.

```bash
whois <host>
```

Get DNS information for domain

```bash
dig <domain>
```

Reverse lookup host

```bash
dig -x host
```

### Sending Requests

Make a basic GET request to the specifed URI.

```bash
curl <uri>
```

Include HTTP-Header information in the output.

```bash
curl --include <uri>
```

Pass user credential to basic auth.

```bash
curl --user "username:password" <uri>
```

Send a header.

```bash
curl --header "Authorization: 12345" <uri>
```

Show more output.

```bash
curl -v <uri>
     --verbose
```

### Copying Remote Files

Secure copy a file from remote server to the directory on your machine.

```bash
scp user@host:file <directory>
```

Secure copy a file from your machine to the directory on a remote server.

```bash
scp file user@host:<directory>
```

### SSH

Connect to host as user.

```bash
ssh user@host
```

Connect to host on port as user.

```bash
ssh -p port user@host
```

### Processes

List all processes running on port.

```bash
lsof -i :<port>
```

List all processes running on tcp port.

```bash
lsof -i tcp:<port>
```

List process using a file.

```bash
lsof <file>
```

## Text Processing

Process text files. Awk assigns some variables for each data field found:

- $0 for the whole line.
- $1 for the first field.
- $2 for the second field.
- $n for the nth field.

```bash
awk '{print $n}' <file>
```

## Searching

Search for pattern in directory.

```bash
grep <pattern> <directory>
```

Search recursively for pattern in directory.

```bash
grep -r <pattern> <directory>
```

Case-insensitive search for pattern in directory.

```bash
grep -i <pattern> <directory>
```

Prefix output with line numbers.

```bash
grep -n <pattern> <directory>
```

Select non-matching lines.

```bash
grep -v <pattern> <directory>
```

Only print a count of matching lines.

```bash
grep -c <pattern> <directory>
```

Find directories or files in system.

```bash
find <path>
```

Find a file that is a certain type. Possible types: d, t, l.

```bash
find <path> -type <type>
```

Find a file by name but the match is case sensitive.

```bash
find <path> -type <type> -name "<pattern>"
```

Find a file by name but the match is case insensitive.

```bash
find <path> -type <type> -iname "<pattern>"
```

True if the current file or directory is empty.

```bash
find <path> -type <type> -empty
```

Find all occurrences of day in a file and replace them with night - s means substitude and g means global - sed also supports regular expressions.

```bash
sed -i 's/day/night/g' <file>
```

## Compression

Create a tar containing files.

```bash
tar cf <file>.tar <files>
```

Extract the files from tar.

```bash
tar xf <file>.tar
```

Create a tar with Gzip compression.

```bash
tar czf <file>.tar.gz <files>
```

Extract a tar using Gzip.

```bash
tar xzf <file>.tar.gz
```

Compresses file and renames it to file.gz.

```bash
gzip <file>
```

Decompresses Gzip back to file.

```bash
gzip -d <file>.gz
```

## Shortcuts

Move cursor to beginning of line.

```bash
ctrl + a
```

Move cursor to end of line.

```bash
ctrl + e
```

Cut everything from line start to cursor.

```bash
ctrl + u
```

Cut everything from the cursor to end of the line.

```bash
ctrl + k
```

Cut one word backwards using white space as delimiter.

```bash
ctrl + w
```

Paste whatever was cut by the last cut command.

```bash
ctrl + y
```

Kill whatever you are running.

```bash
ctrl + c
```

Clears the screen.

```bash
ctrl + l
```

Clears the screen.

```bash
cmd + k
```

## Redirections

Redirect the standard output (stdout) of command to a file.

```bash
<command> > file
```

Same as `<command> > file`. 1 is the default file descriptor for stdout.

```bash
<command> 1> file
```

Redirect the standard error (stderr) of command to a file. 2 is the default file descriptor for stderr.

```bash
<command> 2> file
```

Redirect stdout and stderr to a file.

```bash
<command> &> file
```

Append stdout of command to a file.

```bash
<command> >> file
```

Redirect the contents of the file to the stdin of command.

```bash
<command> < file
```

Append stderr of command to a file.

```bash
<command> 2>> file
```

Another way to redirect both stdout and stderr of command to a file. This *is not* same as `<command> 2>&1 > file`. Redirection order matters!

```bash
<command> > file 2>&1
```

Discard stdout of command.

```bash
<command> > /dev/null
```

Discard stderr of command.

```bash
<command> 2> /dev/null
```

Discard stdout and stderr.

```bash
<command> &> /dev/null
```

## Others

Print a string.

```bash
echo "<string>"
```

Prints exit code of previous command.

```bash
echo $?
```

Append stdout of command to a file.

```bash
<cmd> >> <file>
```

Show present working directory.

```bash
pwd
```

Print out a list of all environment variables.

```bash
env
```

Clear the terminal screen.

```bash
clear
```

Add directory to the beginning of the $PATH environment variable.

```bash
PATH=$PATH:<dir>
```

Add directory to the ending of the $PATH environment variable.

```bash
PATH=<dir>:$PATH
```

Provide copying to the pasteboard.

```bash
pbcopy < <file>
```

Provide copying to the pasteboard.

```bash
cat <file> | pbcopy
```

Provide pasting to the pasteboard.

```bash
pbpaste
```

Split a file into pieces. The default size for each split file is 1000 lines.

```bash
split
```

Evaluate a file or resource as a script.

```bash
source <file>
```

An arbitrary precision calculator language.

```bash
bc
```

Do not print the normal GNU bc welcome.

```bash
bc -q
```

Run left-hand command and then right-hand command, regardless of success of left-hand command.

```bash
<command>; <command>
```

Run right-command if left-hand command succeeded.

```bash
<command> && <command>
```

Run right-hand command if left-hand command failed.

```bash
<command> || <command>
```

Run command in background.

```bash
<command> &
```

List recent commands.

```bash
history
```

Get the weather forecast in your current location based on your ip address.

```bash
curl wttr.in
```

Get the weather in a different city. Replace any spaces in the name with a + or underscode.

```bash
curl wttr.in/<city>
```

Print a sequence of numbers.

```bash
seq 1 10
```

Print last executed command.

```bash
!!
```
