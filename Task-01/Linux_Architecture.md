# A1.1 – Linux Architecture

## Introduction

Linux is an open-source operating system widely used in servers, cloud platforms and embedded systems. It provides a stable environment for running applications and managing computer hardware. The Linux operating system consists of the kernel, system libraries, shell and system utilities.

## Linux Kernel

The Linux kernel is the core component of the operating system. It acts as an interface between application software and computer hardware.

The main responsibilities of the Linux kernel are:

- Process management: Creates, schedules and terminates processes.
- Memory management: Allocates and releases memory for running applications.
- File management: Controls access to files and directories.
- Device management: Communicates with hardware devices through device drivers.
- Network management: Handles network communication and data transfer.

## System Libraries

System libraries provide standard functions that applications use to communicate with the Linux kernel. They reduce the need for applications to directly communicate with hardware.

For example, the GNU C Library (glibc) provides functions for file operations, memory allocation and process management.

## Shell

The shell is a command interpreter that allows users to interact with the operating system. Users can enter commands to perform operations such as creating files, managing directories and executing programs.

Examples of Linux shells include:

- Bash
- Zsh
- Fish

## System Utilities

System utilities are tools used to perform administrative and general operating system tasks.

Examples:

- ls – Lists files and directories.
- mkdir – Creates directories.
- cp – Copies files.
- mv – Moves or renames files.
- ps – Displays running processes.
- df – Displays disk-space usage.
- systemctl – Manages system services.

## How the Kernel Manages System Resources

**Process Management:** The kernel creates processes, assigns CPU time and manages process execution. It uses scheduling algorithms to decide which process receives CPU time.

**Memory Management:** The kernel allocates memory to processes and manages physical memory and virtual memory. It also uses swapping when memory becomes insufficient.

**File Management:** The kernel manages files, directories and file permissions through the Linux file system and Virtual File System.

**Device Management:** Device drivers allow the kernel to communicate with hardware components such as keyboards, storage devices and network cards.

**Network Management:** The kernel manages network interfaces, IP communication, routing and data transmission.

## Evaluation for the University Result Portal

Linux is suitable for the university result portal because it supports multiple users, efficient resource management, networking services and automation. Its open-source nature reduces operating system licensing costs. It also supports web servers, databases, Docker and Kubernetes.

## Conclusion

Linux provides an efficient operating environment through its kernel, system libraries, shell and utilities. Its resource-management capabilities make it suitable for hosting the university result portal.
