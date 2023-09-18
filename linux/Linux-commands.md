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

## File permission

- The `chmod` command in Linux is used to change file permissions. It allows you to modify the read (r), write (w), and execute (x) permissions for files and directories. You can set permissions for the owner (user), group, and others (everyone else) who have access to the file.
```bash
chmod 744 install.sh
```
The first number (7) represents permission for a user: 7 = ( 4 (read) +2 (write) +1(execute) )
The second number (4) represents permissions for a group: 4 (read)
The third number (4) represents permissions for others: 4 (read)

- The `chown` command in Linux is used to change the owner and group owner of files and directories. It allows you to transfer ownership of a file or directory to another user or group.

The basic syntax for the `chown` command is as follows:

```bash
chown [OPTIONS] USER[:GROUP] FILE
sudo chown -R user2:group2 myfolder
```
After running this command, "myfolder" and all its contents will be owned by "user2" and assigned to "group2."

## `curl` Command in Linux
The `curl` command in Linux is a versatile and powerful tool for making network requests to transfer data to or from a server or URL. It supports various protocols, including HTTP, HTTPS, FTP, FTPS, SCP, SFTP, LDAP, and more. `curl` is commonly used for tasks such as downloading files, testing APIs, and performing various web-related operations.

```bash
curl [OPTIONS] [URL]
```
- Download the file
    `curl -O https://example.com/example.txt`
- Send GET Requests
    `curl https://api.example.com/data`
- Send POST Requests
    `curl -X POST -d "key1=value1&key2=value2" https://api.example.com/submit`

## Package management commands
#### For RPM based linux

- Directly install the package
```bash
sudo yum install package-name  # For older versions (e.g., CentOS 6)
sudo dnf install package-name  # For newer versions (e.g., CentOS 8)
```
- Remove package
```bash
sudo yum remove package-name  # For older versions
sudo dnf remove package-name  # For newer versions
```
- Upgrade installed package
```bash
sudo yum install package-name  # For older versions (e.g., CentOS 6)
sudo dnf install package-name  # For newer versions (e.g., CentOS 8)
```

- Download the RPM package
`curl -O https://example.com/path-to/package.rpm`

- Install the RPM package
`sudo rpm -i package.rpm`

- Verify the installation
`rpm -q package-name`

#### For Debian-based based linux
- Directly install the package
```bash
sudo apt-get install package-name
```
- Remove package
```bash
sudo apt-get remove package-name 
```
- Upgrade installed package
```bash
sudo apt-get update
```

- Download the RPM package
`curl -O https://example.com/path-to/package.deb`

- Install the RPM package
`sudo dpkg -i package.deb`

- Verify the installation
`rpm -q package-name`