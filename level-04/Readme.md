# Bandit Level 4 → Level 5

## Objective

The password for the next level is stored in the only human-readable file in the `inhere` directory.

## Initial Enumeration

Navigate to the challenge directory:

```bash
cd inhere
```

List the available files:

```bash
ls -la
```

Output:

```text
-file00
-file01
-file02
-file03
-file04
-file05
-file06
-file07
-file08
-file09
```

## Investigation

Several files were inspected using the `cat` command.

Examples:

```bash
cat ./-file00
```

```bash
cat ./-file01
```

```bash
cat ./-file02
```

Most files produced unreadable binary output.

Eventually, one file displayed normal text:

```bash
cat ./-file07
```

The output contained the password for Bandit Level 5.

## Commands Used

```bash
cd
ls -la
cat
```

## Explanation

- `cd` was used to navigate into the challenge directory.
- `ls -la` displayed the files available in the directory.
- `cat` was used to inspect the contents of individual files.
- Most files contained binary data, while only one file contained readable text.

## Skills Learned

- Identifying the difference between text files and binary files.
- Inspecting files from the command line.
- Working with filenames beginning with `-`.
- Basic enumeration within Linux.

## Key Takeaway

Not all files contain readable text. Inspecting multiple files helped identify the only human-readable file, which stored the password for the next level.
