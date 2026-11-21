# Performance Measurement

## Aim
To measure and compare the performance of the same web application running on bare metal, a virtual machine and a Docker container.

## Parameters Measured
- Start-up time
- Memory used
- Image or disk size
- Requests per second

## Software Required
- Linux
- Docker
- VirtualBox
- Apache Benchmark (ab)

## Procedure

### 1. Install Apache Benchmark

```bash
sudo apt update
sudo apt install apache2-utils -y
```

### 2. Measure Requests per Second

Run the following command against each deployment separately:

```bash
ab -n 1000 -c 50 http://localhost:8000/
```

Record the Requests per second value shown in the output.

### 3. Measure Memory Usage

For Linux and the virtual machine:

```bash
free -h
ps aux | grep gunicorn
```

For Docker:

```bash
docker stats result-portal
```

### 4. Measure Disk or Image Size

For Docker:

```bash
docker images result-portal
```

For a virtual machine, check the virtual disk file size.

For bare metal, record the disk space used by the application and its required dependencies.

### 5. Record Start-up Time

Measure the time from starting each deployment until the application becomes ready to accept requests. Use the same method for all three deployments.

## Observation
The performance measurements are recorded in performance_results.txt.

## Result
The performance of bare metal, virtual machine and Docker deployments is measured using start-up time, memory usage, disk or image size and requests per second.
