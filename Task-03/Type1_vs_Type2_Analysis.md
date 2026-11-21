# Alternative Concept – Type-2 Hypervisor Instead of Type-1

## Introduction

The university can use a Type-2 hypervisor such as VirtualBox instead of a Type-1 hypervisor such as KVM. In this approach, VirtualBox runs on a host operating system, and the portal and database run inside separate virtual machines.

## Proposed Type-2 Solution

The deployment would contain:

- Physical computer with Linux or Windows as the host operating system.
- VirtualBox installed on the host.
- One virtual machine for the Python result portal.
- Another virtual machine for the database.
- Network communication between the two virtual machines.

The host operating system manages the physical hardware, while VirtualBox manages the guest virtual machines.

## CPU-Bound Workload

A CPU-bound workload mainly depends on processor operations.

In a Type-2 environment, the virtual machine runs through the hypervisor and host operating system. This can introduce additional overhead.

KVM runs as part of the Linux kernel and is generally more suitable for server workloads where lower virtualisation overhead is important.

For the result portal, CPU overhead can affect request processing when many students access the application simultaneously.

## I/O-Bound Workload

An I/O-bound workload spends much of its time performing storage or network operations.

A Type-2 hypervisor uses the host operating system's storage and networking interfaces. This additional layer can affect disk and network performance.

KVM can use Virtio drivers to provide efficient virtualised storage and networking.

For the university database, disk I/O performance is important because the database must retrieve student records quickly.

## Memory Used by the Host Operating System

A Type-2 hypervisor requires memory for both the host operating system and the guest virtual machines.

For example, the host operating system uses memory for its own services, while each virtual machine requires additional memory for its guest operating system and applications.

KVM does not require a separate general-purpose host operating system layer in the same way as a hosted hypervisor, although the Linux host and hypervisor services still consume memory.

## Comparison of KVM and VirtualBox

| Factor | KVM – Type-1 style deployment | VirtualBox – Type-2 |
|---|---|---|
| Architecture | Integrated with Linux kernel | Runs on a host operating system |
| CPU overhead | Generally lower for server workloads | Additional host layer may add overhead |
| I/O performance | Supports efficient Virtio drivers | Depends on host and virtual device configuration |
| Host memory | Linux host services still use memory | Host OS and guest OS memory are both required |
| Production use | Suitable for production when properly configured | Mainly suitable for testing and development |
| Management | Server virtualisation tools | Desktop graphical management tools |

## Complexity Analysis

Virtualisation overhead is not an algorithmic operation, so Big-O notation does not directly describe the CPU or I/O performance difference between KVM and VirtualBox.

For the virtual machine management process:

- Creating one virtual machine requires configuration and resource allocation.
- Managing N virtual machines requires managing N sets of configurations and resources.
- The administrative effort generally grows with the number of virtual machines.

The management effort can be described as O(N) when each virtual machine requires an individual configuration or check. Automation can reduce repeated manual work.

Actual CPU, memory and I/O overhead should be measured on the same hardware using the same guest operating system and workload.

## Suitability for Production

VirtualBox is suitable for learning, development and testing. It allows administrators to test the portal without using the production server.

KVM is a better choice for the university production environment because it is designed for Linux server virtualisation and supports server-oriented management features.

## Final Evaluation

If VirtualBox were used, the university would need to provide memory and CPU resources for the host operating system as well as the guest virtual machines. CPU-bound and I/O-bound performance may also be affected by the additional host layer.

Therefore, KVM is recommended for production, while VirtualBox can be used for development and testing.

## Conclusion

Type-2 virtualisation is easy to use but adds host operating-system overhead. Type-1 virtualisation using KVM is more suitable for hosting the university result portal in a production environment.
