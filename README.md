# Ubuntu Infrastructure as Code Toolkit

**Automated Ubuntu Server Provisioning & Security Hardening**

An Infrastructure as Code (IaC) project designed to automate the deployment, configuration, and security hardening of Ubuntu servers using **Vagrant and Ansible**.

This project demonstrates how infrastructure can be provisioned consistently and secured through automation rather than manual system administration.

---

## Project Overview

The Ubuntu IaC Toolkit automates the provisioning of an Ubuntu 22.04 virtual machine and applies a baseline security configuration using Ansible.

The project uses Vagrant to create an isolated Ubuntu environment and Ansible to automate system configuration and firewall management.

The primary objective is to establish a repeatable deployment process while implementing essential server security practices.

## Technology Stack

| Technology | Purpose |
|---|---|
| Ubuntu 22.04 LTS | Target operating system |
| Vagrant | Virtual machine provisioning |
| Ansible | Configuration management and automation |
| UFW | Firewall management |
| YAML | Infrastructure and configuration definitions |
| Git / GitHub | Version control |

## Features

### Automated Infrastructure Provisioning
- Creates an Ubuntu 22.04 virtual machine.
- Assigns a private network IP address (`192.168.56.10`).
- Uses Vagrant to maintain a consistent deployment environment.

### Automated Security Hardening
- Updates the Ubuntu package registry.
- Installs Uncomplicated Firewall (UFW).
- Enables the firewall automatically.
- Blocks incoming network traffic by default.
- Explicitly allows SSH connections on TCP port 22.

### Infrastructure as Code
- Uses YAML-based Ansible playbooks.
- Maintains infrastructure configurations in version control.
- Reduces repetitive manual configuration.
- Supports repeatable infrastructure deployments.

## Repository Structure

```text
ubuntu-iac-toolkit/
│
├── roles/
│   └── hardening/
│       └── tasks/
│           └── main.yml
│
├── .gitignore
├── Vagrantfile
├── hosts.ini
└── site.yaml
```

## Prerequisites

Before deploying the project, ensure you have:

- A Linux environment or Windows with WSL2.
- Vagrant installed.
- A supported Vagrant virtualization provider.
- Ansible installed.
- Git installed.
- Sufficient system resources to run an Ubuntu virtual machine.

## Installation

**1. Clone the repository**

```bash
git clone https://github.com/dshaferdave-ai/ubuntu-iac-toolkit.git
```

**2. Navigate into the project**

```bash
cd ubuntu-iac-toolkit
```

**3. Provision the Ubuntu virtual machine**

```bash
vagrant up
```

Vagrant will download the Ubuntu 22.04 base image and provision the virtual machine using the included Vagrantfile.

**4. Configure the Ansible inventory**

The included `hosts.ini` defines the target server:

```ini
[my_servers]
192.168.56.10
```

Ensure the SSH connection settings and private key path match your Vagrant environment.

## Deployment

Once the virtual machine is provisioned and Ansible can connect to the target server, execute the infrastructure playbook:

```bash
ansible-playbook -i hosts.ini site.yaml
```

The playbook is designed to execute the Ubuntu provisioning and hardening configuration.

## Security Configuration

The hardening component implements the following baseline security measures:

| Configuration | Implementation |
|---|---|
| Package Management | Updates package registry |
| Firewall Installation | Installs UFW |
| Firewall Activation | Enables UFW |
| Incoming Traffic | Default policy set to DENY |
| SSH Access | Allows TCP port 22 |

**Security Note:** The firewall configuration is intended to establish a basic security baseline. Additional configuration may be necessary depending on the server's intended use.

## Project Goals

This project explores several fundamental infrastructure and cybersecurity concepts:

- Infrastructure as Code (IaC).
- Automated server provisioning.
- Configuration management.
- Linux system administration.
- Network security and firewall configuration.
- Repeatable infrastructure deployments.

## Future Improvements

Potential future additions include:

- Automated security updates.
- SSH key management and authentication hardening.
- Additional firewall rules and network segmentation.
- Automated system auditing.
- Ansible Vault integration for sensitive configuration.
- Deployment verification and automated testing.
- Support for additional Ubuntu server environments.

## License

This project is open source. See the repository for licensing information.

---

**Author:** [@dshaferdave-ai](https://github.com/dshaferdave-ai)

**Repository:** [ubuntu-iac-toolkit](https://github.com/dshaferdave-ai/ubuntu-iac-toolkit)

**Project Type:** Infrastructure as Code / DevOps / Linux Security
