# A5.2 – Kubernetes Components

## Introduction

Kubernetes is a container orchestration platform used to deploy, manage and scale containerised applications. It can manage multiple instances of the university result portal across a group of servers.

## Pods

A pod is the smallest deployable unit in Kubernetes. It contains one or more containers that share network and storage resources.

For the result portal, a pod can run one instance of the Python application container.

## Deployments

A Deployment manages application pods. It maintains the required number of replicas and replaces pods when they fail.

For example, a Deployment can maintain three running portal pods.

## Services

A Service provides a stable network endpoint for accessing a group of pods.

It allows students or other application components to access the portal without depending on individual pod IP addresses.

## Replicas

Replicas are multiple running instances of the same application.

If the portal has three replicas, Kubernetes attempts to maintain three available pod instances according to the Deployment configuration.

More replicas can help handle increased traffic, provided sufficient CPU, memory and database capacity are available.

## Resource Requests and Limits

Resource requests specify the CPU and memory required by a container for scheduling.

Resource limits define the maximum CPU and memory resources a container can use.

Example:

```yaml
resources:
  requests:
    cpu: "250m"
    memory: "256Mi"
  limits:
    cpu: "500m"
    memory: "512Mi"
```

This example requests 250 millicores of CPU and 256 MiB of memory. The limits are 500 millicores and 512 MiB.

These values are examples and should be adjusted based on application measurements.

## Horizontal Pod Autoscaler (HPA)

The Horizontal Pod Autoscaler automatically increases or decreases the number of pod replicas based on configured metrics, such as CPU utilisation.

For example:

- When traffic increases and CPU utilisation rises, HPA can increase the number of portal pods.
- When demand decreases, HPA can reduce the number of replicas.

HPA requires the relevant metrics to be available, and scaling also depends on available cluster capacity.

## How Kubernetes Helps the Result Portal

| Component | Purpose |
|---|---|
| Pods | Run portal containers |
| Deployments | Maintain the required number of pods |
| Services | Provide stable network access |
| Replicas | Run multiple application instances |
| Resource requests | Help schedule pods based on required resources |
| Resource limits | Restrict CPU and memory usage |
| HPA | Adjust replicas based on demand |

## Conclusion

Kubernetes helps the university deploy, manage and scale the result portal. Deployments and replicas support recovery from pod failures, while Services provide stable access and HPA adjusts application capacity according to demand.
