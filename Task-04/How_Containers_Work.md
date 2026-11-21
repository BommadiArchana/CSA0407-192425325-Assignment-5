# A4.1 – How Containers Work

## Introduction

Containerisation is a technology used to package an application and its required dependencies into a container. Containers allow applications to run in a consistent environment across different systems.

For the university result portal, the Python application can be packaged into a container so that it can be deployed easily on a Linux server or cloud platform.

## What Is a Container?

A container is an isolated environment that runs an application using the host operating system's kernel.

A container includes:

- Application code.
- Required libraries.
- Runtime environment.
- Application dependencies.
- Configuration files.

Unlike a virtual machine, a container does not normally require a separate guest operating system.

## How Containers Work

1. The developer creates an application and its dependencies.
2. A container image is built using a Dockerfile.
3. The container engine uses the image to create a container.
4. The container runs the application in an isolated environment.
5. The container uses the host operating system kernel.

## Container Architecture

The container environment contains the following components:

- Host operating system: Provides the Linux kernel.
- Container engine: Creates and manages containers.
- Container image: Contains the application and dependencies.
- Container: Runs the application using the image.

## Application to the University Result Portal

The Python result portal can run inside a container. The database can run in a separate container so that both services can be managed independently.

This makes deployment and application updates easier.

## Advantages

- Consistent application environment.
- Easy deployment.
- Faster startup compared with many full virtual machines.
- Efficient resource usage.
- Easy application updates and scaling.

## Conclusion

Containers package applications and their dependencies into portable environments. They help the university deploy and manage the result portal efficiently.
