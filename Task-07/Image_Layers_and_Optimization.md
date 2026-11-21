# Image Layers and Optimization

## Aim
To inspect Docker image layers using the docker history command and reduce the Docker image size using a slim base image.

## Software Required
- Docker
- Ubuntu Linux
- Dockerfile
- Result Portal application

## Procedure

### Step 1: Build the Docker Image

```bash
docker build -t result-portal .
```

### Step 2: View Docker Image Layers

```bash
docker history result-portal
```

The command displays the image layers, their sizes and the instructions used to create them.

### Step 3: Check Docker Image Size

```bash
docker images result-portal
```

Record the image size in docker_images_output.txt.

### Step 4: Optimize the Image

Use a lightweight Python base image in the Dockerfile:

```dockerfile
FROM python:3.12-slim
```

Install only the required dependencies:

```dockerfile
RUN pip install --no-cache-dir -r requirements.txt
```

Copy the application files into the image and avoid installing unnecessary packages.

### Step 5: Rebuild and Compare

```bash
docker build -t result-portal .
docker history result-portal
docker images result-portal
```

Compare the image size before and after optimization.

## Explanation

Docker images are created using multiple layers. Each Dockerfile instruction can create a layer. The docker history command displays these layers and their sizes.

A slim base image contains fewer unnecessary packages than a full operating system image. This can reduce image size, image transfer time and the number of installed packages.

## Result

Docker image layers are inspected using docker history. The image is optimized using the Python slim base image, and its size is checked using docker images.
