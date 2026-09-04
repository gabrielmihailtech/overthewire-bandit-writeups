# Bandit Level 12 → Level 13

## Objective

The password for the next level is stored in a file that has been repeatedly compressed and encoded. The provided file, `data.txt`, contains a hexdump of the original file.

## Initial Investigation

Display the contents of the file:

```bash
cat data.txt
```

The file contained hexadecimal data rather than readable text.

A temporary working directory was created:

```bash
mktemp -d
```

Navigate into the directory:

```bash
cd /tmp/tmp.xxxxxxxx
```

Copy the challenge file:

```bash
cp ~/data.txt .
```

Convert the hexdump back into its original binary format:

```bash
xxd -r data.txt > data
```

## Investigation Process

Identify the file type:

```bash
file data
```

Output:

```text
gzip compressed data
```

### Extraction Sequence

```bash
mv data data.gz
gunzip data.gz
```

```bash
file data
```

Output:

```text
bzip2 compressed data
```

```bash
mv data data.bz2
bunzip2 data.bz2
```

```bash
file data
```

Output:

```text
gzip compressed data
```

```bash
mv data data.gz
gunzip data.gz
```

```bash
file data
```

Output:

```text
POSIX tar archive
```

```bash
mv data data.tar
tar -xf data.tar
```

Extracted:

```text
data5.bin
```

```bash
file data5.bin
```

Output:

```text
POSIX tar archive
```

```bash
mv data5.bin data5.tar
tar -xf data5.tar
```

Extracted:

```text
data6.bin
```

```bash
file data6.bin
```

Output:

```text
bzip2 compressed data
```

```bash
mv data6.bin data6.bz2
bunzip2 data6.bz2
```

```bash
file data6
```

Output:

```text
POSIX tar archive
```

```bash
mv data6 data6.tar
tar -xf data6.tar
```

Extracted:

```text
data8.bin
```

```bash
file data8.bin
```

Output:

```text
gzip compressed data
```

```bash
mv data8.bin data8.gz
gunzip data8.gz
```

```bash
file data8
```

Output:

```text
ASCII text
```

## Solution

Display the contents of the final file:

```bash
cat data8
```

The file contained the password for Bandit Level 13.

## Commands Used

```bash
mktemp
cd
cp
xxd
file
mv
gunzip
bunzip2
tar
cat
```

## Skills Learned

- Working with temporary directories.
- Reversing hexdumps using `xxd`.
- Identifying file types using `file`.
- Extracting gzip compressed files.
- Extracting bzip2 compressed files.
- Extracting tar archives.
- Performing multi-stage file analysis.
- Tracking file transformations during investigations.

## Key Takeaway

Complex files are often nested inside multiple layers of compression and archives. 
The most effective approach is to identify each file type with `file`, extract it, and repeat the process until the final content is revealed.
