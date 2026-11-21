# CSA0407-192425325-Assignment-5

# LINUX, CONTAINERS AND VIRTUALISATION FOR EFFICIENT OPERATIONS

# AIM

To analyse Linux operating systems, system administration, virtualisation, containerisation, cloud deployment and orchestration to improve system performance, resource utilisation, scalability and failure recovery.

# CASE STUDY

The university publishes semester results through a web portal. The portal is a Python web application connected to a database. Normally, it handles a few hundred users per day, but approximately 150,000 students access the portal within two hours on result day.

The existing portal runs on a single physical Linux server that experiences failures during result day. The university has a small private server room and an account with a public cloud provider.

This assignment evaluates suitable Linux, virtualisation, containerisation and cloud technologies for improving the portal's performance and availability.

# SOFTWARE AND TOOLS REQUIRED

- Linux Ubuntu
- GCC Compiler
- Python 3
- Docker
- Docker Compose
- Kubernetes
- Minikube or Kind
- Oracle VirtualBox
- Nginx
- Git and GitHub
- Bash Shell

---

# TASK 01 – EVALUATE THE LINUX SYSTEM COMPONENTS (7 MARKS)

## Aim

To study and evaluate Linux architecture, process management, memory management, file systems and permissions.

## A1.1 – Linux Architecture

Linux architecture consists of the kernel, system libraries, shell and utilities. The kernel manages processes, memory, files, devices and network communication.

## A1.2 – Process and Memory Management

The Completely Fair Scheduler (CFS) manages CPU scheduling. The page cache improves file access performance, while swapping provides additional memory support. The /proc and /sys file systems provide information about processes, system resources and hardware.

## A1.3 – Linux File System and Permissions

Linux uses a hierarchical directory structure. The Virtual File System provides a common interface for different file systems. Permissions are assigned to owners, groups and others. Setuid and sudo provide controlled privilege management.

## Alternative Concept – Windows Server

Windows Server can also host the university portal. Its base memory and disk requirements, administration automation time and licence cost per server must be evaluated against Linux.

## Result

Linux architecture, process and memory management, file systems and permissions are studied and evaluated for the university result portal.

---

# TASK 02 – DESIGN THE SYSTEM ADMINISTRATION (5 MARKS)

## Aim

To design user accounts, services, logs, networking and automation for the university result portal server.

## A2.1 – Users, Services and Logs

Create separate user accounts and groups for administration and application access. Use systemd to manage portal services and monitor system logs.

## A2.2 – Networking Services

Configure IP addressing, DNS, Nginx reverse proxy, firewall rules and SSH key-based access.

## A2.3 – Automation

Automate routine administration tasks such as backups, log rotation and disk-space alerts using shell scripts and cron.

## Alternative Concept – Ansible

Ansible can automate server configuration. It helps maintain consistent settings across multiple servers and reduces manual administration effort.

## Result

A Linux server administration design is prepared with user management, systemd services, networking, firewall security and automation.

---

# TASK 03 – EVALUATE VIRTUALISATION (5 MARKS)

## Aim

To study hypervisors, virtualisation techniques, benefits and costs of virtual machines.

## A3.1 – Hypervisors

A Type-1 hypervisor runs directly on physical hardware. Examples include KVM, VMware ESXi, Xen and Hyper-V.

A Type-2 hypervisor runs on a host operating system. Examples include VirtualBox and VMware Workstation.

Full virtualisation provides a complete virtual hardware environment. Para-virtualisation allows the guest operating system to cooperate with the hypervisor.

Intel VT-x and AMD-V provide hardware support for virtualisation.

## A3.2 – Benefits and Costs

Virtual machines provide isolation, server consolidation, snapshots and live migration. Their costs include CPU overhead, memory consumption and software licences.

## Alternative Concept – Type-2 Hypervisor

VirtualBox can be used instead of a Type-1 hypervisor. However, the host operating system consumes additional memory, and CPU-bound and I/O-bound workloads may experience additional overhead.

## Result

Type-1 and Type-2 hypervisors, virtualisation techniques, benefits and costs are evaluated for the university server environment.

