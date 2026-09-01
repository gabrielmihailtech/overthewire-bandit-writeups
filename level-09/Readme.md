# Bandit Level 9 → Level 10

## Objective

The password for the next level is stored in the file `data.txt` in one of the few human-readable strings, preceded by several `=` characters.

## Investigation

The challenge involved a binary file rather than a normal text file.

An initial attempt was made to search for the character `=` directly:

```bash
grep "=" data.txt
```

Output:

```text
grep: data.txt: binary file matches
```

This indicated that `data.txt` contained binary data.

## Solution

Extract all human-readable strings from the file:

```bash
strings data.txt
```

To quickly identify the relevant string, filter the output using `grep`:

```bash
strings data.txt | grep "="
```

Output:

```text
========== [password]
```

The password for Bandit Level 10 was displayed after a sequence of `=` characters.

## Commands Used

```bash
strings
grep
```

## Explanation

### strings

Extracts human-readable text from binary files.

Example:

```bash
strings data.txt
```

This command displays only the readable text contained within a binary file.

### grep

Searches for specific text patterns.

Example:

```bash
strings data.txt | grep "="
```

This filters the output and displays only lines containing the `=` character.

### |

The pipe operator sends the output of one command to another.

Example:

```bash
strings data.txt | grep "="
```

The output of `strings` becomes the input for `grep`.

## Skills Learned

- Identifying binary files.
- Extracting readable strings from binary data.
- Using command pipelines.
- Filtering output with `grep`.
- Finding specific information within large datasets.

## Key Takeaway

Binary files cannot always be searched effectively using standard text-processing commands.
The `strings` command can extract readable content, which can then be filtered using tools such as `grep` to locate specific information quickly.
