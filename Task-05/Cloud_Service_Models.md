# A5.1 – Cloud Service Models

## Introduction

Cloud computing provides computing resources such as servers, storage, databases and networking through the internet. It allows the university to increase resources when many students access the result portal.

The three main cloud service models are IaaS, PaaS and SaaS.

## Infrastructure as a Service (IaaS)

IaaS provides virtual machines, storage and networking resources through a cloud provider.

The university manages the operating system, application, database software and application configuration.

Examples:

- Amazon EC2
- Microsoft Azure Virtual Machines
- Google Compute Engine

**Advantages:**

- Provides control over virtual machines.
- Allows custom operating-system configuration.
- Supports flexible resource allocation.

**Limitations:**

- Requires server administration.
- The university must manage operating-system updates and application deployment.
- Resource configuration and monitoring are required.

## Platform as a Service (PaaS)

PaaS provides a managed platform for developing and hosting applications. The cloud provider manages much of the underlying infrastructure and operating system.

Examples:

- Google App Engine
- Azure App Service
- AWS Elastic Beanstalk

**Advantages:**

- Reduces server-management work.
- Supports application deployment.
- Provides managed platform services.

**Limitations:**

- Provides less control over the underlying infrastructure.
- Some platforms have restrictions on supported runtimes and configurations.
- Costs depend on usage and service configuration.

## Software as a Service (SaaS)

SaaS provides ready-to-use software through the internet. The provider manages the application and its infrastructure.

Examples:

- Gmail
- Microsoft 365
- Salesforce

**Advantages:**

- No need to manage application servers.
- Accessible through a web browser.
- Updates are generally managed by the provider.

**Limitations:**

- Limited control over application internals.
- Customisation may be restricted.
- Depends on the provider's available features.

## Comparison of IaaS, PaaS and SaaS

| Factor | IaaS | PaaS | SaaS |
|---|---|---|---|
| Provides | Virtual machines and infrastructure | Application hosting platform | Ready-to-use software |
| Server management | Customer manages OS and applications | Provider manages platform infrastructure | Provider manages application and infrastructure |
| Control | High | Medium | Low |
| Flexibility | High | Medium | Depends on the software |
| Example | Amazon EC2 | Azure App Service | Gmail |

## Best Choice for the University

IaaS or managed Kubernetes can be used when the university needs control over the result portal infrastructure. PaaS is suitable when the university wants to deploy the application without managing the complete server environment.

SaaS is not the main choice for hosting a custom university result portal because it provides ready-to-use software rather than a custom application hosting environment.

## Conclusion

IaaS provides infrastructure control, PaaS simplifies application hosting and SaaS provides ready-to-use software. The university can choose IaaS or a managed Kubernetes platform for flexible deployment of the result portal.
