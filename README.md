# Ansible configuration management playbook for automated provisioning of Linux servers #

## 📌 Project Overview

This project demonstrates Infrastructure as Code (IaC) automation using Ansible to configure a production-ready Linux server. The playbook provisions the system, secure user access with public SSH keys, installs and configures Nginx, and deploys a static web application directly from GitHub.

## Tech Stack

- Ansible
- Linux (Ubuntu)
- Nginx
- Git / GitHub
- SSH
- YAML
- Fail2Ban

## Project Structure

``` id="wq3p9k"
Configuration-Management/
├── inventory.ini                  # Ansible inventory with hosts
├── setup.yml                      # Main playbook
└── roles/
    ├── base/                      # Base system setup and utilities
    ├── nginx/                     # Web server installation
    ├── app/                       # Application deployment
    └── ssh/                       # SSH key provisioning
```
## ⚙️ Roles Implemented
### base

- System update & upgrade

- Install essential utilities

- Install and configure Fail2Ban

- Basic server hardening

### ssh

- Adds authorized public SSH key

- Secures remote access

### nginx

- Installs Nginx

- Configures web server

- Enables and starts service

### app

- Pulls static website repository from GitHub

- Deploys application to /var/www/html

- Sets proper permissions

- Restarts Nginx if required
## Usage
### 1.Clone the repository
```
git clone https://github.com/mishalbiju07/Configuration-Management.git
```
### 2.Define your inventory and SSH key
### 3.Run all roles
```
ansible-playbook -i inventory.ini setup.yml
```
### 4.Run specific role
```
ansible-playbook -i inventory.ini setup.yml --tags "app"
```
## Skills Demonstrated

- Infrastructure provisioning and configuration
- Idempotent automation with Ansible
- Modular roles for reusability and clarity
- Remote deployment via SSH
- Integration of GitHub as source for application artifacts

## Conclusion

This project automates end-to-end server configuration using Ansible roles to enforce consistency, repeatability, and scalable infrastructure management and as IaC.
