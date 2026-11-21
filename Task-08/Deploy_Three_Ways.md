# Deploy the Web Application in Three Ways

## Aim
To deploy the same university result portal web application directly on Linux, inside a virtual machine and inside a Docker container.

## Software Required
- Ubuntu Linux
- Python 3
- Flask
- Oracle VirtualBox
- Docker

## 1. Bare Metal Deployment

In this method, the web application runs directly on the Linux operating system without using a virtual machine or container.

**Commands:**

```bash
sudo apt update
sudo apt install python3 python3-pip -y
pip3 install flask gunicorn
cd result-portal
gunicorn --bind 0.0.0.0:8000 app:app
```

Open the browser and enter:

`http://localhost:8000`

## 2. Virtual Machine Deployment

In this method, the web application runs inside an Ubuntu virtual machine created using Oracle VirtualBox.

**Procedure:**

1. Open Oracle VirtualBox.
2. Create a new Ubuntu virtual machine.
3. Allocate CPU, RAM and disk space.
4. Install Python and Flask inside the virtual machine.
5. Copy the result portal application into the virtual machine.
6. Start the application using the following command:

```bash
gunicorn --bind 0.0.0.0:8000 app:app
```

Open the application using the virtual machine IP address and port 8000.

## 3. Docker Container Deployment

In this method, the application runs inside a Docker container.

**Commands:**

```bash
docker build -t result-portal .
docker run -d --name result-portal -p 8000:8000 result-portal
docker ps
```

Open the browser and enter:

`http://localhost:8000`

## Observation

The same web application is deployed using three different methods:

- Bare Metal – runs directly on Linux.
- Virtual Machine – runs inside a separate guest operating system.
- Docker Container – runs in an isolated container sharing the host Linux kernel.

## Result

The university result portal application was deployed using bare metal, a virtual machine and a Docker container. These deployment methods are ready for performance measurement and comparison.
