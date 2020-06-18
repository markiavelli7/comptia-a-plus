# What is the Registry?

The primary database for every Windows system

Inside every operating system, there has to be some place to keep settings. The **Registry** stores Windows settings.

Linux stores these settings in text files.

The Windows Registry is a binary file that can only be used by a particular program called the **Registry Editor (regedit.exe)**.

## Registry Editor

Organizes the Registry into 5 Root Keys

**HKEY_CLASSES_ROOT** - rarely go into this one. Deals with file types, who will open it, etc.

**HKEY_LOCAL_MACHINE** - defines all of the settings for the computer. Drivers, hardware, software, how Windows is configured, etc.

**HKEY_CURRENT_CONFIG** - what software/settings are being used right now. HKEY_CURRENT_CONFIG is a subset of HKEY_LOCAL_MACHINE.

**HKEY_USERS** - lists all of the current users that are on the computer

**HKEY_CURRENT_USER** - is a subset of HKEY_USERS, takes the current user and displays their preferences/settings.

The big thing that we do with the Registry is add values.

**Whenever we edit the Registry, it is important to export a backup before we make changes**

# Processes

Task Manager lets us kill errant processes

**Applications** - things that we can see and access

**Services** - running in the background

When we combine applications and services together, we get processes

A process is a program that is actually running and taking up memory. Windows has to manage these hundreds of processes

Each running program has a **Process ID (PID)**.

**End Process Tree** - Dynamic Link Libraries (dll) or Executable Files (exe) files store additional information that add functionality to programs. A process tree is where programs depend on each other (dependency hierarchy)

**Process Explorer** - lets us see the dependency trees

# Services

Processes that run without an interface

Typical Windows systems have many services running

Microsoft **Services** manages the many services that are on our computer.

Services can be manually or automatically turned on.

# Windows Toolset

**Right Click** to view a context menu, and in most times select **Properties**.

**Control Panel** can help find almost anything that we need.

**Administrative Tools** from the Control Panel menu contains a lot of important settings

**System Configuration** from Administrative tools lets us adjust General, Boot, Services, Startup, and Tools settings.

**Settings** has a lot of overlap with Control Panel

# Windows 7 Task Manager

ctrl - alt - delete

ctrl - shift - esc

Windows 7 Task Manager is split out into Applications, Processes, Services, Performance, Networking, and Users

Resource Monitor was added to Task Manager in Windows 7 and includes CPU, Disk, Network, and Memory Data

If Task Manager couldn't tell us what we needed to know, **Resource Monitor** gives us a more granular view.

When a program is running in memory, it is a process that is taking up a certain amount of memory. This memory is allocated into something called **Pages**. If a program is running and needs to load another Page and can't find it in RAM, so has to go to the Hard Drive, that is a **Hard Fault**. If we start seeing 100 Hard Faults per second and the computer is running slow, **we don't have enough RAM**.

# Windows 10 Task Manager

Ctrl - Alt -Delete, Ctrl - Shift - Esc, and right-clicking on the Windows icon in the taskbar will all get you to the Task Manager in Windows 10

Background processes are services

Windows 10 Task Manager is split out into Processes, Performance, App History, Startup, Users, Details, and Services

# Information and Configuration Tools

**System Information (msinfo32)** - Very old information tool

**System Configuration (msconfig)** - General, Boot, Services, Tools, Startup. System Configuration is very helpful for troubleshooting. If we think we have problems with Drivers or Services, we can disable items to pinpoint problem areas. **Active Directory Repair** will attempt to repair and reconnect to the server, assuming that we have a good network connection.

**System** lists the Windows edition, System properties, computer name and domain settings, and Windows activation status

**Microsoft Management Console (MMC)** lets us create our own utilities

# Performance Monitor

If we want a performance baseline, we are going to use Performance Monitor and set up counters

We have to decide how we are going to run this, **realtime** or **scheduled**.

**Data Collector Sets** lets us track performance over time. DCS is nothing more than a pile of individual counters that we put together for our own needs.

# Event Viewer

Event Viewer logs thousands of activities that take place on a Windows system

There are four different types of logs: Application, Security, Setup, and System

We can add events to log using Local Security Policy

# Tools for Programmers

Windows has two tools to support applications

The Open Database Connectivity (ODBC) tool lets a Windows system locate shared databases

The Component Services utility enables users to edit Component Object Model features
