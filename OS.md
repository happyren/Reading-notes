# Operating System

> This is a reading notes based on the book *Modern Operating Systems*.

## Introduction

Modern operating system plays important roles in almost all industry and everyday life. Knowing operating system to a rather detailed level is important for penetration testing.

### What is operating system

Operating system is **software**, a special one in the modern computer architecture, it serves as a kernel program.

It has two major functions:

1. It abstract the service of machine language level instruction set, and transform them into a neater abstracted st of calls.

2. It manages the system resources such as processors, memory, and I/O, orderlly control the allocation of them among the competing programs.

---

OS could be classified by different application scenarios, however, for modern OS, mostly we are talking about:

1. Server OS: Linux and Windows

2. PC OS: Linux, OS X, Windows

3. PDA OS: Android, IOS

4. Embedded OS: Android, ARM

5. Sensor OS: Tiny OS

---

### OS concepts

####  Process

Basically a program in execution, each would have **address space** for it to read and write.

A Process holds all the information needs to run a program.

#### Address Spaces

Address space is in terms of a process. For system allows multiple programs to work in the memory, it would allow address space to each program's process, and they cannot be larger than main memory for there are spaces reserved for the operating system.

#### Files

File system are design to grouping files together, every file would be having a **path name** from top to bottom, and each process has a currently **working directory**.

**Mounting** is a unique process to the UNIX based OS, the external (or second) file system must be mounted to the empty directory of the root directory to be accessible.

#### I/O

Including usb devices, bluetooth devices, proprietary ports, wireless and ethernet, they are all I/Os for user to input and observe output, despite they all hardwares, they are very likely being managed by OS when different process competing for the usage of them.

#### Protection

POSIX access control, and firewalls.

#### Shell

Unix command interpreter, original shell is (**sh**), with GUI as a program running on top of the command line.

#### Virtual Memory

Resolving the program which has greater demand on RAM than physical RAM available, OS would move back and forth the files that process operating on between RAM and Disk.

---

### OS Structure

#### Monolithic Systems


