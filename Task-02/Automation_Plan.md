# A2.3 – Automation Using Shell Scripts and Cron

## Introduction

Automation reduces repetitive administrative work and helps maintain the university result portal. Linux provides shell scripts and cron for scheduling routine tasks.

## Tasks to Be Automated

### 1. Database Backup

Database backups should be performed regularly to protect student result information.

The backup process should:

- Create a database backup.
- Store it in a protected backup directory.
- Add the date to the backup filename.
- Retain backups according to the university backup policy.
- Copy backups to a separate storage location.

Example backup filename:

`result_backup_2026-11-21.sql`

### 2. Log Rotation

Log files grow over time and may consume disk space. Log rotation manages old log files by rotating, compressing and removing them according to a retention policy.

Linux provides the `logrotate` utility for this purpose.

Example command:

```bash
sudo logrotate -d /etc/logrotate.conf
```

The `-d` option displays what logrotate would do without actually performing the rotation.

### 3. Disk-Space Alerts

A shell script can check available disk space and generate an alert when usage exceeds a defined limit.

Example command:

```bash
df -h
```

The administrator can use this information to identify partitions that are running out of space.

### 4. Service Monitoring

Scripts can check whether important services are running.

Example commands:

```bash
systemctl is-active nginx
systemctl is-active portal
```

If a required service is inactive, the administrator can receive an alert and investigate the problem.

## Scheduling with Cron

Cron is a Linux utility used to execute commands or scripts automatically at scheduled times.

Example cron entries:

```cron
0 2 * * * /opt/scripts/database_backup.sh
0 * * * * /opt/scripts/log_analysis.sh
*/30 * * * * /opt/scripts/disk_alert.sh
```

Explanation:

- The first entry runs the database backup daily at 2:00 AM.
- The second entry runs log analysis every hour.
- The third entry checks disk usage every 30 minutes.

The scripts must be created, tested and given the correct execution permissions before scheduling them.

## Evaluation for the University Result Portal

Automated backups protect important student records. Log rotation controls disk usage, and disk alerts help administrators identify storage problems. Service monitoring helps detect application failures.

Automation reduces manual work and supports regular server maintenance.

## Conclusion

Shell scripts and cron can automate backups, log management, disk monitoring and service checks. These tasks help maintain the availability and reliability of the university result portal.
