# A3.1 – Hypervisors

## Introduction

Virtualisation is a technology that allows one physical computer to run multiple virtual machines. Each virtual machine behaves like an independent computer with its own operating system, CPU allocation, memory and storage.

A hypervisor is software that creates and manages virtual machines. It allocates physical hardware resources to each virtual machine.

## Type-1 Hypervisor – Bare-Metal

A Type-1 hypervisor runs directly on the physical hardware without requiring a general-purpose host operating system underneath it.

Examples:

- KVM
- VMware ESXi
- Xen
- Microsoft Hyper-V

**Working:**

1. The hypervisor runs on the physical server.
2. It allocates CPU, memory and storage to virtual machines.
3. Each virtual machine runs its own guest operating system.
4. Applications run inside the guest operating systems.

**Advantages:**

- Suitable for server environments.
- Provides isolation between virtual machines.
- Supports efficient resource allocation.
- Supports enterprise virtualisation features, depending on the platform.

**Limitations:**

- Requires proper installation and configuration.
- Hardware and licensing requirements depend on the platform.
- Administration requires virtualisation knowledge.

## Type-2 Hypervisor – Hosted

A Type-2 hypervisor runs as an application on an existing host operating system.

Examples:

- Oracle VirtualBox
- VMware Workstation

**Working:**

1. A host operating system is installed on the physical computer.
2. The Type-2 hypervisor is installed as software.
3. Virtual machines are created using the hypervisor.
4. Each virtual machine runs its own guest operating system.

**Advantages:**

- Easy to install and use.
- Suitable for learning and testing.
- Allows multiple operating systems to run on one computer.
- Useful for development environments.

**Limitations:**

- Requires memory and CPU resources for the host operating system.
- Adds another software layer.
- I/O performance may be affected by host operating-system activity.
- Generally less suitable for high-demand production server environments.

## Comparison of Type-1 and Type-2 Hypervisors

| Factor | Type-1 | Type-2 |
|---|---|---|
| Installation | Directly on hardware | On a host operating system |
| Performance | Generally lower overhead | Additional host-layer overhead |
| Resource usage | No separate general-purpose host OS is required | Host OS also consumes resources |
| Usage | Server and data-centre environments | Desktop testing and development |
| Examples | KVM, ESXi, Xen, Hyper-V | VirtualBox, VMware Workstation |

## Application to the University Result Portal

A Type-1 hypervisor is suitable for the university server because it can host separate virtual machines for the web application and database. It supports resource allocation and isolation between services.

A Type-2 hypervisor can be used by students or developers to test the portal, but it is not the preferred choice for a high-traffic production deployment.

## Conclusion

Type-1 hypervisors are generally more suitable for production server environments, while Type-2 hypervisors are useful for learning, testing and development.
