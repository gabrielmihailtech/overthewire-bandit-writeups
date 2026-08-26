# Bandit Level 3 → Level 4

## Objective

The password for the next level is stored in a hidden file located in the `inhere` directory.

## Initial Enumeration

List the contents of the current directory:

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

## Investigation

List all files, including hidden files:

```bash
ls -la
```

Output:

```text
...Hiding-From-You
```

The filename begins with dots (`.`), which indicates that it is hidden from normal directory listings.

## Solution

Display the contents of the hidden file:

```bash
cat ...Hiding-From-You
```

The command reveals the password for Bandit Level 4.

## Commands Used

```bash
ls
cd
ls -la
cat
```

## Explanation

### ls

Lists the contents of the current directory.

Example:

```bash
ls
```

### cd

Changes the current working directory.

Example:

```bash
cd inhere
```

### ls -la

Displays all files, including hidden files, together with detailed information such as permissions, ownership, and file size.

Example:

```bash
ls -la
```

### cat

Displays the contents of a file.

Example:

```bash
cat filename
```

## Skills Learned

- Navigating directories using `cd`.
- Identifying hidden files in Linux.
- Using `ls -la` to reveal hidden files.
- Reading file contents using `cat`.
- Understanding that files beginning with a dot (`.`) are hidden by default.

## Key Takeaway

Hidden files are commonly used in Linux systems for configuration files and sensitive information.
Standard directory listings may not display them, making `ls -la` an important command for file discovery and enumeration.
