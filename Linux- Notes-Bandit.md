Linux commands- Bandit
ssh bandit0@bandit.labs.overthewire.org -p 2220

Commands:

---
**ssh
- `ssh` is used to connect securely to a remote server.

When I use it
•	Connecting to remote Linux servers
•	SSH access during Bandit challenges
•	Linux administration

---
**ls
- `ls` lists the files and directories in the current location.

When I use it
•	Initial enumeration
•	Viewing directory contents
•	Investigating Linux systems

---
**cat
- `cat` displays the contents of a file directly in the terminal.

Example:
cat readme
cat /var/lib/dpkg/info/bandit7.password

When I use it
•	Reading text files
•	Viewing passwords during Bandit
•	Checking configuration files

---
**ls -la
- `ls -la` displays detailed information, including hidden files and permissions.

When I use it
•	Finding hidden files
•	Viewing permissions
•	Linux investigations

---
**exit
- Closes the current shell session.

When I use it
•	Logging out of Bandit
•	Ending SSH sessions

---
**cat  ./-
- `cat ./-` Used when a file is named -.

Example:
cat ./.file2

When I use it
•	Accessing files with special names

---
**cd
- Changes the current directory.

Example:
Cd inhere

When I use it
•	Navigating the Linux filesystem

---
**file
- `file` command identifies the type of each file

Example: 
File ./* or  file ./-file07

When I use it
•	Determining whether a file contains text, binary data, archives, etc.

---
**find
- Searches for files and directories.

Example:
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
find . -size 1033c

When I use it
•	Locating files
•	Filtering by owner, group, size, name or permissions

---
**2>/dev/null
- Suppresses error messages.

Example:
find / -user bandit7 2>/dev/null

When I use it
•	Reducing clutter from permission-denied errors
•	Large filesystem searches

---
**pwd
- Displays the current working directory.

When I use it
•	Verifying my current location
•	Troubleshooting navigation issues
•	Working with complex directory structures

---
**./
- References the current directory.

Examples:
cat ./-
cat ./.file2

When I use it:

•	Accessing files with special characters
•	Using relative paths
•	Running files and scripts from the current directory

---
**grep
-Searches for a specific word or pattern inside a file.

Example
grep "millionth" data.txt

Output Example
millionth password_here

When I use it:

. Searching for specific words in files
. Finding indicators during investigations
. Filtering large amounts of text
. Looking for usernames, IP addresses, domains, hashes, or passwords
. Bandit challenges involving text searches

---
**sort
-Sorts lines of text alphabetically.

Example
sort data.txt

When I use it

-Organizing text output
-Preparing data for filtering
-Processing logs
-Working with uniq

---
**uniq
-Removes or counts duplicate lines.

Example
sort data.txt | uniq -c

When I use it

-Finding duplicate entries
-Identifying unique values
-Analyzing logs
-Processing large text files

---
**Pipe (|)

-Passes the output of one command as input to another command.

Example
sort data.txt | uniq -c

When I use it

-Combining commands
-Filtering output
-Text processing
-Linux investigations
-Log analysis

---
**strings
-Extracts readable text from binary files.

Example
strings data.txt


When I use it

-Investigating binary files
-Malware analysis
-Extracting readable content from executables
-Solving Bandit challenges involving binary data

---
**tr
-Translates or replaces characters from one set to another.

Example
tr 'A-Za-z' 'N-ZA-Mn-za-m' < data.txt

When I use it

-Decoding ROT13 text
-Character substitution
-Simple text transformations
-Processing command output
-Bandit challenges involving encoded text
-Feeding file contents into commands
-Text processing workflows
-Avoiding the use of cat when input can be redirected directly
-Linux automation and scripting

---
**mktemp -d

Description
Creates a temporary directory.

Example
mktemp -d

When I use it

-Creating temporary workspaces
-File analysis
-Malware investigations
-Extracting archives safely

---
**cp

Description
Copies files and directories.

Example
cp ~/data.txt .


When I use it

-Creating backups
-Copying files to a working directory
-Preserving original files

---
**mv

Description
Moves or renames files.

Example
mv data data.gz


When I use it

-Renaming files
-Preparing files for decompression
-Organizing directories

---
**xxd

Description
Creates or reverses hexdumps.

Example
xxd -r data.txt > data


When I use it

-Converting hexdumps back to binary files
-File forensics
-Malware analysis
-Binary data investigations

---
**gunzip

Description
Decompresses gzip archives.

Example
gunzip data.gz

When I use it

-Extracting gzip archives
-Log investigation
-File recovery

---
**bunzip2

Description
Decompresses bzip2 archives.

Example
bunzip2 data.bz2

When I use it

-Extracting bzip2 archives
-Working with compressed Linux files

---
**tar

Description
Creates or extracts tar archives.

Example
tar -xf data.tar


When I use it

-Extracting archives
-Packaging files
-Linux administration
-Incident response investigations
