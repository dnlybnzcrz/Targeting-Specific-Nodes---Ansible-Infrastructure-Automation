# Targeting Specific Nodes - Ansible Infrastructure Automation

This repository contains an Ansible automation project for managing and configuring multiple server roles (web servers, database servers, and file servers) across both Ubuntu and CentOS environments.

## Overview

This project provides automated server configuration and management using Ansible playbooks. It supports:
- Web servers (Apache/httpd with PHP)
- Database servers (MariaDB)
- File servers (Samba)
- Multi-distribution support (Ubuntu and CentOS)

## Project Structure

```
.
├── ansible.cfg      # Ansible configuration file
├── inventory        # Inventory file defining server groups
└── site.yml        # Main playbook containing all server configurations
```

## Server Groups

The project manages three types of server groups:
- **web_servers**: Apache/httpd web servers with PHP support
- **db_servers**: MariaDB database servers
- **file_servers**: Samba file sharing servers

## Features

- Automated system updates for both Ubuntu and CentOS
- Web server installation and configuration (Apache/httpd)
- PHP installation and configuration
- MariaDB database server setup
- Samba file server configuration
- Role-based server management
- Tagged tasks for selective execution

## Prerequisites

- Ansible installed on the control node
- SSH access to target servers
- Sudo privileges on target servers
- Target servers running either Ubuntu or CentOS

## Usage

1. Update the `inventory` file with your server IP addresses
2. Run the playbook:
   ```bash
   ansible-playbook -i inventory site.yml
   ```

### Running Specific Tasks

You can use tags to run specific parts of the playbook:
```bash
# For web server tasks only
ansible-playbook -i inventory site.yml --tags apache

# For database tasks only
ansible-playbook -i inventory site.yml --tags db

# For file server tasks only
ansible-playbook -i inventory site.yml --tags samba
```

## Supported Distributions

- Ubuntu
- CentOS

## License

This project is open source and available under the MIT License.
