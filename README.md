# Unix Cheat Sheet

A collection of some of the most useful Git commands

## Table of Contents

1. [File System](#file-system)
    * [Listing Directories and Files](#listing-directories-and-files)
    * [Displaying the Contents of a File](#displaying-the-contents-of-a-file)
2. [Searching](#searchgin)

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

### Displaying the Contents of a File

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
