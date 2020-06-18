# Understanding Partitioning

A partition is a logical electronic device readable by an OS

Partitions must be created and mounted

In Windows, partitions manifest as drive letters; in Linux/macOS, partitions manifest as folders

In order for an operating system to use a mass storage device we have to take the physical mass storage device and turn it into a logical electronic device that makes sense to an OS.

If a hard drive were a house, partitions are the different rooms in the house.

## Common Partitions

- **Operating System**

- **Swap File**

- **Recovery Partition**

It is the OSes themselves that make the partitions

After we create a partition, we have to mount it, so that we as the user are able to see it.

# MBR Partitioning

Oldest type of partition still in use today

MBR consisted of a boot loader and up to four partitions with one set as an active partition

If we need more than four partitions on a single drive, we create an extended partition and add logical drives to that partition

Master Boot Record (MBR) - Not only does it define partitions, but it also tells the computer where to find the OS. LBA 0 is where the directory is. Stored in LBA 0 is something called the Master Boot Record.

**Bootloader**: The first code read off of mass storage. The job of the bootloader is to point to the start of one of the other 4 partitions. In the old days, the other 4 partitions commonly held other OSes (UNIX, CPM, DOS).

The bootloader would have to be assigned an **active partition**. This is where we want to boot from by default.

**Limitations of MBR**

- limited to 2TB of storage

- limited to 4 partitions

To see hard drives in Windows, we use a tool called Disk Management

A partition and a volume are the same thing

Because we could only have a maximum of 4 partitions, **extended partitions** were created. If we wanted more than 4, one of the partitions is split, into **logical drives/partitions**.

# GUID Partition Table (GPT) Partitioning

Designed to take advantage of UEFI BIOSes. GPT works closely with UEFI to provide a broad cross section of extra features.

## Global Unique Identifier (GUID)

128 bit unique value that defines our particular partitioning system and makes us unique all over the world.

We can have up to 128 partitions/drive

GPT creates a **Protective MBR** so that if someone with an older system plugs a GPT drive into their computer, it will protect the drive. The older computer won't be able to read the LBA Partitions and they will get a warning.

The other thing that is in the Protective MBR is that if the system is GPT capable, there will be a little piece of information that tells the computer that the drive is a GPT, so it can ignore the Protective MBR

**Primary GPT Header (LBA 1)**: This stores the information that we need for the partitions

**Secondary GPT Header (usually LBA 2)**: Just a copy of the Primary GPT Header. Allows for self healing

# Understanding File Systems

A file system is applied to a partition by formatting

A partition must be formatted before they are usable

All file systems have a data structure that keeps track of the location of files and folders

File systems often have a problem with fragmentation

Formatting is like creating shelves for the rooms in our house so that we have a place to store our folders and files. If we want to use a drive, we have to partition it, and then format it.

## File Allocation Table

An index card at the beginning of every partition that keeps track on an LBA by LBA basis where all of our stuff is on the partition.

FAT16 - Two Column spread sheet with the LBA value for every block on the drive in one column. In the other column is the actual content that is in that block for every LBA value.

FAT32 - 8 Hexadecimal characters

Part of the format process is to go through and check all of the individual blocks and flag bad blocks that can't be used.

We we think that we have deleted something on a hard drive, we have only flagged it as available for reuse.

**Fragmentation** is where we have a file stored in multiple spaces on the drive, in contrast with blocks that would be next to each other.

# Popular File Systems

FAT32 and exFAT are handy for them drives

## FAT32

Very old file system. Can support up to 8TiB volumes. FAT32 works on very small hard drives and thumb drives

## New Technology Files System (NTFS)

When we are talking about Windows, NTFS is the big dog. Massive volumes up to 16EiB. Individual files can be up to 256 TiB big. We don't use a FAT with NTFS, we use a **Master File Table (MFT)**. Supports compression, encryption, security.

**ExFAT** supports about the same sizes that we see with NTFS, but it has less overhead

## Compact Disc File System (CDFS)

Design to allow optical discs to organize a file system that we can read with our OS. Standard system for all optical media. Can have individual files up to 4GiB

## ext3/ext4

Linux based.

ext3 supports 32TiB volumes, 2 GiB files

ext4 supports 2EiB volumes, 16TiB files

## Hierarchical File System Plus (HFS+)

macOs defacto system, unique to mac. 8 EiB volumes and files.

# Formatting in Action

Windows uses Disk Management ot partition and format disks

New drives must first be initialized in Windows

There is no single Linux tool for partitioning and formatting - choose the one that you like

# Dynamic Disks

Unique to Microsoft Windows, to make this work, we have to set our drives to dynamic.

Inside of Disk Management, we can convert a drive to dynamic

**Windows Recommendations:**

1. Always keep the boot drive basic (not dynamic)

2. Set drives to GPT

3. Easy to create dynamic drive, but if we go back to basic **we lose all of our data.**

# Software RAID in Storage Spaces

Software RAID uses the operating system to configure the RAID array

Windows comes with a powerful tool called Storage Spaces to configure advanced software RAID arrays

Storage Spaces provides superb flexibility

# Encrypting Mass Storage

File-based and Disk-based

### File-based Encryption

There is some kind of software feature built into the OS where we can pick a particular file or folder and say 'go ahead and encrypt this'

In Windows, Encrypting File System (EFS) is used (actually built into NTFS)

### Disk-based Encryption

Some type of tool that is built into the OS that will encrypt entire drives.

If we want to encrypt entire disks, we use Bit Locker on Windows, File Vault on macOS, and one of many options on Linux.

In order for disk based encryption to work, we need some kind of key and some kind of lock. For this we **Trusted Platform Module (TPM)**, TPM is a chip that is soldered into the motherboard.
