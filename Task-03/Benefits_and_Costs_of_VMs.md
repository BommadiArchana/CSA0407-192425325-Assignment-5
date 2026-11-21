# A3.2 – Benefits and Costs of Virtual Machines

## Introduction

Virtual machines allow the university to run multiple services on one physical server. The result portal can use separate virtual machines for the web application, database and testing environment.

## Benefits of Virtual Machines

### 1. Isolation

Each virtual machine runs separately. If one virtual machine experiences an application failure, the other virtual machines can continue operating, provided the physical host remains available.

For example, a failure in the testing virtual machine does not necessarily affect the production database virtual machine.

### 2. Server Consolidation

Multiple virtual machines can run on one physical server. This reduces the need to purchase a separate physical server for every service.

The university can use one physical server to host the portal, database and monitoring services, depending on available capacity.

### 3. Snapshots

A snapshot records the state of a virtual machine at a particular time. It can help administrators return to an earlier state after a configuration problem.

Snapshots are useful before software updates and system changes. They should not replace regular backups.

### 4. Live Migration

Live migration moves a running virtual machine from one physical host to another with little or no interruption, when supported by the hypervisor and infrastructure.

It is useful during hardware maintenance and resource balancing.

## Costs and Limitations of Virtual Machines

### 1. Performance Overhead

Virtual machines use virtual hardware and hypervisor services. Some operations may have additional overhead compared with running directly on physical hardware.

### 2. Memory Usage

Every virtual machine requires memory for its guest operating system and applications.

For example, if the university runs three virtual machines, memory must be available for all three guest operating systems in addition to the hypervisor's requirements.

### 3. Licensing Cost

Some virtualisation platforms and guest operating systems require paid licences. The university must consider these costs when selecting a platform.

### 4. Hardware Requirements

The physical server must have sufficient CPU, RAM and storage capacity to run all virtual machines.

## Proposed Virtual Machine Design

| Virtual machine | Purpose |
|---|---|
| VM 1 | Nginx and web access |
| VM 2 | Python result portal |
| VM 3 | Database server |
| VM 4 | Monitoring and testing |

This is a proposed design. The actual number of virtual machines should depend on measured workload and available hardware resources.

## Evaluation for the University

Virtual machines provide service isolation, consolidation and easier maintenance. Snapshots help with configuration recovery, while live migration supports planned hardware maintenance.

However, each virtual machine consumes memory and storage. The university must avoid creating too many virtual machines on a server with limited resources.

## Conclusion

Virtual machines provide flexibility and isolation for the university result portal. Their benefits are useful for server management, but resource usage and licensing costs must be considered before deployment.
