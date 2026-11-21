# Resource Limits

## Aim
To configure and verify separate CPU and memory limits for the result portal and learning management system.

## Resource Configuration

| Service | CPU Limit | Memory Limit |
|---|---:|---:|
| Result Portal | 0.50 CPU | 512 MB |
| LMS | 0.25 CPU | 256 MB |

## Commands
```bash
docker compose ps
docker stats
docker inspect result-portal
docker inspect learning-management-system
```

## Explanation
The CPU limit controls the maximum CPU resources available to each container. The memory limit restricts the amount of RAM each container can use. The `docker stats` command displays the current resource usage.

## Result
Both services are configured with separate CPU and memory limits. Their running status and resource usage can be checked using Docker commands.