---

# TASK 04 – EVALUATE CONTAINERISATION (4 MARKS)

## Aim

To understand how containers work and compare containers with virtual machines.

## A4.1 – How Containers Work

Containers use Linux namespaces to isolate processes, networks and file systems. Control groups (cgroups) manage CPU and memory resources. Docker images are built using multiple layers.

## A4.2 – Containers versus Virtual Machines

Containers share the host operating system kernel and generally require fewer resources. Virtual machines run separate guest operating systems and provide stronger operating-system-level isolation.

| Feature | Containers | Virtual Machines |
|---|---|---|
| Start-up time | Usually faster | Usually slower |
| Memory usage | Generally lower | Generally higher |
| Isolation | Process-level | Guest OS-level |
| Portability | Container images | VM images |
| Resource usage | Generally efficient | Requires guest OS resources |

## Alternative Concept – Separate Virtual Machines

The portal and database could run in separate virtual machines. This provides separate guest operating systems but increases memory requirements and start-up time.

## Result

Container architecture, namespaces, cgroups, image layers and the differences between containers and virtual machines are evaluated.

---

# TASK 05 – DESIGN THE CLOUD DEPLOYMENT AND ORCHESTRATION (4 MARKS)

## Aim

To design a cloud deployment architecture and understand how Kubernetes manages application deployment, scaling and recovery.

## A5.1 – Cloud Set-up

Cloud computing provides three main service models:

- IaaS – Infrastructure as a Service.
- PaaS – Platform as a Service.
- SaaS – Software as a Service.

For the university result portal, the cloud architecture can use virtual machines or managed Kubernetes, a load balancer and a managed database.

## A5.2 – Kubernetes

Kubernetes uses pods, deployments, services and replicas to manage applications. Resource requests and limits control resource allocation. Horizontal Pod Autoscaler adjusts the number of pods according to workload.

## Alternative Concept – Fixed Virtual Machines

Fixed virtual machines can be configured to handle result-day traffic. However, additional resources may remain unused during the other 364 days, increasing operational costs.

## Result

A cloud deployment design is prepared, and Kubernetes features for application scaling and failure recovery are evaluated.

---

# TASK 06 – ADMINISTER THE LINUX SERVER (7 MARKS)

## Aim

To monitor Linux system resources, automate administration tasks and configure web services and network security.

## B1.1 – Observe the System

Use Linux commands to monitor processes, memory, disk and network resources.

```bash
ps
top
free -h
vmstat
iostat
df -h
ss -tuln
```

## B1.2 – Automate

Create shell scripts for web-server log analysis and disk-space alerts. Schedule the scripts using cron.

## B1.3 – Services and Network

Run the portal or sample web application as a systemd service behind Nginx. Configure the firewall to allow HTTP, HTTPS and SSH.

## B1.4 – Compare with Your Design

Compare the implemented server configuration with the administration design prepared in Task 02.

## Complete the Code

Complete TODO 1 and TODO 2 in the given Bash script using awk, sort and uniq. Display requests per status code, the busiest client and total bytes sent.

Expected output:

```text
Requests per status code:
200 4
302 1
403 1
404 1

Busiest client:
10.0.0.5 4

Total bytes sent: 43200
```

Schedule the script with cron to run every hour.

## Alternative Concept – Central Log System

Central logging systems such as journald with a log server or ELK can collect and analyse logs from multiple servers. They require additional storage, memory and configuration effort.

## Result

Linux system monitoring, log analysis, disk alerts, cron scheduling, web services and firewall configuration are implemented and evaluated.

---

# TASK 07 – CONTAINERISE THE PORTAL (5 MARKS)

## Aim

To containerise the university result portal using Docker, configure database services, apply resource limits and optimize the Docker image.

## B2.1 – Dockerfile and Image Build

Create a Dockerfile, build the result portal image and run the application using Docker.

```bash
docker build -t result-portal .
docker images
```

## B2.2 – Docker Run and Port Mapping

Run the application using docker run and map container port 8000 to the host port 8000.

