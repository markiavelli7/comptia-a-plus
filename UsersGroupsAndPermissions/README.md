# Introduction to Users and Groups

Windows combined with NTFS gives tremendous control over resources

NTFS permissions can be assigned

A group is a container for user accounts

Permissions are assigned to groups for easy administration

# Managing Users and Groups

Settings > Accounts enables basic account creation

User Accounts in Control Panel provides more account control

Local Users and Groups provides the most control over users and groups

# NTFS Permissions

All files and folders on an NTFS formatted drive have NTFS permissions

Full Control permission gives the user complete control over the resource

Inheritance is when a new folder or file gets the permissions of the folder in which it was created

Inheritance is stopped with a deny

**Full Control** - enables us to do anything that we want

**Modify** - enables us to read, write, and delete files and subfolders

**Read and Execute** - enables us to see the contents of the folder and any subfolders as well as run any executable programs or associations in that folder

**List Folder Contents** - enables us to see the contents of the folder and any subfolders

**Read** - enables us to view a folder's contents and open any file in the folder

**Write** - enables us to write to files and create new files and folders

## Files

**Full Control** - enables us to do anything that we want with the file

**Modify** - enables us to read, write, and delete the file

**Read and Exectue** - enables us to open and run the file

**Read** - enables us to view a folder's contents and open any file in the folder

**Write** - enables us to open and write to the file

### Inheritance

If we have a folder where we specify permissions, any files inside of that folder will inherit the permissions defined on the parent.

### Allow vs. Deny

The idea behind Deny is to stop inheritance. If we have to use Deny, it usually means that we've structured something wrong

# Linux and macOS Permissions

Linux and macOS permissions use the owner, group, and everyone

Each of these three can have read, write, or execute permissions

These are assigned by changing the file or folder properties

# File Explorer

File Explorer is the primary tool for folder and file manipulation in Windows

File Explorer in highly customizable

There's usually multiple wary to do the same job in File Explorer

# Sharing Resources

Windows networking has both NTFS and share permissions

Shared resources have a UNC name

Resources are first offered for sharing, then others access the shared resource

Shared resources can be mapped to a drive letter

# Security Policy

Security policies define a broad spectrum of security features

We use the **Local Security Policy** application to manage policies

Account policies enable login and password rules

## Passwords

**Maximum Password Age** - how long can the password be there before it has to be changed
