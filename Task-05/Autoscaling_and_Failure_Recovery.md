# Autoscaling and Failure Recovery

## Introduction

The university result portal experiences different traffic levels during normal days and result days. Autoscaling helps increase application capacity when demand rises and reduce resources when demand falls.

## Horizontal Scaling

Horizontal scaling means adding more application instances instead of increasing the resources of one existing instance.

For example, the university can increase the portal from three pods to six pods when student traffic increases.

## Autoscaling Process

1. Monitoring collects CPU utilisation or other supported metrics.
2. The Horizontal Pod Autoscaler checks the configured scaling target.
3. If demand increases, Kubernetes increases the number of pod replicas.
4. If demand decreases, Kubernetes can reduce the number of replicas.
5. The Service continues directing traffic to available pods.

## Failure Recovery

Kubernetes helps recover from certain application failures.

If a portal pod stops working, the Deployment controller attempts to create another pod to maintain the desired replica count.

Readiness and liveness probes can also help Kubernetes identify whether an application is ready to receive traffic or needs to be restarted.

However, Kubernetes cannot automatically recover every failure. Physical server failure, database failure, storage failure and network failure may require additional configuration and infrastructure.

## Benefits for the University

- Supports increased student traffic.
- Maintains multiple application instances.
- Replaces failed pods.
- Adjusts the number of replicas according to demand.
- Helps use resources more efficiently.

## Limitations

- Requires proper cluster configuration.
- Scaling depends on available computing resources.
- Poor resource limits can affect application performance.
- Database capacity can become a bottleneck even when application pods scale.

## Conclusion

Kubernetes autoscaling and recovery features help maintain portal availability during high-demand periods. Monitoring, suitable resource limits and database capacity planning are also necessary.
