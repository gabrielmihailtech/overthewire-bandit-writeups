# Bandit Level 5 → Level 6

## Objective

The password for the next level is stored in a file somewhere under the `inhere` directory and has the following properties:

- Human-readable
- 1033 bytes in size
- Not executable

## Initial Enumeration

List the contents of the home directory:

```bash
ls
```

Output:

```text
inhere
```

Navigate into the directory:

```bash
cd inhere
```

List the available items:

```bash
ls
```

Output:

```text
maybehere00
maybehere01
...
maybehere19
```

## Investigation

Determine the file types within the current directory:

```bash
file ./*
```

Output indicated that all entries were directories.

Since the challenge provided specific file characteristics, the `find` command was used to search for a file with the exact size of 1033 bytes.

```bash
find . -size 1033c
```

Output:

```text
./maybehere07/.file2
```

## Solution

Navigate to the directory containing the file:

```bash
cd ./maybehere07
```

Display the contents of the file:

```bash
cat ./.file2
```

The output contained the password for Bandit Level 6.

## Commands Used

```bash
ls
cd
file
find
cat
```

## Explanation

### file

Determines the type of a file or directory.

Example:

```bash
file ./*
```

### find

Searches for files and directories that match specific criteria.

Example:

```bash
find . -size 1033c
```

Where:

- `.` = current directory
- `-size` = search by file size
- `1033c` = exactly 1033 bytes

### cat

Displays the contents of a file.

Example:

```bash
cat ./.file2
```

## Skills Learned

- Using `find` to search for files by size.
- Identifying file types with the `file` command.
- Navigating complex directory structures.
- Combining multiple Linux commands to locate specific files.

## Key Takeaway

The `find` command is a powerful tool for locating files based on specific criteria such as file size, permissions, ownership, and type.
Instead of manually searching through multiple directories, the search can be automated using precise filters.
