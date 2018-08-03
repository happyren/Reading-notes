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

Entire OS run as a single program in kernel mode.

\* No information hiding between procedures.

Basic Structs:

1. Main program call service procedure.

2. Service procedures respond to calls.

3. Utility procedures supports services procedures.

#### Layered Systems

OS is organized as a hierarchy of layers, each one constructed upon the one below it.

#### Microkernels

Still layered systems, but some process may not be included into kernel mode, so that the bugs in these process would not be fatal and bring down the system instantly.

#### Client-Server Model

Server provides services, and clients use them.

#### VM

A derivation that allows multiple users working interactively at a terminal. (Timesharing System)

Further, virtualization can serve as a way to run multiple service in different OS but on the same hardware.

Type 1 hypervisor is not good for the PC, most VM we are seeing running on PCs are using type 2 hypervisor.

There is a hosting to run the hybervisor then run the guest system.

#### Exokernels

Giving each user a subset of system resources.

### How OS are written

OS are mostly written in C and C++.

C has pointer, but does not have strings, threads, packages, classes, objects, type safety, and garbage collection.

C has storage either static or explicitly alocated and released by the programmer, that os why it is so attractive for programming an OS. Garbage collector consume too much time.

*.h* and *.c* files are for C program to know what are the functions to be called, and how are they defined.

*make* is a program that check what are needed, and what are changed, incrementally calling preprocessor and compiler to build the program.

C preprocessor would expand dependent files and pass them to the compiler.

After all *.o* files are ready, they are passed to the linker to be bind together and form a program could be executed.

## Processes

## Memory Mangement

## File Systems

## I/O

## Deadlocks

## Multiple Processor System
