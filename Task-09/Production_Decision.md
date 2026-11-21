# Production Decision

## Aim
To select a suitable deployment method for the university result portal, learning management system and online examination system.

## Deployment Options

**Own Servers with Virtual Machines:** Each application runs inside a separate virtual machine. This provides isolation, but requires more memory and server resources.

**Own Servers with Containers and Kubernetes:** Applications run in containers. Kubernetes manages replicas, scaling and recovery. It provides better flexibility for managing multiple services.

**Public Cloud:** Applications use cloud-based computing resources. Capacity can be increased when student traffic rises. The university pays for the resources used.

**Hybrid Deployment:** Normal services run on the university's existing infrastructure. Additional public cloud resources are used during result day and other high-demand periods.

## Selected Approach: Hybrid Deployment

The hybrid approach is suitable because the university already has a private server room and a public cloud account. The existing infrastructure can support normal workloads, while cloud resources can provide additional capacity during result day.

Kubernetes can manage the containerised services, and a load balancer can distribute incoming requests.

## Result
A hybrid deployment is recommended to improve availability and handle high student traffic without purchasing additional physical servers. The final decision should be checked against the measured performance and estimated cost.
