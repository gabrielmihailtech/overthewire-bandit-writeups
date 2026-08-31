# Bandit Level 7 → Level 8

## Objective

The password for the next level is stored in the file `data.txt` next to the word `millionth`.

## Investigation

The challenge provided a large text file named `data.txt`.

Instead of manually reading the entire file, the `grep` command was used to search for a specific word.

Search for the string:

```bash
grep "millionth" data.txt
```

Output:

```text
millionth    [password]
```

The password was displayed next to the word `millionth`.

## Solution

Use the following command:

```bash
grep "millionth" data.txt
```

The output contains the password required for Bandit Level 8.

## Commands Used

```bash
grep
```

## Explanation

### grep

Searches for a specific word or pattern within a file.

Example:

```bash
grep "millionth" data.txt
```

Parameters:

```bash
"millionth"
```

The text pattern being searched for.

```bash
data.txt
```

The file to search.

## Skills Learned

- Searching text files efficiently.
- Locating specific information within large files.
- Using pattern matching with `grep`.
- Avoiding manual review of large amounts of data.

## Key Takeaway

The `grep` command is one of the most useful Linux text-processing tools. It allows specific information to be extracted quickly from large files by searching for keywords or patterns.