```bash
docker run -d --name result-portal -p 8000:8000 result-portal
docker ps
```

Open the application at:

http://localhost:8000

## B2.3 – Docker Compose and Database

Run the portal and database using Docker Compose. Use a volume to preserve database data.

```bash
docker compose up -d
docker compose ps
docker volume ls
```

## B2.4 – CPU and Memory Limits

Apply CPU and memory limits using Docker options and monitor resource usage using docker stats.

```bash
docker run -d --name result-portal --cpus="0.5" --memory="512m" -p 8000:8000 result-portal

docker stats result-portal
```

## B2.5 – Image Layers and Optimization

Inspect Docker image layers using docker history. Optimize the image using a slim base image or multi-stage build.

```bash
docker history result-portal
docker images result-portal
```

## Complete the Code

Complete TODO 1, TODO 2 and TODO 3 in the given Dockerfile.

- TODO 1: Set the working directory to /app.
- TODO 2: Copy the application source and create a non-root user named portal.
- TODO 3: Expose port 8000 and start Gunicorn on 0.0.0.0:8000 using the app object in app.py.

## Alternative Concept – Full Ubuntu Image

Compare a full Ubuntu base image with python:3.12-slim and a multi-stage build based on image size, build time, image pull time and the number of installed packages.

## Result

The result portal is configured as a Docker application with database integration, resource limits and image optimization.

---

# TASK 08 – COMPARE BARE METAL, VIRTUAL MACHINE AND CONTAINER (8 MARKS)

## Aim

To deploy the same web application using bare metal, virtual machines and Docker containers and compare their performance.

## B3.1 – Deploy Three Ways

Run the same web application directly on Linux, inside a virtual machine and inside a Docker container.

The three deployment methods are:

1. Bare Metal – application runs directly on Linux.
2. Virtual Machine – application runs inside a guest operating system.
3. Docker Container – application runs inside an isolated container.

## B3.2 – Measure

Measure and compare:

- Start-up time.
- Memory used.
- Image or disk size.
- Requests per second using ab, wrk or hey.

Use Apache Benchmark:

```bash
ab -n 1000 -c 50 http://localhost:8000/
```

Record actual measurements for all three deployment methods.

## B3.3 – Scale with Kubernetes

Deploy the container to a local Kubernetes cluster with three replicas. Delete one pod and demonstrate automatic recreation. Scale the deployment to six replicas under load.

```bash
kubectl apply -f deployment.yaml
kubectl get pods
kubectl delete pod <pod-name>
kubectl get pods -w
kubectl scale deployment result-portal --replicas=6
kubectl get pods
```

## B3.4 – Engineering Trade-Off

Compare bare metal, virtual machines and containers.

| Feature | Bare Metal | Virtual Machine | Container |
|---|---|---|---|
| Start-up | Depends on application and server | Requires guest OS startup | Usually fast |
| Memory | No guest OS overhead | Higher memory usage | Generally lower |
| Isolation | Physical machine separation | Hypervisor isolation | Process-level isolation |
| Portability | Less portable | Portable VM images | Portable container images |

Bare metal is suitable for applications requiring direct hardware access and high performance. Virtual machines are suitable when separate operating systems and stronger isolation are required. Containers are suitable for applications requiring fast deployment and easy scaling.

## Complete the Code

Complete TODO 1 and TODO 2 in the Kubernetes deployment.yaml file.

- TODO 1: Configure three replicas and select pods using the app: result-portal label.
- TODO 2: Configure CPU requests of 250m and memory requests of 256Mi, with limits of 500m CPU and 512Mi memory.

Apply the configuration using:

```bash
kubectl apply -f deployment.yaml
```

## Alternative Concept – Docker Compose

Compare Docker Compose scaling on one server with Kubernetes on multiple nodes based on recovery time, required resources and maximum workload.

Docker Compose is suitable for smaller single-server applications. Kubernetes is suitable for applications requiring multi-node deployment, automatic recovery and scaling.

## Result

