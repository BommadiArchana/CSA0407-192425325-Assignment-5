# B1.2 – Disk-Space Alert

## Aim

To create a shell script that checks Linux disk usage and displays an alert when usage reaches a specified limit.

## Introduction

Disk-space monitoring is important for the university result portal because log files, application files and database backups consume storage space.

If disk usage becomes too high, the server may not be able to store new files or logs.

## Script Description

The `disk_alert.sh` script:

- Checks the disk usage of the root file system.
- Compares the usage with a configured threshold.
- Displays a warning if the threshold is reached.
- Displays a normal status if disk usage is below the threshold.

## Procedure

1. Create the `disk_alert.sh` file.
2. Set the required execution permission.
3. Run the script.
4. Observe the disk usage percentage and message.
5. Save the actual output in `disk_alert_output.txt`.

## Result

The disk-space alert script checks storage usage and displays a warning when the configured threshold is reached.
