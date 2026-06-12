# uptime-monitor

A lightweight, automated script to monitor 3 servers uptime!

## Overview

This Project Demonstrates basics infrastructure automation using ansible.

A dedicated Linux controller node connects to three remote Linux servers using SSH key-based authentication
and execute "Uptime" checks across all managed hosts.

The goal of this lab was to gain hands-on experience with:

- infrastructure automation
- Ansible inventory management
- SSH key authentication
- Remote command execution
- Linux administration
- Basic DevOps workflow

## Lab Environment

### Controller Node

- Ubuntu Linux
- Ansible Installation and openssh-server 

### Managed Nodes

- Server 1
- Server 2
- Server 3

All systems including the controller node use static private IP addressing and SSH connectivity.

## Project Objective

The controller node remotely connects to all managed servers and retrieves uptime information through
a single ansible command.

This validates:

- Network connectivity
- SSH trust relationships
- Sucessful Ansible automation.

 
## Skills Demonstrated

- Linux Adminstration
- Ansible Automation
- SSH configuration
- Network troubleshooting
- Firewall configuration
- Traffic Management
- Infrastructure management
- DevOps Fundamentals.

### Future Improvement

- Automated users management
- Automated Access Control List
- Automated Group Plicy
- Automated Least Privilage automation

## Author 
Ben Mbarek


## License

This project is licensed under the MIT License
