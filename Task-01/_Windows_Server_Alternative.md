# Alternative Concept – Windows Server Instead of Linux

## Introduction

If the university result portal used Windows Server instead of Linux, the web application and database could be hosted using Windows-based server services. IIS could be used as the web server, and Windows administration tools could be used to manage users, storage and networking.

## Windows Server Solution

The proposed setup would include:

- Windows Server as the operating system.
- IIS for hosting the web application.
- A supported database server.
- Windows Firewall for network protection.
- Active Directory for centralized user management, if required.
- PowerShell for administration and automation.

## Evaluation of Memory and Disk Usage

Windows Server provides several built-in services and management components. These can increase the base memory and disk requirements depending on the selected edition, installed roles and configuration.

Linux server installations can be configured with fewer packages and services when a minimal installation is selected.

The actual memory and disk usage must be measured on the selected operating system versions. It should not be assumed that every Windows installation uses more resources than every Linux installation.

## Automation Time

Windows Server supports PowerShell for automating administration tasks such as:

- User creation.
- Service management.
- Log monitoring.
- Backup operations.
- Disk-space monitoring.

Linux supports shell scripts, cron and configuration-management tools such as Ansible.

Both systems can automate routine administration. The time required depends on the administrator's experience and the complexity of the task.

## Licence Cost

Windows Server generally requires a commercial licence. The cost depends on the edition, licensing model, number of cores and user or device access requirements.

Linux distributions such as Ubuntu Server can be used without purchasing an operating-system licence, although support and cloud-service costs may apply.

The exact Windows Server licence cost should be checked using the current official pricing for the required edition and deployment.

## Comparison

| Factor | Linux Server | Windows Server |
|---|---|---|
| Operating-system licence | Many distributions are free to use | Commercial licensing generally applies |
| Administration | Shell and system utilities | PowerShell and graphical tools |
| Web hosting | Nginx or Apache | IIS or other supported servers |
| Automation | Bash and cron | PowerShell and Task Scheduler |
| Resource usage | Depends on installed services | Depends on installed roles and services |
| Container support | Native Linux containers | Windows containers and Linux VM-based workloads |

## Final Evaluation

For the university result portal, Linux is a suitable choice because it supports Python applications, databases, Nginx, Docker and Kubernetes. It also offers flexible automation and avoids the need for a paid operating-system licence in many deployment configurations.

Windows Server is also a valid option, especially where the university already uses Microsoft-based infrastructure and administration tools. The final choice should depend on measured resource usage, licensing cost, application compatibility and administrator skills.

## Conclusion

Both Linux and Windows Server can host the university result portal. Linux is a practical choice for this case because of its support for open-source server technologies, automation and container platforms.
