# CPU Memory Limits and Docker Stats

## Aim
To limit the CPU and memory resources of the result portal container and observe its resource usage using Docker Stats.

## Software Required
- Docker
- Ubuntu Linux
- Result Portal Docker Image

## Procedure

### Step 1: Build the Docker Image

```bash
docker build -t result-portal .
```

### Step 2: Run the Container with Resource Limits

```bash
docker run -d --name result-portal --cpus="0.5" --memory="512m" -p 8000:8000 result-portal
```

### Step 3: Check Running Containers

```bash
docker ps
```

### Step 4: Monitor Resource Usage

```bash
docker stats result-portal
```

### Step 5: Stop the Container

```bash
docker stop result-portal
```

## Explanation

The --cpus option limits the container to 0.5 CPU. The --memory option restricts its memory usage to 512 MB. The docker stats command displays CPU usage, memory usage, network activity and block I/O.

## Result

CPU and memory limits are applied to the result portal container. Docker Stats is used to monitor its resource consumption.
