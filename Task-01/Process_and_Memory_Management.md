# A1.2 – Process and Memory Management in Linux

## Introduction

Linux uses process scheduling and memory-management techniques to improve system performance. These techniques help the university result portal handle multiple student requests efficiently.

## Completely Fair Scheduler (CFS)

The Completely Fair Scheduler (CFS) is a Linux CPU scheduling mechanism designed to distribute CPU time fairly among runnable processes.

It uses virtual runtime (vruntime) to track the amount of CPU time received by each process. A process with a smaller virtual runtime is generally selected earlier.

**Advantages:**

- Provides fair CPU-time distribution.
- Supports multiple running processes.
- Helps prevent one normal process from continuously occupying the CPU.
- Improves system responsiveness.

**Limitations:**

- CPU-intensive processes can still consume significant resources.
- Heavy system load can increase response time.
- Fair CPU scheduling alone cannot guarantee that the result portal will meet every response-time requirement.

**Evaluation:** CFS is useful for the result portal because it allows web-server processes, database processes and background tasks to share CPU resources.

## Page Cache

The Linux page cache stores recently accessed file data in RAM. When a file is requested again, Linux may read it from memory instead of accessing the disk.

**Advantages:**

- Reduces repeated disk access.
- Improves file-reading performance.
- Helps database and web-server operations.

**Limitation:** Cached data uses available RAM, so memory pressure may require Linux to reclaim cache pages.

## Swapping

Swapping is a memory-management technique in which Linux moves less-active memory pages from RAM to swap space.

**Advantages:**

- Helps the system continue operating when RAM is under pressure.
- Provides additional virtual memory capacity.

**Limitations:**

- Disk access is slower than RAM access.
- Excessive swapping can reduce application performance.
- It should not be treated as a replacement for sufficient physical memory.

**Evaluation:** The university should provide enough RAM for the web application and database. Swapping should be monitored to identify memory pressure.

## /proc File System

The `/proc` file system provides information about running processes and kernel activity.

Useful examples:

- `/proc/cpuinfo` – CPU information.
- `/proc/meminfo` – Memory information.
- `/proc/loadavg` – System load information.
- `/proc/<PID>/` – Information about a particular process.

## /sys File System

The `/sys` file system provides information about devices, drivers and kernel subsystems.

It helps administrators inspect hardware and device information.

## Commands for Observing the System

```bash
ps aux
free -h
top
cat /proc/meminfo
cat /proc/cpuinfo
cat /proc/loadavg
ls /sys
```

## Evaluation for the Result Portal

CFS helps distribute CPU time among processes. The page cache improves file access, while swapping provides additional memory support when required. The `/proc` and `/sys` file systems help administrators monitor system conditions.

These features help identify CPU, memory and device-related performance problems before they affect students accessing their results.

## Conclusion

Linux process and memory-management features help maintain system performance. Regular monitoring of CPU usage, RAM and swapping is important for handling high traffic on result day.
