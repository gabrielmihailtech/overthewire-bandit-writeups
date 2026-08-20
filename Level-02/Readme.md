# Bandit Level 2 → Level 3

## Objective

The password for the next level is stored in a file called:

```text
--spaces in this filename--
```

located in the home directory.

## Initial Enumeration

List the contents of the current directory:

```bash
ls -la
```

Output:

```text
--spaces in this filename--
```

## Problem

The file name contains spaces.

A direct attempt to read the file may fail because the shell interprets spaces as separators between multiple arguments.

Examples:

```bash
cat ./--spaces in this filename--
```

Result:

```text
cat: ./--spaces: No such file or directory
cat: in: No such file or directory
cat: this: No such file or directory
cat: filename--: No such file or directory
```

## Solution

The filename must be enclosed in quotation marks:

```bash
cat "./--spaces in this filename--"
```

This displays the password required for Bandit Level 3.

## Commands Used

```bash
ls -la
cat "./--spaces in this filename--"
```

## Explanation

- `ls -la` lists all files, including hidden files, and displays detailed information.
- Spaces in filenames must be escaped or enclosed in quotes.
- Quotation marks allow the shell to interpret the entire string as a single filename.
- `cat` reads and displays the contents of the file.

## Skills Learned

- Working with filenames containing spaces.
- Understanding how the Linux shell processes arguments.
- Using quotation marks to reference filenames correctly.
- Basic file inspection in Linux.

## Key Takeaway

Filenames containing spaces require special handling. Wrapping the filename in quotation marks ensures that Linux treats it as a single argument instead of multiple separate words.
