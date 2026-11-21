# A1.3 – Linux File System and Permissions

## Introduction

The Linux file system organizes files and directories in a hierarchical structure. Linux permissions control who can read, write or execute files. These features help protect the university result portal and its student data.

## Linux Directory Hierarchy

Linux uses a single directory tree that begins with the root directory `/`.

Important directories include:

| Directory | Purpose |
|---|---|
| `/` | Root directory |
| `/bin` | Essential user commands |
| `/boot` | Boot-related files |
| `/dev` | Device files |
| `/etc` | System configuration files |
| `/home` | User home directories |
| `/var` | Logs and variable data |
| `/tmp` | Temporary files |
| `/usr` | Applications and shared files |
| `/opt` | Optional software packages |

## Virtual File System (VFS)

The Virtual File System is a Linux kernel layer that provides a common interface for accessing different file systems.

It allows applications to access files without needing to understand the internal implementation of each file-system type.

Examples include:

- ext4
- XFS
- Btrfs
- FAT

**Advantages of VFS:**

- Provides a common file-access interface.
- Supports different file-system types.
- Makes file management easier.
- Helps applications access files consistently.

## Linux Permission Model

Linux permissions are divided into three categories:

1. Owner – The user who owns the file.
2. Group – Users belonging to the file's group.
3. Others – All other users.

There are three basic permissions:

- Read (r): Allows reading the file.
- Write (w): Allows modifying the file.
- Execute (x): Allows executing a file or accessing a directory.

Example:

```bash
-rwxr-xr--
```

This means:

- Owner: Read, write and execute.
- Group: Read and execute.
- Others: Read only.

## Permission Commands

```bash
ls -l
chmod 755 file.sh
chown user1 file.txt
chgrp students file.txt
```

## Setuid

Setuid is a special permission that allows an executable file to run with the privileges of its file owner rather than the privileges of the user executing it.

It must be used carefully because incorrect use can create security risks.

## Sudo

The `sudo` command allows an authorized user to execute a command with elevated privileges.

Example:

```bash
sudo apt update
```

It helps administrators perform system-management operations without using the root account for every task.

## Application to the University Result Portal

The portal should use separate accounts for administrators, application services and database services. Student records and database files should only be accessible to authorized users.

The application should run with minimum required permissions. The `sudo` command should be restricted to authorized administrators.

## Conclusion

The Linux directory hierarchy, VFS and permission model provide organized file management and access control. These features help protect university records and improve server security.
