# Bandit Level 10 → Level 11

## Objective

The password for the next level is stored in the file `data.txt`, which contains Base64 encoded data.

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
VGhlIHBhc3N3b3JkIGlz...
```

The content appears to be Base64 encoded text.

## Investigation

An initial attempt was made using:

```bash
base64 data.txt
```

This produced another encoded string because the command encoded the file instead of decoding it.

After reviewing the challenge requirements, the decode option was used.

## Solution

Decode the Base64 data:

```bash
base64 -d data.txt
```

Output:

```text
The password is ...
```

The decoded output revealed the password for Bandit Level 11.

## Commands Used

```bash
ls
cat
base64
```

## Explanation

### cat

Displays the contents of a file.

Example:

```bash
cat data.txt
```

### base64

Encodes or decodes Base64 data.

Encode:

```bash
base64 filename
```

Decode:

```bash
base64 -d filename
```

### -d

Stands for:

```text
decode
```

and converts Base64 encoded content back to plain text.

Example:

```bash
base64 -d data.txt
```

## Skills Learned

- Recognizing Base64 encoded text.
- Decoding Base64 data.
- Understanding the difference between encoding and decoding.
- Working with encoded information in Linux.

## Key Takeaway

Base64 is a common encoding format used to represent data as readable text. When investigating files or encoded content,
Linux provides built-in tools to quickly decode the information and reveal the original data.
