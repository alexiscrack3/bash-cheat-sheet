# Unix Cheat Sheet

A collection of some of the most useful Git commands

## Table of Contents

1. [File System](#file-system)
    * [Listing Directories and Files](#listing-directories-and-files)
    * [Changing Working Directory](#changing-working-directory)
    * [Making Directories](#making-directories)
    * [Copying Files](#copying-files)
    * [Moving Files](#moving-files)
    * [Making Files](#making-files)
    * [Displaying the Contents of a File](#displaying-the-contents-of-a-file)
2. [Compression](#compression)
3. [System](#system)
4. [Networking](#networking)
5. [Process Management](#process-management)
6. [Permissions](#permissions)
7. [Searching](#searching)
8. [Others](#others)

## File System

### Listing Directories and Files

List items in current directory.

```bash
ls
```

List items in current directory and show in long format to see perimissions, size, and modification date.

```bash
ls -l
```

List all items in current directory, including hidden files.

```bash
ls -a
```

### Changing Working Directory

Change directory to dir.

```bash
cd <dir>
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

Make directory dir.

```bash
mkdir <dir>
```

### Removing Directories

Remove empty directory.

```bash
rmdir <dir>
```

Remove directory dir recursively.

```bash
rm -r <dir>
```

Ignore nonexistent files, never prompt.

```bash
rm -f <dir>
```

### Removing Files

Remove file.

```bash
rm <file>
```

Remove files that match a pattern.

```bash
rm <pattern>
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

### Moving Files

Move (rename) file1 to file2.

```bash
mv <file1> <file2>
```

### Making Files

Create or update file

```bash
touch <file>
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

## Compression

## System

Show directory space usage.

```bash
du <file>
```

Show directory space usage with human readable size.

```bash
du -h <file>
```

## Networking

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

## Process Management

Display all running processes.

```bash
top
```

Kill process id pid.

```bash
kill <pid>
```

Force kill process id pid.

```bash
kill -9 <pid>
```

## Permissions

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
````

chmod +x <file>
chmod -x <file>

## Searching

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

## Others

Show present working directory.

```bash
pwd
```

Executes the right-hand command of && only if the previous one succeeded.

```bash
<command> && <command
```

Executes the right-hand command of || only it the previous one failed.

```bash
<command> || <command
```