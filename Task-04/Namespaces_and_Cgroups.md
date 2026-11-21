# Linux Namespaces and Control Groups (cgroups)

## Introduction

Linux containers use namespaces and control groups to provide isolation and resource management. These features allow multiple containers to run independently on the same Linux system.

## Linux Namespaces

Namespaces provide isolation between processes running in different containers. They control which system resources a process can see.

Important namespace types include:

| Namespace | Purpose |
|---|---|
| PID | Isolates process IDs |
| Network | Isolates network interfaces and network settings |
| Mount | Provides separate file-system mount views |
| UTS | Isolates hostname and domain-name information |
| IPC | Isolates inter-process communication resources |
| User | Isolates user and group ID mappings |
| Cgroup | Isolates the view of control-group information |

For example, the portal container can have its own process view and network configuration. This helps separate it from other containers.

## Control Groups (cgroups)

Control groups manage and limit the resources used by processes or groups of processes.

They can control:

- CPU usage.
- Memory usage.
- Disk I/O usage.
- Number of processes.

For example, the university can set a memory limit for the Python portal container so that it does not consume all available server memory.

## Difference Between Namespaces and cgroups

| Factor | Namespaces | cgroups |
|---|---|---|
| Main purpose | Resource isolation | Resource control |
| Function | Controls what a process can see | Controls how much resource it can use |
| Examples | Process, network and mount isolation | CPU, memory and I/O limits |
| Benefit | Separates container environments | Prevents excessive resource consumption |

## Application to the University Result Portal

Namespaces separate the portal and database container environments. Control groups help limit CPU and memory usage so that one service does not consume all server resources.

## Conclusion

Namespaces provide isolation, while cgroups manage resource usage. Together, they help Linux run multiple containers safely and efficiently.
