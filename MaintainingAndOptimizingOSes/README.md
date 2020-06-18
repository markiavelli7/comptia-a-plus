# Patch Management

Windows 7 Update gives the user the ability to choose which updates to install and when

Windows 10 Update locks down the update system; the only option is to pause the update and choose active hours

Patch managment in Ubuntu Linux offers more options for updating

# Working with Disks

**Error Checking** - check for errors and faults on our hard drives and SSDs

**Optimization** - organize our hard drives and to a lesser extent our SSDs so that they can run more efficiently

Error checking runs chkdsk on a disk partition to check for bad sectors

Trimming allows data to be written in individual pages termed "available for use"

Optimizing trim blocks in SSDs allows new data to be written into partially filled blocks

# Working with Applications

In Windows, we can uninstall applications using the **Programs and Features** tool

When we install a progam, we either putting it into Program files if it is 64-bit or Program files (x86) if it is 32-bit.

### Cleaning Up Uninstall Debris

**CCleaner** - free version does a pretty good job at cleaning up the Registry. Not for the faint of heart. **Make a backup of the Registry before we run it, just in case we need to do a restore**

# System Restore

Found in **System/System Properties/System Protection**

1. Turn on system protection and set disk space max usage
2. Create a restore point

System Restore focuses on applications, the Registry and a few critical system files

**Restore points are a good idea when we are adding applications, changing applications, or adding device drivers**

Creating too many System Restore points, without noting the OS changes that we made in between, can become confusing

Windows can restore from a System Restore point even in Windows Recovery Environment

# Backing up Files

**Windows Backup and Restore (Windows 7)** -

A system repair disk is a bootable media that helps with recovery.

A system image isa copy of our system at the time of backup

Backup tools require external backup sources such as external hard drives or network locations

# Task Scheduler

Found under Administrative Tools

Task Scheduler enables users to schedule repetitious tasks

Many tasks are prescheduled by Windows

Creating our own tasks is easy with Task Scheduler
