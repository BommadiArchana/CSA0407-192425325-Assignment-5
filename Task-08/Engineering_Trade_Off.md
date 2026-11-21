# Engineering Trade-Off

## Aim
To compare bare metal, virtual machines and containers and identify the suitable deployment method for the university result portal.

## Comparison

| Feature | Bare Metal | Virtual Machine | Container |
|---|---|---|---|
| Start-up | Depends on application and server | Requires guest OS startup | Usually fast |
| Memory | No guest OS overhead | Higher memory usage | Generally lower memory usage |
| Isolation | Physical machine separation | Strong hypervisor isolation | Process-level isolation |
| Portability | Less portable | Portable VM images | Portable container images |
| Resource Usage | Direct hardware usage | Uses host and guest resources | Shares host kernel |

## Engineering Evaluation

**Bare Metal:** Suitable for applications requiring direct hardware access and high performance.

**Virtual Machine:** Suitable for applications requiring separate operating systems and strong isolation.

**Container:** Suitable for web applications requiring fast deployment, efficient resource usage and easy scaling.

## Decision

Containers are suitable for the university result portal because they allow quick deployment, efficient resource usage and easy scaling. Virtual machines are useful when separate operating systems and stronger isolation are required.

## Result

The three deployment methods are compared based on start-up time, memory, isolation and portability. The final selection should also consider the actual performance measurements collected in B3.2.
