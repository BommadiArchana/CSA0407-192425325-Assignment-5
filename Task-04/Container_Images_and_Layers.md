# Container Images and Layers

## Introduction

A container image is a read-only package that contains the files and dependencies required to run an application. Containers are created from these images.

## How a Container Image Is Built

A container image is commonly built using a Dockerfile. The Dockerfile contains instructions for preparing the application environment.

Example Dockerfile:

```dockerfile
FROM python:3.12-slim

WORKDIR /app

COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 8000

CMD ["python", "app.py"]
```

This example uses a Python base image, creates an application working directory, installs dependencies, copies application files and defines the startup command.

## Image Layers

A container image is built using multiple layers. Each instruction that changes the image can create a new layer.

Example layers:

1. Base image layer – Contains the Python runtime and basic operating-system files.
2. Working directory layer – Creates the application directory.
3. Dependency layer – Installs the required Python packages.
4. Application layer – Copies the application source code.
5. Configuration layer – Defines how the application starts.

## Advantages of Image Layers

- Layers can be reused by different images.
- Existing layers can be cached during builds.
- Rebuilding an image can be faster when earlier layers have not changed.
- Images can be stored and distributed through container registries.

## Application to the University Result Portal

The university can build a container image for the Python portal and use the same image in development, testing and production environments.

When application code changes, a new image can be built and deployed without manually installing all dependencies on each server.

## Conclusion

Container images package applications and dependencies into reusable layers. Layer caching and image reuse make application deployment and updates easier.
