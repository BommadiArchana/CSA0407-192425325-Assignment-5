# Cloud Architecture Design for the University Result Portal

## Introduction

The university result portal normally supports a few hundred users per day. On result day, approximately 150,000 students may try to access the portal within two hours.

A single physical server may not handle this sudden increase in traffic. Therefore, a cloud-based architecture can provide additional resources and improve availability.

## Proposed Cloud Architecture

The proposed architecture contains:

1. Students – Access the result portal through a web browser.
2. DNS – Resolves the university portal domain name.
3. Load Balancer – Distributes incoming requests across application instances.
4. Managed Kubernetes Service or Virtual Machines – Runs the Python application.
5. Managed Database – Stores student records and result information.
6. Monitoring – Tracks CPU, memory, application health and traffic.

## Request Flow

1. Students open the university result portal.
2. DNS directs requests to the cloud load balancer.
3. The load balancer distributes requests across healthy application instances.
4. The Python application processes student requests.
5. The application retrieves result information from the managed database.
6. The response is returned to the student.

## Proposed Deployment

| Component | Responsibility |
|---|---|
| DNS | Resolves the portal domain name |
| Cloud Load Balancer | Distributes incoming traffic |
| Kubernetes or VMs | Runs application instances |
| Managed Database | Stores student records |
| Persistent Storage | Stores required application and database data |
| Monitoring | Tracks system health and performance |

## Why Use a Load Balancer?

A load balancer distributes incoming requests across multiple application instances.

It prevents all requests from reaching a single application server. If one application instance becomes unhealthy, the load balancer can stop sending traffic to that instance, depending on its health-check configuration.

## Why Use a Managed Database?

A managed database reduces the work required to install, update and maintain database software.

The university should configure database backups, access permissions, encryption and recovery procedures. The database should accept connections only from authorized application services.

## Handling Result-Day Traffic

The university can increase the number of application instances before and during result day. The load balancer distributes traffic across these instances.

Monitoring should be used to observe CPU usage, memory usage, response time, database connections and request rates.

## Evaluation

This cloud design can provide flexible capacity and reduce dependence on one physical server. It also supports application scaling and database management.

However, cloud deployment introduces costs for computing resources, storage, networking and managed services. The university must also protect student information and plan backups.

## Conclusion

A cloud architecture using a load balancer, multiple application instances and a managed database is suitable for handling sudden increases in university result portal traffic.