The same application is deployed using three methods, performance is measured, and Kubernetes scaling and automatic recovery are demonstrated.

---

# TASK 09 – FINAL ENGINEERING DECISION (5 MARKS)

## Aim

To extend the deployment with a second service, estimate system capacity and select a suitable production deployment approach for the university.

## B4.1 – Implement a Practical Extension

Add a second service to the existing Kubernetes or Docker Compose setup. Configure both services with their own CPU and memory limits and demonstrate that they are running.

The two services are:

1. University Result Portal.
2. Learning Management System (LMS).

## B4.2 – Estimate the Capacity

Use the measured requests per second from Task 08 to estimate the number of containers or virtual machines required for 150,000 students within two hours.

Given information:

Total students = 150,000

Total time = 2 hours

Time in seconds = 2 × 60 × 60 = 7,200 seconds.

Average login rate:

150,000 / 7,200 = 20.83 logins per second.

Let:

- R = measured requests per second per instance.
- Q = average HTTP requests generated by one student login.
- U = target utilisation as a decimal.

Required instances:

N = Ceiling[(150,000 × Q) / (7,200 × R × U)]

Use the actual measured requests per second from Task 08 to calculate the required instances.

## B4.3 – Production Decision

Evaluate the following deployment options:

1. Own servers with virtual machines.
2. Own servers with containers and Kubernetes.
3. Public cloud.
4. Hybrid deployment.

### Selected Approach – Hybrid Deployment

The hybrid approach uses the university's existing infrastructure for normal workloads and public cloud resources for additional capacity during result day.

Kubernetes can manage containerised applications, and a load balancer can distribute incoming requests.

The final decision must be justified using measured performance and cost estimates.

## Alternative Concept – Public Cloud Only

Evaluate a public-cloud-only solution based on:

- Yearly cost with one result day per semester.
- Time required to add computing capacity.
- Control and protection of student data.

The annual cost should include computing, database, storage, load balancer and network charges.

## Result

A second service is added with resource limits. System capacity is estimated, and a suitable production deployment method is selected based on performance, cost and data protection requirements.

---

# OVERALL CONCLUSION

This assignment evaluates Linux system components, server administration, virtualisation, containerisation, cloud deployment and orchestration.

The implementation tasks demonstrate how applications can be deployed using Linux, virtual machines and Docker containers. Kubernetes provides application scaling and recovery, while performance measurements help compare different deployment methods.

The final engineering decision considers system capacity, resource utilisation, application availability, operational costs and student data protection.

---

# GITHUB 

**Repository Name:** CSA04-192425325-Assignment5


# FINAL RESULT

All nine tasks of Operating Systems Assignment 5 CO5 are documented, covering Linux administration, virtualisation, containerisation, Kubernetes, performance evaluation and final engineering decisions.

---

# MARKS DISTRIBUTION

| Part | Task No. | Task Description | Marks |
|---|---|---|---:|
| Part A – Design | Task 01 | Linux System Components | 7 |
| Part A – Design | Task 02 | System Administration | 5 |
| Part A – Design | Task 03 | Virtualisation | 5 |
| Part A – Design | Task 04 | Containerisation | 4 |
| Part A – Design | Task 05 | Cloud Deployment and Orchestration | 4 |
| | | **PART A TOTAL** | **25** |
| Part B – Implementation | Task 06 | Linux Server Administration | 7 |
| Part B – Implementation | Task 07 | Containerise the Portal | 5 |
| Part B – Implementation | Task 08 | Deployment Comparison | 8 |
| Part B – Implementation | Task 09 | Final Engineering Decision | 5 |
| | | **PART B TOTAL** | **25** |
| | | **GRAND TOTAL** | **50** |

## ASSESSMENT SUMMARY

| Assessment Component | Marks |
|---|---:|
| Part A – Design | 25 |
| Part B – Implementation and Experimental Investigation | 25 |
| **TOTAL MARKS** | **50** |


**Student Name:** B. Archana  
**Register Number:** 192425325  
**Course:** Operating Systems  
**Course Outcome:** CO5  
**Total Marks:** 50


