![image](https://github.com/user-attachments/assets/66cdd32e-ade6-4f93-b32d-d7c3e726bee4)

# Multi-OS Web Server Configuration Automation with Ansible

## Overview

This project automates the installation and configuration of a web server (`httpd`) on both Ubuntu and Red Hat systems, with Ansible managing all steps. By customizing the server to listen on port 82 instead of the default port 80, this playbook simplifies multi-OS server configuration for environments with custom port requirements.

## Project Highlights
- **Cross-Platform Compatibility**: Supports both Ubuntu and Red Hat, with OS-specific settings for seamless configuration.
- **Automated Firewall & SELinux Configuration**: Sets up firewall rules and SELinux policies to secure the server.
- **Port Customization**: Configures the server to listen on port 82, demonstrating flexibility in server setup.

## Roles Description

1. **common**: Includes common dependencies and configurations.
2. **install_apache_and_firewall**: Installs `httpd` and configures UFW (Ubuntu) or firewall-cmd (Red Hat).
3. **ensure_services_are_enabled**: Ensures that web server and firewall services are enabled and running.
4. **change_port**: Modifies the server to listen on port 82.
5. **add_ports_to_firewall**: Configures firewall rules for port 82.
6. **selinux_conf**: Manages SELinux context for Red Hat and Ubuntu.
7. **change_configuration**: Updates server configurations as required.

## Usage

### Prerequisites
Ensure Ansible is installed on the controller machine, and that target machines (Ubuntu and Red Hat) are reachable.

### Running the Playbook

Update the `inventory` with the IPs of target servers. Run the playbook with:

```bash
ansible-playbook -i inventory playbook.yml
