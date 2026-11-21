# Alternative Concept – Separate Virtual Machines Instead of Containers

## Introduction

Instead of using containers, the university could run the Python result portal and database in separate virtual machines. Each virtual machine would have its own guest operating system and application environment.

## Proposed VM-Based Solution

The design would contain:

- VM 1 – Linux guest operating system running the Python result portal.
- VM 2 – Linux guest operating system running the database.
- Hypervisor – Manages both virtual machines.
- Virtual network – Allows the portal VM to communicate with the database VM.

## Startup Time Comparison

A container usually starts within seconds because it shares the host kernel and does not need to boot a complete guest operating system.

A virtual machine normally takes longer because it must boot its guest operating system before starting the application.

Therefore, containers are useful when the university needs to start additional portal instances quickly during result day.

## Memory Usage Comparison

Each virtual machine requires memory for its guest operating system and applications.

Containers share the host kernel, so they generally require less memory for each application instance.

If the university creates many portal instances, containers can use available memory more efficiently than running a full guest operating system for every instance.

## Isolation and Security

Virtual machines provide a separate guest operating system and virtual hardware boundary. This provides stronger separation between the portal and database environments.

Containers isolate processes and resources but share the host kernel. Their security depends on correct configuration, kernel protection and access controls.

## Comparison

| Factor | Separate Virtual Machines | Separate Containers |
|---|---|---|
| Startup time | Usually longer | Usually seconds |
| Memory | Full guest OS memory required | Shared host kernel |
| Isolation | Separate guest OS boundary | Process and resource isolation |
| Resource usage | Generally higher | Generally lower |
| Scaling | More resource-intensive | Easier to scale quickly |
| Maintenance | Guest OS updates for each VM | Host and image updates |

## Complexity Analysis

Let N represent the number of application instances.

- Starting N virtual machines requires booting N guest operating systems.
- Starting N containers requires creating N container instances from available images.

The number of instances is N in both approaches, but the resource requirements differ. Containers generally use less memory per application instance because they share the host kernel.

The actual startup time and memory difference must be measured on the same hardware. Big-O notation alone cannot represent the performance overhead of either approach.

## Evaluation for the University Result Portal

If separate virtual machines are used, the portal and database receive independent guest operating systems. This improves separation but increases memory and storage requirements.

If containers are used, the university can start additional portal instances more quickly and use resources more efficiently. Persistent database storage and security controls must still be configured correctly.

## Final Decision

For the university result portal, containers are recommended for the Python application because they support faster deployment, lower per-instance resource usage and easier scaling.

The database can run in a separate container with persistent storage, or in a dedicated virtual machine if stronger operating-system isolation is required.

## Conclusion

Separate virtual machines provide stronger operating-system separation but require more resources and longer startup times. Containers are a practical choice for scaling the result portal during high-demand periods.
