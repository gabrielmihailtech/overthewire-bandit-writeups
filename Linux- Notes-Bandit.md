Linux commands- Bandit
ssh bandit0@bandit.labs.overthewire.org -p 2220

Commands:
ssh
- `ssh` is used to connect securely to a remote server.

When I use it
•	Connecting to remote Linux servers
•	SSH access during Bandit challenges
•	Linux administration

ls
- `ls` lists the files and directories in the current location.

When I use it
•	Initial enumeration
•	Viewing directory contents
•	Investigating Linux systems

Cat
- `cat` displays the contents of a file directly in the terminal.

Example:
cat readme
cat /var/lib/dpkg/info/bandit7.password

When I use it
•	Reading text files
•	Viewing passwords during Bandit
•	Checking configuration files

ls -la
- `ls -la` displays detailed information, including hidden files and permissions.

When I use it
•	Finding hidden files
•	Viewing permissions
•	Linux investigations

Exit
- Closes the current shell session.

When I use it
•	Logging out of Bandit
•	Ending SSH sessions

cat  ./-
- `cat ./-` Used when a file is named -.

Example:
cat ./.file2

When I use it
•	Accessing files with special names

Cd
- Changes the current directory.

Example:
Cd inhere

When I use it
•	Navigating the Linux filesystem

File
- `file` command identifies the type of each file

Example: 
File ./* or  file ./-file07

When I use it
•	Determining whether a file contains text, binary data, archives, etc.

find
- Searches for files and directories.

Example:
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
find . -size 1033c

When I use it
•	Locating files
•	Filtering by owner, group, size, name or permissions

2>/dev/null
- Suppresses error messages.

Example:
find / -user bandit7 2>/dev/null

When I use it
•	Reducing clutter from permission-denied errors
•	Large filesystem searches

Pwd
- Displays the current working directory.

When I use it
•	Verifying my current location
•	Troubleshooting navigation issues
•	Working with complex directory structures

./
- References the current directory.

Examples:
cat ./-
cat ./.file2

When I use it
•	Accessing files with special characters
•	Using relative paths
•	Running files and scripts from the current directory
