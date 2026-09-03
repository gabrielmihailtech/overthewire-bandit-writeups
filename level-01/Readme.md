# Bandit Level 1 → Level 2

## Objective

The password for the next level is stored in a file called `-` located in the home directory.

## Initial Enumeration

List the contents of the current directory:

```bash
ls
```

Output:

```text
-
```

To gather more information about the environment, hidden files and permissions were also inspected:

```bash
ls -la
```

## Problem

The file name is a single dash (`-`).

A direct attempt to read the file with:

```bash
cat -
```

does not work as expected because many Linux commands interpret `-` as standard input (stdin) rather than a filename.

## Solution

Specify the file path explicitly using the current directory reference:

```bash
cat ./-
```

The command displays the password for Bandit Level 2.

## Commands Used

```bash
ls
ls -la
cat ./-
```

## Explanation

- `ls` lists files in the current directory.
- `ls -la` displays detailed information, including hidden files and permissions.
- `./` represents the current directory.
- `cat ./-` forces Linux to treat `-` as a filename instead of standard input.

## Skills Learned

- Working with special characters in filenames.
- Understanding how commands interpret the `-` character.
- Using relative paths to access files.
- Performing basic Linux enumeration.

## Key Takeaway

Linux allows files to have unusual names, including characters that may have special meanings to commands. When this happens,
specifying the full relative path can help distinguish between a filename and command behavior.
