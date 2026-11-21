# Alternative Concept – Ansible Instead of Handwritten Shell Scripts

## Introduction

Ansible is an automation and configuration-management tool used to configure and manage multiple servers. Instead of manually running commands on each server, administrators can write playbooks that describe the required configuration.

For the university result portal, Ansible can automate user creation, package installation, Nginx configuration, firewall rules, application deployment and service management.

## Ansible-Based Solution

The proposed Ansible setup contains:

- Control node: The computer from which Ansible commands are executed.
- Managed nodes: The Linux servers that Ansible configures.
- Inventory file: Contains the addresses of managed servers.
- Playbook: Contains the configuration and administration tasks.
- SSH keys: Allow Ansible to connect securely to managed servers.

Example inventory:

```ini
[webservers]
192.168.10.10
192.168.10.20

[databases]
192.168.10.30
```

Example playbook:

```yaml
---
- name: Configure university portal servers
  hosts: webservers
  become: yes

  tasks:
    - name: Install Nginx
      apt:
        name: nginx
        state: present
        update_cache: yes

    - name: Ensure Nginx is running
      service:
        name: nginx
        state: started
        enabled: yes
```

This is an example for Debian-based Linux systems. The package-management tasks must be adapted for other distributions.

## Shell Scripts Compared with Ansible

| Factor | Handwritten Shell Scripts | Ansible |
|---|---|---|
| Working method | Executes commands through scripts | Uses playbooks to describe configurations |
| One-server setup | Usually simple for a small number of tasks | Requires initial inventory and playbook preparation |
| Twenty-server setup | Scripts may need repeated execution and maintenance | One playbook can configure multiple managed servers |
| Consistency | Differences can occur if commands are executed manually or scripts change | Helps maintain consistent configuration |
| Learning | Basic shell scripting is easier to start with | Requires learning inventory, YAML and Ansible modules |
| Maintenance | Each script may need separate updates | Shared playbooks can be updated and reused |
| Best use | Small and simple administration tasks | Repeated configuration across multiple servers |

## Estimated Setup-Time Comparison

The following values are illustrative planning estimates, not measured experimental results. Actual time depends on the number of configuration tasks, administrator experience and network conditions.

| Setup | Shell Scripts | Ansible |
|---|---:|---:|
| One server | 1–2 hours | 2–4 hours |
| Twenty servers | 1–2 working days | 3–6 hours after initial playbook preparation |

For one server, a simple shell script may take less time because it requires fewer initial setup steps. For twenty servers, Ansible can save time because the same playbook can be applied to all managed servers.

## Risk of Differences Between Servers

With handwritten scripts, different commands or manual changes may cause servers to have different configurations.

Ansible reduces this risk by applying the same configuration to multiple servers. However, administrators must still manage inventory files, playbooks and permissions correctly.

## Learning and Maintenance Effort

Shell scripting requires knowledge of Linux commands, variables, conditions and loops. It is suitable for simple tasks such as checking disk space and processing log files.

Ansible requires knowledge of YAML, inventories, modules and playbooks. Initial learning takes more time, but it is useful when the university manages multiple servers.

## Final Evaluation

For a single Linux server, handwritten shell scripts are suitable for simple administrative tasks. For twenty or more servers, Ansible is a better choice for applying consistent configurations and reducing repeated manual work.

The university can use shell scripts for individual monitoring tasks and Ansible for configuring and maintaining multiple servers.

## Conclusion

Both shell scripts and Ansible support Linux automation. Shell scripts are simple for small tasks, while Ansible is more suitable for managing multiple servers with consistent configurations.
