# Bandit Level 11 → Level 12

## Objective

The password for the next level is stored in the file `data.txt`, where all lowercase (`a-z`) and uppercase (`A-Z`) letters have been rotated by 13 positions (ROT13).

## Initial Enumeration

List the contents of the current directory:

```bash
ls
```

Output:

```text
data.txt
```

Display the contents of the file:

```bash
cat data.txt
```

Output:

```text
Gur cnffjbeq vf ...
```

The text was readable but did not make sense. The challenge description indicated that the content had been encoded using ROT13.

## Investigation

ROT13 shifts each letter by 13 positions in the alphabet.

To decode the text, the `tr` command was used:

```bash
tr 'A-Za-z' 'N-ZA-Mn-za-m' < data.txt
```

The command translated the encoded characters and revealed the original text.

## Solution

Decode the contents of the file:

```bash
tr 'A-Za-z' 'N-ZA-Mn-za-m' < data.txt
```

Output:

```text
The password is ...
```

The decoded text contained the password for Bandit Level 12.

## Commands Used

```bash
ls
cat
tr
```

## Explanation

### cat

Displays the contents of a file.

Example:

```bash
cat data.txt
```

### tr

Translates characters from one set to another.

Example:

```bash
tr 'A-Za-z' 'N-ZA-Mn-za-m' < data.txt
```

In this challenge:

```text
A → N
B → O
C → P
...
N → A
O → B
...
```

This reverses the ROT13 encoding.

### <

Input redirection.

Example:

```bash
tr 'A-Za-z' 'N-ZA-Mn-za-m' < data.txt
```

The contents of `data.txt` are passed directly to the `tr` command.

## Skills Learned

- Understanding ROT13 encoding.
- Translating characters with `tr`.
- Using input redirection.
- Decoding simple substitution ciphers.
- Processing text directly from files.

## Key Takeaway

The `tr` command is a powerful tool for character translation and text transformation. By combining `tr` with input redirection, encoded text can be quickly decoded without modifying the original file.
