# Unix Cheat Sheet

A collection of some of the most useful Git commands

## Table of Contents

1. [File System](#file-system)
    * [Listing Directories and Files](#listing-directories-and-files)
    * [Making Directories](#making-directories)
    * [Making Files](#making-files)
    * [Displaying the Contents of a File](#displaying-the-contents-of-a-file)
2. [Searching](#searching)
3. [Others](#others)

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

### Making Directories

Make directory dir.

```bash
mkdir <dir>
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

Executes the right-hand command of && only if the previous one succeeded.

```bash
<command> && <command
```

Executes the right-hand command of || only it the previous one failed.

```bash
<command> || <command
```