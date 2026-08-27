# Bandit Level 6 → Level 7

## Objective

The password for the next level is stored somewhere on the server and has the following properties:

- owned by user `bandit7`
- owned by group `bandit6`
- size of 33 bytes

## Investigation

The challenge required searching the entire filesystem for a file matching specific criteria.

To locate the file, the following command was used:

```bash
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
```

Output:

```text
/var/lib/dpkg/info/bandit7.password
```

## Solution

Display the contents of the file:

```bash
cat /var/lib/dpkg/info/bandit7.password
```

The file contained the password for Bandit Level 7.

## Commands Used

```bash
find
cat
```

## Explanation

### find

Searches for files and directories.

Parameters used:

```bash
find / -user bandit7 -group bandit6 -size 33c
```

- `/` searches the entire filesystem
- `-user bandit7` finds files owned by user bandit7
- `-group bandit6` finds files owned by group bandit6
- `-size 33c` finds files exactly 33 bytes in size

### 2>/dev/null

Redirects error messages to `/dev/null`, preventing permission-related errors from being displayed.

Example:

```bash
find / 2>/dev/null
```

### cat

Displays the contents of a file.

## Skills Learned

- Searching files based on ownership.
- Searching files based on group permissions.
- Filtering files by exact size.
- Using output redirection.
- Working with the Linux filesystem hierarchy.

## Key Takeaway

The `find` command is one of the most powerful Linux utilities. By combining multiple search criteria, specific files can be located efficiently even within a large filesystem.
``
