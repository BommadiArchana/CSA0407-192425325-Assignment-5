# B1.1 – Observe the Linux Server

## Aim

To observe Linux server processes, CPU usage, memory usage, disk usage and network connections using Linux monitoring commands.

## Software Required

- Linux operating system or Linux virtual machine.
- Terminal.
- Monitoring utilities such as procps and sysstat.

## Commands Used

### Process Monitoring

```bash
ps aux
```

This command displays running processes, their users, CPU usage and memory usage.

### CPU Monitoring

```bash
top
```

This command displays active processes and real-time CPU and memory usage.

### Memory Monitoring

```bash
free -h
```

This command displays total, used, free and available memory, along with swap information.

### Virtual Memory Monitoring

```bash
vmstat 1 5
```

This command displays process, memory, swap, CPU and system activity at one-second intervals for five reports.

### Disk I/O Monitoring

```bash
iostat -xz 1 3
```

This command displays CPU and storage-device I/O statistics. It requires the `sysstat` package.

### Disk Space Monitoring

```bash
df -h
```

This command displays file-system size, used space, available space and usage percentage.

### Network Monitoring

```bash
ss -tulnp
```

This command displays listening TCP and UDP sockets and associated process information where permissions allow.

## Procedure

1. Start the Linux system.
2. Open the terminal.
3. Execute each monitoring command.
4. Observe the displayed system information.
5. Save the command outputs in `system_monitoring.txt`.
6. Explain the values observed.

## Observation Table

| Command | Information Observed |
|---|---|
| ps aux | Running processes |
| top | CPU and memory usage |
| free -h | RAM and swap usage |
| vmstat | Process, memory and CPU statistics |
| iostat | Disk I/O activity |
| df -h | Disk-space usage |
| ss -tulnp | Network listening ports |

## Result

The Linux monitoring commands were used to inspect the server's processes, CPU, memory, disk and network activity. The actual outputs are saved in `system_monitoring.txt` after execution.
