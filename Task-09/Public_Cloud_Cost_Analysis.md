# Public Cloud Cost Analysis

## Aim
To evaluate the cost and operational impact of using only public cloud services instead of the university's own servers with Kubernetes.

## Public Cloud Solution
The university can host the result portal, learning management system and online examination system on public cloud virtual machines or a managed Kubernetes service. A load balancer can distribute student requests, and a managed database can store student information.

## Yearly Cost Estimation

The university publishes results twice a year. Cloud costs should include:

- Computing resources used throughout the year.
- Additional computing capacity required during the two result days.
- Managed database charges.
- Load balancer charges.
- Storage and backup charges.
- Network data transfer charges.

Estimated yearly cost:

Annual Cost = Normal Running Cost + Additional Result-Day Cost + Database Cost + Storage Cost + Network Cost

Use the cloud provider's actual pricing calculator to enter the required resource sizes and operating hours.

## Evaluation

**Cost:** Public cloud avoids purchasing additional physical servers, but recurring usage, storage and network charges must be considered.

**Adding Capacity:** Cloud resources can be increased when traffic rises, depending on the selected service and available configuration.

**Student Data Control:** The university must select suitable data locations, access controls, encryption and backup policies. It remains responsible for protecting student information and meeting applicable requirements.

## Result
Public cloud provides flexible capacity and avoids buying additional servers. However, the university must evaluate the yearly cost and data protection requirements before choosing a cloud-only solution.
