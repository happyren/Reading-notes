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

Most important abstractions of modern operating system. It allows virtual CPUs, and the making of pseudo concurrent operation.

It hides the effect of interrupts, it can be created and terminated dynamically with its own address space.

Within each process, there could be multiple threads of control, they are scheduled individually, having own stack, but sharing common address spaces.

Processes could be talking with each other through interprocess communication primitives.

## Memory Mangement

Main memory is where the program and its dependent files are stored while it is running. Ideally, each programmer would like the memory be private, infinitely large, infinitely fast, but its normally unreachable.

Instead, the memory hierarchy is developed to divide the memory by its speed vs size. And the **memory manager** is used to manage the memory hierarchy. Be aware, the memory is totally different thing against the disk. which is **File Management**.

The memeory management could vary against its design complication, it could be simple and doing **no swap or page**, this kind of system only allows one program running and taking the RAM, while others supports multiprogramming.

The next step is having **swap**, while the physical memory is not enough, the program or process is swapped to the disk, free spaces in RAM or on disk would be tracked using a bitmap or a hole list.

Then introducing **Virtual Memory**, the process' address space is splited into uniform-sized blocks called pages, which can be put into any available page frame in memory.

Finally, segmentation helps handle data structures that change size during execution and simplifies linking and sharing.

## File Systems

File system is requested to fill out the insufficient of memory:

1. Main memory size is limited.

2. Data is lost when process is terminated.

3. Frequently necessary for multiple process to access the information at the same time.

File can be seen as fixed-sized block accepting operations of: Reading and Writing the block.

File is actually an abstraction of the storage, it is an logical unit of information created by process. Information stored in a file must be persistant, without being affected by the creation or temination of processes.

---

From outside, a file system is a collection of files, directories, and operations on them. Files can be read, write, and executed; directories can be created or destroyed, files can be move among them, and subdirectory could be created.


From inside, a file system needs to concern how storage is allocated, how system keep track of the files, normal techniques includes:

- Contiguous File
- Linked List
- File Allocation Table
- i-nodes

and disk can be managed using free lists of bitmap.

To ensure the reliability of the file system, increamental dump and file system repair program are normally implemented; to enhance the performance, caching, read ahead, placing block of files close to each other are general techniques.

Different file systems are used by different systems: ISO9660 (ISO image), MS-DOS (FAT-32), UNIX (Unix File System)
## I/O

## Multiple Processor System
