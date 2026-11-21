# A2.1 – Users, Services and Logs

## Introduction

System administration is important for maintaining the university result portal. The portal must support students, administrators and application services. Proper user accounts, system services and log monitoring help maintain security and availability.

## User Accounts and Groups

Separate user accounts and groups should be created to control access to the server.

Proposed user accounts:

| User account | Purpose |
|---|---|
| admin | Manages the Linux server |
| portal | Runs the Python web application |
| dbadmin | Manages database administration |
| monitor | Performs monitoring tasks |

Proposed groups:

| Group | Members or purpose |
|---|---|
| admins | Authorized system administrators |
| webteam | Users who maintain the portal application |
| dbteam | Authorized database administrators |
| monitoring | Users responsible for monitoring |

The portal application should run using the `portal` account instead of the root account. This reduces the risk of unauthorized access to system files.

Example commands:

```bash
sudo groupadd admins
sudo groupadd webteam
sudo groupadd dbteam
sudo groupadd monitoring

sudo useradd -m admin
sudo useradd -m portal
sudo useradd -m dbadmin
sudo useradd -m monitor

sudo usermod -aG admins admin
sudo usermod -aG webteam portal
sudo usermod -aG dbteam dbadmin
sudo usermod -aG monitoring monitor
```

These commands are proposed examples. The accounts and groups should be created according to the university's actual access policy.

## systemd Services

systemd is the service manager used by many Linux distributions. It starts, stops and monitors system services.

The university result portal can use the following services:

| Service | Purpose |
|---|---|
| portal.service | Runs the Python web application |
| nginx.service | Handles incoming HTTP and HTTPS requests |
| database.service | Runs the selected database service |
| ssh.service | Provides secure remote administration |

The Python application should run as the `portal` user. It should start automatically when the server boots and restart if the application fails.

Example systemd service design:

```ini
[Unit]
Description=University Result Portal
After=network.target

[Service]
User=portal
Group=webteam
WorkingDirectory=/opt/result-portal
ExecStart=/opt/result-portal/venv/bin/gunicorn --workers 4 --bind 127.0.0.1:8000 app:app
Restart=on-failure

[Install]
WantedBy=multi-user.target
```

The application command and paths must match the actual application installation.

## Log Monitoring

Logs record system events, application activity and errors. They help administrators identify problems and investigate failures.

Important log locations:

- `/var/log/syslog` – General system messages on distributions that use this file.
- `/var/log/auth.log` – Authentication and login events on Debian-based systems.
- `/var/log/nginx/` – Nginx access and error logs.
- `journalctl` – Displays systemd journal entries.

Useful commands:

```bash
sudo journalctl -u nginx
sudo journalctl -u portal
sudo journalctl -p err
sudo tail -f /var/log/nginx/access.log
sudo tail -f /var/log/nginx/error.log
```

The administrator should monitor failed login attempts, application errors, database failures, service restarts and unusual traffic.

## Evaluation for the University Result Portal

Separate accounts reduce unauthorized access. systemd helps restart failed application services. Log monitoring helps administrators identify errors before they affect a large number of students.

## Conclusion

A proper user and group structure, systemd service management and log monitoring provide a secure and manageable Linux server environment for the university result portal.
