# Linux Useful Commands

## File System Commands
- `pwd` (Print Working Directory): Displays the current working directory.
- `ls` : Lists the files and directories in the current directory.
- `ls -l` :  Show hidden files (those starting with a dot).
- `cd` (Change Directory) :Changes the current working directory to the specified location.
    - `cd /home/user/documents`
- `mkdir` (Make Directory): Creates a new directory.
    - `mkdir new_folder`
- `rmdir` (Remove Directory): Removes an empty directory.
    -`rmdir directory_name`
- `touch`: Creates an empty file or updates the timestamp of an existing file.
    - `touch newfile.txt`
- `cp` (Copy)
    - `cp source destination`
    - `cp file.txt /path/to/destination`
- `cp -r` : to copy directory to another directory 
    - `cp dirname /path/to/destination`
- `mv` (Move)
    - `mv file.txt newname.txt`
- `cat` (Concatenate and Display)
    - `cat textfile.txt`

## Linux Filter commands

`grep` is a powerful text-search utility in Linux that allows you to search for patterns or text within files or text streams. Here are some useful `grep` commands for common tasks:

1. **Search for a Specific Word in a File:**
   - To find all occurrences of a specific word (e.g., "searchterm") in a file (e.g., "file.txt"):
     ```bash
     grep "searchterm" file.txt
     ```

2. **Case-Insensitive Search:**
   - To perform a case-insensitive search, use the `-i` option:
     ```bash
     grep -i "searchterm" file.txt
     ```

3. **Directory Search:**
   - To perform a case-insensitive search, use the `-i` option:
     ```bash
     grep -i "searchterm" path/to/dir
     ```

The `tail -f` command in Linux is used to display the contents of a file in real-time as new lines are added to it
```bash
tail -f /var/log/syslog
```


## Managing Users and Access in Linux

This document explains various commands for managing user access in a Linux system.

- `sudo -i` command is used to start a new shell session with root privileges.
- The su - <username> command allows you to switch to another user's account with a login shell. 
    - `su - john`
- `passwd <username>` command is used to change the password of a user account. 
    - `passwd john`

## Basic Redirection Commands in Linux

This document explains three fundamental redirection commands in Linux for controlling input and output streams of commands.

The `>` operator allows you to redirect the output of a command to a file. It will overwrite the file if it already exists.

- Example: Redirect the output of a command to a file named "output.txt."
  ```bash
  command > output.txt
    ```
The `>>` operator appends the output of a command to an existing file. It will create the file if it doesn't exist.
- Example: Append the output of a command to a file named "output.txt."
```bash
command >> output.txt
```
**Example**
```bash
history >> log.txt
```