# Full Virtualisation and Para-Virtualisation

## Introduction

Full virtualisation and para-virtualisation are two approaches used to run operating systems inside virtual machines.

## Full Virtualisation

Full virtualisation provides a complete virtual hardware environment to the guest operating system. The guest operating system can run without being specially modified for the hypervisor.

**Features:**

- Provides virtual CPU, memory and devices.
- Supports unmodified guest operating systems.
- Provides isolation between virtual machines.
- Uses hardware virtualisation support where available.

**Example:** A Linux virtual machine running on KVM or VirtualBox.

## Para-Virtualisation

Para-virtualisation uses communication between the guest operating system and the hypervisor through special interfaces or drivers.

The guest operating system or its drivers must support these interfaces.

**Features:**

- Allows the guest to communicate efficiently with the hypervisor.
- Can reduce some virtualisation overhead.
- Uses hypervisor-aware drivers or interfaces.
- Requires guest support for the relevant para-virtualised features.

**Example:** Virtio drivers used by KVM virtual machines for efficient virtualised network and storage I/O.

## Comparison

| Factor | Full Virtualisation | Para-Virtualisation |
|---|---|---|
| Guest OS modification | Generally not required | Guest support or special drivers are required |
| Hardware view | Complete virtual hardware | Uses hypervisor-aware interfaces for supported operations |
| Compatibility | Generally supports a wider range of operating systems | Depends on guest and driver support |
| Performance | Depends on hardware and virtualisation implementation | Can improve selected I/O operations |
| Example | General virtual machine using virtual hardware | KVM with Virtio drivers |

## Hardware Support – Intel VT-x and AMD-V

Modern processors provide hardware virtualisation extensions to support virtual machines.

**Intel VT-x:**

Intel VT-x is a hardware virtualisation technology that helps processors execute guest operating systems efficiently.

**AMD-V:**

AMD-V is AMD's hardware virtualisation technology. It provides processor support for running virtual machines.

These technologies help the hypervisor manage guest operating systems and improve virtualisation performance.

## Application to the University Result Portal

The university should use a server processor that supports hardware virtualisation. Intel VT-x or AMD-V should be enabled in the system firmware when required by the selected platform.

KVM can use hardware virtualisation support to run virtual machines. Virtio drivers can improve virtual network and storage operations.

## Conclusion

Full virtualisation provides a complete virtual hardware environment, while para-virtualisation uses hypervisor-aware interfaces for supported operations. Intel VT-x and AMD-V provide hardware support for virtualisation.
