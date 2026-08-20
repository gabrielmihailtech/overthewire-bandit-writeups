# Bandit Level 0 → Level 1

## Objective

The goal of this level is to log into the Bandit server using SSH and retrieve the password for the next level from a file named `readme`.

## Connection Details

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

Password:

```text
bandit0
```

## Steps

List the files in the home directory:

```bash
ls
```

Output:

```text
readme
```

Read the contents of the file:

```bash
cat readme
```

The output displays the password required to access **Bandit Level 1**.

## Commands Used

```bash
ssh
ls
cat
```

## Explanation

- `ssh` is used to connect securely to a remote server.
- `ls` lists the files and directories in the current location.
- `cat` displays the contents of a file directly in the terminal.

## Skills Learned

- Connecting to a remote Linux machine using SSH.
- Navigating a Linux environment through the command line.
- Listing files within a directory.
- Reading the contents of a file using terminal commands.

## Key Takeaway

This level introduces the basic workflow used throughout the Bandit wargame:
1. Connect to the remote system.
2. Explore the environment.
3. Retrieve information using Linux commands.
4. Use the discovered password to access the next level.
