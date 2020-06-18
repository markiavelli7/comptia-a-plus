# Understanding the CLI

## Windows

**dir** - shows all system files, the date and time that they were created, and how big the files are. `<DIR>` represents a folder, and not a file

Anything that we type on the end of a command is called a **switch**

Adding the **/?** switch to a command will show us some of the available commands and give us more info. Equally useful is **help `<command>`**

**cls** - clear screen

## Linux

**ls** - list files and folders in the current directory

**clear** - clear screen

Switches are added in Unix environments with **-l**. If we want information on how to use a command, we type **man `<command>`**

# Navigating the CLI

Every OS has a home directory where individual users go to

## Windows

**cd** stands for change directory

**cd `\`** - takes us to the root directory

## Linux

**cd ~** - takes us back to the home directory

**cd /** - takes us to the root directory

**pwd** - shows us what directory we are in

# Working With Folders

## Windows

Windows doesn't care about capitalization, Linux does

**md `<Directory Name>`** - make directory

**rd `<Directory Name>`** - remove directory (only works on empty directories)

**rd/s `<Directory Name>`** - remove directory (this command works with directories that are not empty)

We can't delete non-empty diretories using "rd" in Windows. To delete directories, we have to use the "rd/s" command

## Linux

Case Sensitive

**mkdir `<Directory Name>`** - make directory

**rmdir `<Directory Name>`** - removes empty directories

**rm -r `<Directory Name>`** -removes directories that are not empty

# Working With Files

## Windows

**del `<File Name>`** - delete file

**del \*.txt** - _ is a wildcard, it matches anything. In the _.txt example, any file that ends in .txt will be deleted.

**del \*.\*** - this will delete everything

### Copying Files

1. Get to the directory where the files that we want to copy are located

2. Type **copy `<Name of the file we want to copy>` `<Path of where we want it to go to>`**

3. Hit enter

Copying will leave the original files intact and create a brand new copy

### Moving Files

1. Get to the directory where the files that we want to copy are located

2. Type **mov `<Name of the file we want to copy>` `<Path of where we want it to go to>`**

3. Hit enter

Moving will delete the original file and create a new file at the target destination

**Be careful about typos, especially in the destination directory, if Windows doesn't recognize the directory it will compile all of the files into one big file and rename it to the directory it didn't recognize.**

## Linux

**rm `<Name of File>`** - remove a file

### Copying

**cp `<Name of File> <Desination Diretory>`** - copy file(s)

### Moving

**mv `<Name of File(s)> <Destiation Directory>`** move file(s)

# Working With Drives

We will want administrator privileges to run these commands

**format e: /FS:NTFS**

**chkdsk** - looks at the existing file table

**chkdsk /f** - look at the existing file table AND fix things

**sfc /scannow** - System File Checker. Checks our current backups vs our current files. Checks for corruption/etc

If we run into any kind of a problem with SFC, the standard rule is to then run **dism**.

**dism /online /cleanup-image /restorehealth** - Built into every copy of Windows. Will go online and find the version of Windows that we are running and compare our system store to what is known and good at Microsoft.

**We Always Run SFC first. If it finds any errors at all, we run DISM. After running DISM, we run SFC again to verify that everything is OK.**

## diskpart

Puts us into an interactive screen

# Super Copy Commands

**xcopy** - the 'OG', goes back to earlier versions of windows

```javascript
xcopy c:\backup x: /s /v /h
```

**Switches**

s - copies subdirectories as well
v - verify the data
h - no hidden files

**robocopy** - more verification, more speed than xcopy

```javascript
robocopy c:\backup /s /xa:h
```

/xa:h - switch to exclude hidden files

## Linux

**dd** - bit-by-bit copier

```javascript
dd if=/dev/sda of=/dev/sdb
```

if= - source partition
of= - destination partition

# Advanced Windows Command Line

**shutdown** - shut computer down. /s - shutdown only. /r - shutdown and restart

**tasklist** - gives us all of the running processes and their ids

**taskkill** - lets us kill processes

**gpupdate** - query the domain controller to see if any group policy settings have been changed

**gpresult** - tell us what the group policy changes are

# Advanced Linux Commands

**shutdown** - shutdown computer

**apt-get** - Linux debian command. apt-get is a repository of just about any program that we can think of

```javascript
sudo apt-get update
sudo apt-get install joe
```

**sudo apt-get upgrade joe** - Update applications

**sudo apt-get remove joe** - Remove application

**ps** - Tells us about processes that the user is running

**ps aux** - Show us all of the processes with a lot of details

**ps aux | grep 'libre'** - take the ps aux command, take all of the output and send it to grep. grep is going to look for 'libre'

**kill 1345** - kill process 1345

**vi** - absolute disaster of a text editor

# Command Line Permissions

**icacls `<folder we want to grant access to> /grant <User we want to grant control to>`**

**icacls timmy /grant Mike:F**

## Linux

**chmod** - change file access

read - 4
write - 2
execute - 1

**chmod `<permissions for owner><permissions for group><permissions for everyone> <file>`**

**chmod 744 test** - Allow owner to read, write, and execute. Allow group and everyone else read permissions

**chown** - change ownership

**sudo chown `<new owner>` `<file>`**

**sudo passwd** - change password

# Intro to Scripting

A batch file is a text file that stores a list of commands

Batch files use a ".bat" file extension

Environment variables are phrases that point to system-wide functions

PowerShell provides far more powerful scripts

Linux bash shell scripts also provide powerful scripting functions

Automating tasks using the command prompt

Batch file - file that we write out on a text editor

**set** - command that shows us the environment variables on the system

**%HomePath%** - references the environment variable HomePath

# Interpreted Languages

.exe files are executable files, preset lists of commands that are designed to talk to the OS and the CPU.

.exe files are compiled code.

Interpreted languages
