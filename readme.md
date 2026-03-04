# Ansible Playbooks — Linux Infrastructure Automation

A collection of Ansible playbooks for automating RHEL/Rocky Linux 
system administration tasks.

## Requirements

- Ansible Core 2.10+
- Target: RHEL 9 / Rocky Linux 9
- SSH key-based authentication configured
- Sudo privileges on managed nodes

## Structure

ansible-lab/
├── inventory          # Host inventory
├── hardening.yml      # OS hardening playbook
├── nginx.yml          # Nginx installation playbook
└── README.md

## Usage

Clone the repo and configure your inventory file with your target hosts:

    [servers]
    192.168.x.x ansible_user=youruser ansible_port=22

Run a playbook:

    ansible-playbook -i inventory hardening.yml --ask-become-pass

## Playbooks

### hardeningnew.yml
Automates baseline OS hardening on a fresh Rocky Linux 9 installation.

- Moves SSH from port 22 to 2222
- Disables root login and password authentication via SSH
- Updates SELinux context for new SSH port
- Configures firewalld rules accordingly
- Restarts sshd to apply changes

### nginx.yml
Installs and enables nginx as a persistent system service.

## Notes

- Always review playbooks before running against production systems
- Test in a VM environment first
- SELinux must be in enforcing mode for hardening playbook to work correctly
