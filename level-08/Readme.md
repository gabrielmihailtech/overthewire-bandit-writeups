# Bandit Level 8 → Level 9

## Objective

The password for the next level is stored in the file `data.txt` and is the only line that occurs once.

## Initial Enumeration

List the contents of the current directory:

```bash
ls
```

Output:

```text
data.txt
```

Inspect the contents of the file:

```bash
cat data.txt
```

The file contains many repeated strings, making it difficult to identify the unique entry manually.

## Investigation

Sort the contents of the file and count duplicate occurrences:

```bash
sort data.txt | uniq -c
```

The command displays each unique line together with the number of times it appears.

Example:

```text
10 abc123
10 xyz456
1 password_here
10 qwe789
```

The line with a count of:

```text
1
```

is the password required for the next level.

## Commands Used

```bash
ls
cat
sort
uniq
```

## Explanation

### sort

Sorts lines alphabetically.

Example:

```bash
sort data.txt
```

### uniq

Filters duplicate lines from sorted input.

Example:

```bash
sort data.txt | uniq -c
```

### | (Pipe)

Sends the output of one command directly to another command.

Example:

```bash
sort data.txt | uniq -c
```

In this challenge:

- `sort` groups identical lines together.
- `uniq -c` counts how many times each line appears.

## Skills Learned

- Sorting text data.
- Identifying duplicate and unique entries.
- Using pipelines (`|`).
- Combining Linux commands to process large text files.

## Key Takeaway

Many Linux commands become more powerful when combined. By piping the output of `sort` into `uniq -c`, it becomes easy to identify values that appear only once within large datasets.
