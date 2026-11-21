# Alternative Concept – Fixed Virtual Machines Instead of Kubernetes Autoscaling

## Introduction

The university can use fixed virtual machines sized to handle the expected result-day traffic instead of using Kubernetes with an autoscaler.

In this approach, the required number of virtual machines is created before result day and kept running.

## Proposed Fixed VM Solution

The design would contain:

- Multiple virtual machines running the Python result portal.
- A load balancer distributing requests between the virtual machines.
- A managed database storing student records.
- Monitoring to check application and server performance.

The number of virtual machines would be selected based on load testing and expected traffic.

## Response Time on Result Day

Fixed virtual machines can provide enough capacity if they are correctly sized and tested before result day.

However, if the actual number of requests is higher than expected, the servers may become overloaded and response time may increase.

Kubernetes with autoscaling can increase the number of application replicas when demand rises, provided that additional cluster resources are available.

## Idle Resources During Normal Days

The assignment states that result-day traffic is much higher than normal traffic.

If virtual machines are sized for result day, many resources may remain unused during the other 364 days of the year.

For example, servers running at high capacity during result day may have very low utilisation during normal university days.

Kubernetes autoscaling can reduce the number of application replicas when demand falls. However, the underlying cluster resources may still incur costs.

## Cost Comparison

| Factor | Fixed Virtual Machines | Kubernetes with Autoscaling |
|---|---|---|
| Result-day capacity | Prepared in advance | Can increase replicas based on demand |
| Normal-day resource use | May leave many resources idle | Can reduce application replicas |
| Scaling | Requires manual or separately configured scaling | HPA adjusts pod replicas |
| Recovery | Depends on VM and infrastructure configuration | Controllers can replace failed pods |
| Administration | Manage VM capacity and updates | Manage cluster, workloads and policies |
| Cost | May pay for unused VM capacity | Can reduce application resource usage, but cluster and service costs remain |

## Annual Cost Evaluation

The university should compare the annual cost of keeping result-day-sized virtual machines running with the cost of using Kubernetes and autoscaling.

A basic cost calculation is:

**Annual fixed VM cost:**

`Monthly VM cost × 12`

**Annual autoscaling cost:**

`Normal-period infrastructure cost + additional result-day capacity cost + managed Kubernetes and other service costs`

The university should use actual provider prices, usage hours, storage and network charges before deciding which solution is cheaper.

## Complexity Analysis

Let N represent the number of application instances.

- Fixed VM deployment requires managing the configured virtual machines.
- Kubernetes manages the desired number of pod replicas and adjusts that number based on configured metrics.

Managing N virtual machines individually can require O(N) configuration and maintenance work. Kubernetes automates replica management, although cluster administration and monitoring still require effort.

## Final Evaluation

Fixed virtual machines are simple to understand and can provide predictable capacity. However, keeping enough machines running for result day may waste resources during normal days.

Kubernetes with autoscaling is more flexible because it can adjust application replicas based on demand. It is the preferred design when the university expects large changes in traffic and has the infrastructure and skills to operate Kubernetes.

## Conclusion

Kubernetes with autoscaling is recommended for the university result portal because it can adjust application capacity according to demand. Fixed virtual machines are an alternative, but they may leave resources unused during normal days and increase annual costs.
